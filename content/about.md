---
title: "about"
draft: false
hide_date: true
---

24 year old data engineer based in Bradford, UK — open to relocation or remote work.

---

## skills

**languages:** Python, SQL

**cloud & infrastructure:** AWS (S3, Lambda, CloudWatch, Secrets Manager, EventBridge, RDS), Terraform, Docker

**databases:** PostgreSQL

**libraries & frameworks:** pandas, boto3, pg8000, psycopg2, moto, dbt

**testing & devops:** pytest, GitHub Actions, Git, TDD, agile

**monitoring:** Grafana

---

## projects

**ToteSys ETL pipeline** — aug 2024 – sept 2024

- collaborated across a six-person agile team, contributing to sprint planning, daily stand-ups, code reviews, and final project presentation
- built a fully automated ETL pipeline across three Lambda functions: incremental extraction from a live PostgreSQL database using timestamp-based change detection, transformation into a Parquet-based OLAP star schema (7 dimension tables and 3 fact tables) using pandas and pyarrow, and loading into an AWS RDS data warehouse via SQLAlchemy
- provisioned all AWS infrastructure using Terraform with remote state in S3, including separate Lambda dependency layers, resource tagging, and IAM roles
- implemented CI/CD with GitHub Actions for automated Terraform deployment on merge to main, backed by a 1,214-line pytest test suite using moto for AWS service mocking
- stack: Python, SQL, AWS (S3, Lambda, CloudWatch, Secrets Manager, EventBridge, RDS), Terraform, PostgreSQL, pandas, pg8000, boto3, moto, GitHub Actions

**GDPR obfuscator** — jan 2025 – mar 2025

- versioned Python library for GDPR-compliant PII detection and obfuscation in AWS S3 CSV files
- exposed as both a reusable library and CLI tool with a 515-line pytest test suite with moto-based S3 mocking
- includes Black formatting, Safety dependency scanning, and DeepSource for test coverage reporting

**FuelNearMe** — apr 2026 – present

- CLI tool fetching data from the government's Fuel Finder REST API to find the cheapest nearby fuel stations by address using haversine distance calculations and bounding box pre-filtering
- planned: integrate AWS Lambda to cache price data; enable historical price tracking
- stack: Python, pandas, numpy, geopy, requests, uv

**this site** — aug 2023 – present

- portfolio site built with Hugo and deployed on Cloudflare Pages via automated CI/CD
- stack: Hugo, GitHub Actions

---

## experience

**IT systems administrator** — Mortimer Site Services Ltd (oct 2022 – present)

- deploy and manage Microsoft 365 and Exchange Online infrastructure
- orchestrated website modernisation and migration to a new VPS, resolving a long-standing SSL issue
- migrated company data from on-premises file storage to Dropbox

**operations associate** — GoPuff, Leeds (jan 2026 – present)

- maintained consistent employment and continued independent technical development alongside exposure to real-time inventory systems in a high-volume operational environment

**freelance data engineer** — self-employed via Tech Returners/Northcoders (jan 2025 – mar 2025)

- delivered a GDPR-compliant PII obfuscation tool on commission against a defined client brief
- packaged as a standalone Python library with a full pytest test suite, deployed against CSV data in AWS S3

---

## education

**Northcoders** — bootcamp certificate in data engineering (june 2024 – sept 2024)

- 13-week intensive programme covering Python, SQL, PostgreSQL, AWS, Terraform, and data pipeline architecture

**the University of Manchester** — DipHE in biochemistry (sept 2021 – apr 2024)

- completed two years of a BSc, awarded the DipHE qualification on exit
- applied Python for data sanitisation and transformation; conducted statistical analysis (t-tests, ANOVA, regression) on experimental datasets

