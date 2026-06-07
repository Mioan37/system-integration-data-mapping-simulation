# System Integration & Data Mapping Simulation

## 📌 Project Overview

This is a learning portfolio project designed to simulate how two business systems exchange data.

The goal is to demonstrate Technical Business Analyst thinking without claiming professional API or system integration work experience.

The project uses a simple business scenario based on operational sales and inventory data from a fish market.

- **Source System A:** Fish Market Sales / Inventory CSV export
- **Target System B:** Reporting / Analytics platform requiring structured JSON-style data
- **Business Need:** Ensure accurate data flow between systems so sales, inventory, product categories, revenue, stock levels and waste can be reported correctly.

---

## ❓ Business Question

How can daily fish market sales and inventory data be mapped, transformed and validated from a CSV source system into a structured JSON-style format required by a reporting platform?

This project focuses on documenting the data flow between systems, defining source-to-target field mapping, applying transformation rules and checking that the final output supports accurate reporting of sales, inventory, revenue and waste.

---

## ✅ Project Outcome

The project produces a simple source-to-target mapping document and sample JSON payload showing how operational CSV data can be converted into a structured format for reporting and analytics.

The output helps ensure that transaction dates, products, categories, revenue, stock levels and waste values are transferred accurately between systems.

---

## 📂 Project Files

```text
README.md
sample_source_sales_inventory.csv
sample_target_payload.json
```

### File Description

| File | Purpose |
|---|---|
| `README.md` | Explains the business scenario, mapping logic, validation rules and project purpose |
| `sample_source_sales_inventory.csv` | Example CSV export from the source sales and inventory system |
| `sample_target_payload.json` | Example JSON-style output required by the target reporting platform |

---

## 🧩 Why This Project Is Relevant

This project demonstrates skills relevant to entry-level Technical Business Analyst, Business Analyst and Data Analyst roles, including:

- Understanding business requirements
- Identifying source and target data fields
- Creating a source-to-target data mapping table
- Defining transformation rules
- Thinking through data validation
- Documenting data flow between systems
- Communicating technical concepts in simple business language

---

## 🐟 Business Scenario

The fish market needs to move daily sales and inventory data into a reporting system.

The reporting system must show:

- Daily revenue
- Units sold by product
- Product category performance
- Stock remaining
- Waste risk
- Seasonal demand patterns

The problem is that the source data is not always structured in the same format required by the reporting system.

The purpose of this simulation is to show how source data can be mapped, transformed and validated before being used for reporting.

---

## 🗂️ Source Data Example

The source system exports daily sales and inventory records in CSV format.

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

## 🎯 Target Data Example

The target reporting platform requires the data to be structured in a JSON-style format.

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

## 🔄 Data Mapping Table

| Source Field | Target Field | Transformation Rule | Validation Rule |
|---|---|---|---|
| sale_date | transactionDate | Convert to YYYY-MM-DD format | Must not be blank |
| product_name | product.name | Direct mapping | Must match product reference list |
| category | product.category | Direct mapping | Must not be blank |
| quantity_kg | sales.quantityKg | Convert to decimal number | Must be greater than 0 |
| unit_price | sales.unitPrice | Convert to decimal number | Must be greater than 0 |
| revenue | sales.totalRevenue | Calculate as quantity_kg x unit_price | Must equal calculated revenue |
| stock_start_kg | inventory.openingStockKg | Convert to decimal number | Must be greater than or equal to stock_end_kg |
| stock_end_kg | inventory.closingStockKg | Convert to decimal number | Must be greater than or equal to 0 |
| waste_kg | inventory.wasteKg | Convert to decimal number | Must be greater than or equal to 0 |

---

## 🔁 Data Flow

The simulated data flow follows these steps:

1. Export sales and inventory data from the source system as CSV.
2. Review and clean the source data.
3. Identify source fields and target fields.
4. Map source fields to the required target structure.
5. Apply transformation rules where needed.
6. Convert structured records into JSON-style output.
7. Validate dates, product names, revenue totals, stock values and missing fields.
8. Use the transformed output for reporting and analytics.

---

## ✅ Validation Checklist

Before the data is accepted by the target reporting platform, the following checks should be completed:

- [ ] No missing transaction dates
- [ ] Product names match the product reference list
- [ ] Product categories are consistent
- [ ] Quantity values are numeric
- [ ] Price values are numeric
- [ ] Revenue equals quantity x unit price
- [ ] Opening stock is greater than or equal to closing stock
- [ ] Closing stock is not negative
- [ ] Waste values are not negative
- [ ] Output structure matches the target JSON-style format

---

## 📊 Reporting Requirements Supported

The mapped output supports reporting on:

- Daily sales revenue
- Product-level sales performance
- Product category performance
- Quantity sold by product
- Opening and closing stock levels
- Waste quantity
- Inventory movement
- Seasonal demand patterns

---

## 🧠 Technical Business Analyst Skills Demonstrated

This project demonstrates practical understanding of:

- Requirements interpretation
- Source-to-target data mapping
- Data transformation rules
- Data validation logic
- Integration documentation
- Business process understanding
- Reporting requirements
- Clear communication between business and technical users
- Translating business needs into structured data requirements

---

## 🛠️ Tools & Concepts Used

- CSV data structure
- JSON-style target payload
- Data mapping documentation
- Basic transformation rules
- Data validation checklist
- Business process analysis
- Reporting and analytics requirements

---

## ⚠️ Assumptions

This project uses the following assumptions:

- The source system exports daily sales and inventory data in CSV format.
- Product names should match an approved product reference list.
- Revenue should be calculated as quantity sold multiplied by unit price.
- Stock values cannot be negative.
- The target system requires structured JSON-style data.
- The project is a simulation and does not connect to a live API or database.

---

## 📌 Honest Positioning

This is a learning and portfolio project.

It does not claim professional API integration, software engineering or live system implementation experience.

Its purpose is to show practical understanding of integration concepts, data flow, source-to-target mapping, transformation rules, validation checks and documentation.

---

## 🎯 Portfolio Value

This project is useful for showing entry-level capability in Technical Business Analyst and Business Analyst work because it demonstrates how business data can be understood, documented and prepared for system-to-system reporting.

It shows the ability to think about both the business need and the technical structure required to support accurate reporting.
