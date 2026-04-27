# System Integration & Data Mapping Simulation

## Project Overview

This is a learning portfolio project designed to simulate how two business systems exchange data.

The goal is to demonstrate Technical Business Analyst thinking without claiming professional API experience.

The project uses a simple business scenario based on operational sales and inventory data:

- Source System A: Fish Market Sales / Inventory CSV export
- Target System B: Reporting / Analytics platform requiring structured JSON-style data
- Business Need: Ensure accurate data flow between systems so sales, inventory, product categories and revenue can be reported correctly.

---

## Why This Project Is Relevant

This project demonstrates skills relevant to Technical Business Analyst roles, including:

- Understanding business requirements
- Identifying source and target data fields
- Creating a data mapping table
- Defining transformation rules
- Thinking through data validation
- Documenting data flow between systems
- Communicating technical concepts in simple business language

---

## Business Scenario

The fish market needs to move daily sales and inventory data into a reporting system.

The reporting system must show:

- Daily revenue
- Units sold by product
- Product category performance
- Stock remaining
- Waste risk
- Seasonal demand patterns

The problem is that the source data is not always structured in the same format required by the reporting system.

---

## Source Data Example

| Source Field | Example |
|---|---|
| sale_date | 2019-07-15 |
| product_name | Sardines |
| category | Small Fish |
| quantity_kg | 12.5 |
| unit_price | 6.00 |
| revenue | 75.00 |
| stock_start_kg | 15.0 |
| stock_end_kg | 2.5 |
| waste_kg | 0 |

---

## Target Data Example

```json
{
  "transactionDate": "2019-07-15",
  "product": {
    "name": "Sardines",
    "category": "Small Fish"
  },
  "sales": {
    "quantityKg": 12.5,
    "unitPrice": 6.00,
    "totalRevenue": 75.00
  },
  "inventory": {
    "openingStockKg": 15.0,
    "closingStockKg": 2.5,
    "wasteKg": 0
  }
}
```

---

## Data Mapping Table

| Source Field | Target Field | Transformation Rule | Validation Rule |
|---|---|---|---|
| sale_date | transactionDate | Convert to YYYY-MM-DD | Must not be blank |
| product_name | product.name | Direct mapping | Must match product list |
| category | product.category | Direct mapping | Must not be blank |
| quantity_kg | sales.quantityKg | Decimal number | Must be greater than 0 |
| unit_price | sales.unitPrice | Decimal number | Must be greater than 0 |
| revenue | sales.totalRevenue | quantity_kg x unit_price | Must equal calculated revenue |
| stock_start_kg | inventory.openingStockKg | Decimal number | Must be >= stock_end_kg |
| stock_end_kg | inventory.closingStockKg | Decimal number | Must be >= 0 |
| waste_kg | inventory.wasteKg | Decimal number | Must be >= 0 |

---

## Data Flow

1. Export sales and inventory data from the source system as CSV.
2. Clean and validate the source data.
3. Map source fields to the target data structure.
4. Apply transformation rules where needed.
5. Convert structured records into JSON-style output.
6. Validate totals, stock values and missing fields.
7. Load or use the transformed data for reporting.

---

## Validation Checklist

- [ ] No missing transaction dates
- [ ] Product names match the product reference list
- [ ] Quantity and price values are numeric
- [ ] Revenue equals quantity x unit price
- [ ] Stock end is not negative
- [ ] Waste values are not negative
- [ ] Product categories are consistent
- [ ] Output structure matches the target format

---

## Technical Business Analyst Skills Demonstrated

- Requirements interpretation
- Data mapping
- Integration documentation
- Source-to-target analysis
- Data validation
- Business process understanding
- Clear communication between business and technical users

---

## Honest Positioning

This is a learning and portfolio project.

It does not claim professional API integration experience.

Its purpose is to show practical understanding of integration concepts, data flow, data mapping and documentation.
