# Fraud Detection Analysis — SPL Queries

## Project Overview

This document contains the Splunk Search Processing Language (SPL) queries for my fraud detection analysis project, completed as part of the Commonwealth Bank Cybersecurity Virtual Experience.

The queries analyse fraudulent transactions by category, age, gender, merchant and transaction step.

**Dataset source type:** `fraud_dectection.csv`

> Note: These queries are documented examples based on the project's analysis requirements. Confirm the source type and field names against your Splunk environment before treating them as the exact saved dashboard searches.

---

## 1. Transaction Count by Category

```spl
sourcetype="fraud_dectection.csv"
| stats count by category
| sort - count
```

## 2. Total Fraudulent Transactions

```spl
sourcetype="fraud_dectection.csv" fraud=1
| stats count AS "Fraudulent Transactions"
```

## 3. Fraudulent Transactions by Age

```spl
sourcetype="fraud_dectection.csv" fraud=1
| stats count by age
| sort - count
```

## 4. Fraudulent Transactions by Gender

```spl
sourcetype="fraud_dectection.csv" fraud=1
| stats count by gender
| sort - count
```

## 5. Top 10 Merchants by Fraudulent Transactions

```spl
sourcetype="fraud_dectection.csv" fraud=1
| stats count by merchant
| sort - count
| head 10
```

## 6. Fraudulent Transactions by Step

```spl
sourcetype="fraud_dectection.csv" fraud=1
| stats count by step
| sort step
```

## 7. Fraud by Gender and Category

```spl
sourcetype="fraud_dectection.csv" fraud=1
| stats count by gender category
| sort - count
```

## 8. Top 10 Age and Merchant Combinations

```spl
sourcetype="fraud_dectection.csv" fraud=1
| stats count by age merchant
| sort - count
| head 10
```

---

## Key Skills Demonstrated

- Splunk Enterprise
- Search Processing Language (SPL)
- Fraud transaction analysis
- Data filtering and aggregation
- Statistical analysis
- Dashboard development and reporting

**Project:** Commonwealth Bank Cybersecurity Virtual Experience  
**Task:** Task 1 — Data Analysis and Fraud Detection
