# ⚡ Energy Consumption Dashboard

> An end-to-end data engineering project analyzing global energy consumption across 25+ countries, 6 regions, and 5 energy sources — powered by AWS, Snowflake, and Tableau.

![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white)
![Snowflake](https://img.shields.io/badge/Snowflake-%2329B5E8.svg?style=for-the-badge&logo=snowflake&logoColor=white)
![Tableau](https://img.shields.io/badge/Tableau-E97627?style=for-the-badge&logo=Tableau&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

---

## 📌 What does this project do?

Designed and built a cloud-based data pipeline that ingests raw energy data into **AWS S3**, transforms it using **Snowflake (ELT)**, and visualizes it through an interactive **Tableau dashboard** — covering KWH and CSU metrics for business decision-making.

---

## 🏗️ Architecture

```
Raw Data (CSV/JSON)
        │
        ▼
   ┌─────────┐
   │  AWS S3  │  ← Data Lake (raw storage)
   └────┬─────┘
        │
        ▼
   ┌───────────┐
   │ Snowflake │  ← Data Warehouse (ELT + SQL transformations)
   └────┬──────┘
        │
        ▼
   ┌─────────┐
   │ Tableau │  ← Dashboard (KWH & CSU visualizations)
   └─────────┘
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Cloud Storage | AWS S3 |
| Access Management | AWS IAM |
| Data Warehouse | Snowflake |
| Transformation | SQL (ELT) |
| Visualization | Tableau Desktop |
| Data Format | CSV, JSON |

---

## 📊 Dashboard Preview

![Energy Consumption Dashboard](tableau/screenshots/dashboard.png)

### Visualizations Included

| Chart | Metric | Coverage |
|-------|--------|----------|
| KWH by Country | Kilowatt Hours | 25+ countries |
| KWH by Region | Kilowatt Hours | 6 global regions |
| KWH by Energy Source | Kilowatt Hours | Geothermal, Biomass, Solar, Hydro, Wind |
| CSU by Country | Carbon/Consumption Units | 25+ countries |
| CSU by Region | Carbon/Consumption Units | 6 global regions |
| CSU by Energy Source | Carbon/Consumption Units | 5 energy sources |

---

## 📈 Key Insights

- 🌏 **Australia & New Zealand** recorded the highest KWH consumption
- 💨 **Wind energy** led all sources in CSU contribution globally
- 🌍 **Africa & Europe** showed comparable regional KWH levels
- ☀️ **Solar & Hydro** showed strong growth potential in consumption patterns

---

## 🚀 How to Run This Project

**Prerequisites:** AWS account · Snowflake account · Tableau Desktop or Tableau Public

**Step 1 — AWS S3**
1. Create an S3 bucket (e.g. `energy-consumption-data`)
2. Upload your raw CSV dataset
3. Attach IAM role for secure Snowflake ↔ S3 access

**Step 2 — Snowflake**

Run SQL files in this order:
```sql
-- 1. Create database, schema, and tables
snowflake/schema.sql

-- 2. Set up external stage pointing to S3
snowflake/stage_setup.sql

-- 3. Run ELT transformation queries
snowflake/queries.sql
```

**Step 3 — Tableau**
1. Open Tableau Desktop
2. Connect to **Snowflake** as the data source
3. Select your database and schema
4. Open `tableau/energy_dashboard.twbx`

---

## 📁 Project Structure

```
energy-consumption-dashboard/
├── README.md
├── .gitignore
├── .env.example
├── aws/
│   ├── s3_setup.md
│   └── iam_policy.json
├── snowflake/
│   ├── schema.sql
│   ├── stage_setup.sql
│   └── queries.sql
├── tableau/
│   ├── screenshots/
│   │   └── dashboard.png
│   └── energy_dashboard.twbx
└── data/
    └── sample_data.csv
```

---

## 🔐 Environment Variables

All values below are **placeholders only** — never add real credentials to GitHub.

Create a `.env` file on your local machine with your actual values:

```env
SNOWFLAKE_ACCOUNT=your_account
SNOWFLAKE_USER=your_username
SNOWFLAKE_PASSWORD=your_password
SNOWFLAKE_DATABASE=ENERGY_DB
SNOWFLAKE_WAREHOUSE=COMPUTE_WH
AWS_S3_BUCKET=your-bucket-name
AWS_REGION=us-east-1
```

> ⚠️ Add `.env` to your `.gitignore`. Only `.env.example` (with placeholder values) should be pushed to GitHub.

---

## 📬 Contact

Have questions or feedback? Feel free to open an issue or connect on LinkedIn!
