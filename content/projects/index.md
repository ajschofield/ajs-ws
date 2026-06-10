---
title: "projects"
draft: false
hide_date: true
---

you can find all my projects below.

## nc-de-totesys-solo

[[src]](https://github.com/ajschofield/nc-de-totesys-solo)
[[video]](https://vimeo.com/1149980207)

an improved version of the ETL pipeline I contributed to
during my time as a student on the Northcoders Data Engineering
bootcamp.

built in Python and deployed on AWS, it implements
a fully automated pipeline that extracts data from a PostgreSQL
operational database on a 30-minute schedule. this data is
scheduled in S3 as CSV, transforms it into a star schema
(dimension and fact tables) stored in a Parquet format, and
then loaded into a data warehouse. it runs entirely on AWS Lambda
functions triggered by EventBridge and S3 event notifications, with
Terraform used for easy deployment.

**key areas that were improved**:

1. non-idempotent loading meant that if the load Lambda ran twice (e.g. due to
   redeployment or retries), then it would blindly append the same data to
   the warehouse tables again, duplicating rows. mechanisms were added to
   skip dimension tables that already have data, and load markers now track
   which specific parquet files have already been loaded into the mutable
   tables
2. incremental processing was needed to address the fact that every time the
   transform lambda ran, all CSV files from the extract bucket were read and
   everything was reprocessed from scratch, even if the data had already been
   transformed. this could be quite expensive and time-consuming over time,
   especially if this project was deemed to be 'production-ready'. a watermark,
   stored in S3, records the timestamp of the last successful transform run.
   then, checks were added to filter out any S3 objects older than that stored
   timestamp so that only new data gets reprocessed, saving compute time.
3. due to the limited time we had to reach the MVP, test quality dropped over
   the course of development. by the end, we had many failing tests due to
   wrong expected results, placeholder code that was never finished, and
   structural issues that were unfortunately missed until now. the tests now
   mostly pass, but there are still some that have been skipped due to remaining
   issues.

## de-project-bentley

[[src]](https://github.com/ajschofield/de-project-bentley)
[[video]](https://vimeo.com/1149980207)

Please see [above](#nc-de-totesys-solo) for project description.

## gdpr-obfuscator
[[src]](https://github.com/ajschofield/gdpr-obfuscator)

a python library that automatically detects and removes PII from CSV files
stored in AWS S3. it accepts a JSON input specifying an S3 file path and the
fields to anonymise, reads the data directly from the bucket, obfuscates those
sensitive values, and then returns the result as a byte stream. this result
is then ready to be written straight back to S3. whilst it is intended to be
used as a library, I also created a CLI tool for quick local use.

the project is fully tested with unit and integration tests across all core
modules such as file reading, obfuscation logic, the CLI and more.

there are still areas to improve, but I was happy with the outcome at the
end of development.
