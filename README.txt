# Week 1 Data Engineering Lab

## Scenario
A small online shop sends daily order data as a CSV file. A manager wants a reliable summary of valid orders by city.

## Pipeline plan
- Source: `orders.csv` (daily batch file)
- Raw destination: BigQuery table `de_intro.raw_orders`
- Curated output: query results after checking and filtering the data
- User of the output: shop manager

## Local data check
Before reporting, record at least two issues you found in the CSV and what you recommend doing with each.

1. Issue and recommendation: the order_date column should be more detailed to include not just the date but the timestamp for each sale. Also, the row with order_id O-1005 contains numbers that do not make sense as the quantity and order_total values are set to 0 with the status being set to delivered, this record should be inspected and investigate what happened in this case.
2. Issue and recommendation: the record O-1006 is duplicated with all values of the record being the same (this could be a case where a customer ordered the same things twice, that's why the order_date should be expanded to include the timestamp of the sale as well the see whether this record is valid or not).

## What the pipeline does
Complete after the lab: In one sentence, describe how the data moves from the source to a useful output.
