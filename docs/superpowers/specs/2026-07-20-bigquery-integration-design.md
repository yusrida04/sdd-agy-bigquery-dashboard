# BigQuery Integration Design Spec

## Goal
Replace local static CSV data reads in the FastAPI e-commerce dashboard with live queries against the `thelook_ecommerce` dataset in BigQuery. Ensure high performance using a parallel thread pool and in-memory TTL cache, while maintaining high code quality with full automated mock tests.

## Requirements & Constraints
1. **Tech Stack**: Python 3.11+, FastAPI, `google-cloud-bigquery` library, `pandas` (if needed, but direct SQL preferred for SQL efficiency), `pytest`.
2. **Environment Configuration**:
   * `GOOGLE_CLOUD_PROJECT`: Project ID for BigQuery.
   * `BIGQUERY_DATASET`: Dataset ID (defaults to `thelook_ecommerce`).
3. **Data Source Indicator**: Update the dashboard UI's data source indicator to display "BigQuery" instead of "CSV".
4. **Performance**:
   * Parallel execution of queries.
