---
name: gestor-autonomos
description: >
  Management and accounting for freelancers in Spain. Use when the user
  needs to calculate quarterly VAT (model 303), calculate fractional payments
  of personal income tax (model 130), manage income and expense books, verify
  issued or received invoices, calculate withholdings, prepare quarterly
  declarations, estimate taxes to pay, process Stripe or
  Substack income (separating EU payments with VAT vs exempt international payments,
  converting currencies to euros), or any consultation about taxation or
  accounting for freelancers in Spain. This skill guarantees mathematically
  accurate calculations using Python scripts and applies current Spanish
  tax regulations.
---

# Freelancer Manager Spain (Gestor Autónomos España)

Skill for accounting and tax management of self-employed workers in Spain with mathematically accurate calculations.

> [!CAUTION]
> **WARNING**: This skill is a support tool and does not replace professional advice. The calculations and suggestions generated must be reviewed by an accountant or qualified professional. The use of this tool is the sole responsibility of the user. Mafia Claude Skills and its contributors are not responsible for errors in tax declarations or penalties resulting from its use.

## Core principles

1. **Mandatory mathematical accuracy**: ALWAYS use the Python scripts for any calculation. NEVER calculate mentally.
2. **Legal basis**: All operations follow the regulations of the AEAT (Tax Agency).
3. **Double verification**: Every calculation must be verifiable and traceable.

## Main workflow

### Step 1: Identify the type of operation

**What does the user need?**
- Calculate quarterly VAT → Execute `scripts/calcular_iva.py`
- Calculate quarterly IRPF (income tax) → Execute `scripts/calcular_irpf.py`
- Process invoices/expenses → Execute `scripts/procesar_facturas.py`
- Generate accounting book → Execute `scripts/generar_libro.py`
- **Process Stripe/Substack income** → Execute `scripts/procesar_stripe.py`
- Regulatory consultation → See `references/normativa_fiscal.md`

### Step 2: Gather data

Request the necessary information from the user depending on the operation:

**For quarterly VAT (IVA):**
- Issued invoices (taxable base + passed-on VAT)
- Deductible received invoices (taxable base + borne VAT)
- Quarter (Q1, Q2, Q3, Q4) and year

**For IRPF (Model 130):**
- Quarter income (excluding VAT)
- Quarter deductible expenses (excluding VAT)
- Withholdings applied by clients
- Previous fractional payments of the year

**For invoices:**
- Invoice number
- Date
- Client/provider NIF/CIF
- Concept
- Taxable base
- Applicable VAT rate
- IRPF withholding (if applicable)

### Step 3: Execute calculations with scripts

MANDATORY to use scripts for all numerical calculations:

```bash
# Calculate quarterly VAT
python3 scripts/calcular_iva.py --iva-repercutido <amount> --iva-soportado <amount>

# Calculate IRPF model 130
python3 scripts/calcular_irpf.py --ingresos <amount> --gastos <amount> --retenciones <amount> --pagos-anteriores <amount>

# Process invoice list from CSV
python3 scripts/procesar_facturas.py --archivo <path.csv> --tipo <emitidas|recibidas>

# Generate income and expense book
python3 scripts/generar_libro.py --trimestre <1-4> --año <YYYY> --facturas-emitidas <path> --facturas-recibidas <path>
```

### Step 4: Present results

Show the user:
1. Complete breakdown of the calculation
2. Final result with monetary format (€)
3. Submission deadline if applicable
4. Relevant warnings or considerations

## VAT Rates in Spain (2024-2025)

| Rate | Percentage | Application |
|------|------------|-------------|
| General | 21% | Most goods and services |
| Reduced | 10% | Food, transport, hospitality |
| Super-reduced | 4% | Bread, milk, fruits, vegetables, books, press |
| Exempt | 0% | Healthcare, education, insurance, financial services |

## IRPF Withholdings on invoices

| Situation | Withholding |
|-----------|-------------|
| Professionals (general) | 15% |
| New freelancers (first 3 years) | 7% |
| Courses, conferences | 15% |
| Leases | 19% |

## Quarterly submission deadlines

| Quarter | Period | Submission deadline |
|---------|--------|---------------------|
| Q1 | January-March | April 1-20 |
| Q2 | April-June | July 1-20 |
| Q3 | July-September | October 1-20 |
| Q4 | October-December | January 1-30 (following year) |

## Main deductible expenses

See full details in `references/normativa_fiscal.md`

**100% Deductible:**
- Freelancer social security quota (Cuota de autónomos)
- Accounting and consultancy
- Civil liability insurance
- Office supplies
- Hosting, domains, software
- Activity-related training
- Advertising and marketing

**Deductible with limits:**
- Utilities (30% if working from home)
- Vehicle (50% maximum, depending on professional use)
- Per diems and travel (with daily limits)

## Important warnings

1. **Never approximate**: Tax calculations must be exact to the cent.
2. **Keep vouchers**: Mandatory to keep invoices for a minimum of 4 years.
3. **Verify NIFs**: Always validate that NIFs/CIFs are correct.
4. **VAT coherence**: Borne VAT is only deductible if linked to the activity.

## Stripe/Substack Integration

### ⚠️ IMPORTANT - Difference between Model 303 and Model 130

**Model 303 (Quarterly VAT):**
- DOES NOT include taxable base in the submission
- Only reports:
  - Box 03: Accrued VAT quota (21% from EU clients)
  - Box 60: Exempt exports (taxable base of non-EU)

**Model 130 (Quarterly IRPF):**
- DOES include taxable base (sum of EU + non-EU)
- Then subtracts deductible expenses (fees)
- Result: net yield of the quarter

### IMPORTANT - Applied tax rules

**1. The charged price INCLUDES VAT (Tax Inclusive)**
- The amount you charge the client already has VAT inside
- To extract the taxable base: `Base = Total / 1.21`
- DO NOT multiply by 0.21 (that would be adding VAT on top)
- Example: If you charge 60€ → Base = 49.59€, VAT = 10.41€

**2. Territoriality is determined by COUNTRY, not by currency**
- A client from Chile who pays in EUR → Export (without VAT)
- A client from Spain who pays in USD → Includes VAT
- Priority: `country (billing)` > `country (ip)`

**3. Payments without identified country → Conservative criterion (EU)**
- If there is no country, it is treated as an EU client (pays VAT)
- It is safer tax-wise even if you pay a bit more

**4. Fees (Substack + Stripe) are deductible expenses**
- They are subtracted in the IRPF (Model 130)
- They DO NOT affect VAT

### Supported formats

**Substack CSV (native format):**
```
email,date,currency,amount,Substack fee,Stripe fee,...,country (ip),country (billing)
user@mail.com,02-Oct-25,eur,€60.00,€6.00,€1.15,...,ES,ES
```

**Stripe Dashboard CSV:**
```
id,Amount,Currency,Created (UTC),country (billing),Status,...
pi_xxx,60.00,eur,2025-10-02,ES,succeeded,...
```

### Script usage

```bash
# Process Substack or Stripe CSV:
python3 scripts/procesar_stripe.py --archivo pagos.csv --trimestre 4 --año 2025

# The script automatically:
# - Detects format (Substack or Stripe)
# - Parses amounts with symbol (€60.00, CA$140.00)
# - Extracts taxable base by dividing by 1.21 (not multiplying)
# - Classifies by client COUNTRY (not by currency)
# - Calculates fees as deductible expenses
```

### Generated results

**For Model 303 (VAT):**
- Box 03: VAT quota to pass on (21% of the EU base)
- Box 60: Exempt exports (non-EU clients) - IMPORTANT: it is reported as base, not as quota

**For Model 130 (IRPF):**
- Taxable base: Sum of bases of EU + non-EU clients
- Expenses: Substack + Stripe fees (deductible)
- Net yield: Taxable base - Expenses

### EU-27 Countries (reference)

AT, BE, BG, CY, CZ, DE, DK, EE, ES, FI, FR, GR, HR, HU, IE, IT, LT, LU, LV, MT, NL, PL, PT, RO, SE, SI, SK

**⚠️ United Kingdom (GB/UK) is NOT in the EU since 2021 → Exempt**

### Practical example

```
Payment of 60€ from Spain (ES):
  Taxable base: 60 / 1.21 = 49.59€
  VAT included:   60 - 49.59 = 10.41€

Payment of 60€ from Chile (CL):
  Taxable base: 60€ (total, without division)
  VAT: 0€ (exempt export)

Payment of 85€ without identified country:
  → Treated as EU (conservative)
  Taxable base: 85 / 1.21 = 70.25€
  VAT included:   85 - 70.25 = 14.75€
```

## Regulatory consultations

For questions about legislation, consult `references/normativa_fiscal.md` which contains:
- VAT Law (Law 37/1992)
- IRPF Law (Law 35/2006)
- Invoicing regulation
- AEAT criteria
