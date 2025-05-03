# 💹 Cryptocurrency Data Pipeline (GCP)

This project builds a **near real-time data pipeline** for the **top 100 cryptocurrency coins** using the [CoinGecko API](https://www.coingecko.com/en/api/documentation). The pipeline fetches market data every **5 minutes** and streams it through a serverless architecture built on **Google Cloud Platform**.

The data is processed and stored in **BigQuery** for analytics and visualization. The complete pipeline is built using:

- [Google Cloud Function](https://cloud.google.com/functions) – to fetch and transform crypto data
- [Google Cloud Scheduler](https://cloud.google.com/scheduler) – to trigger the function every 5 minutes
- [Google Cloud Pub/Sub](https://cloud.google.com/pubsub) – for event-driven messaging
- [Google Cloud Dataflow](https://cloud.google.com/dataflow) – for data transformation using Apache Beam
- [BigQuery](https://cloud.google.com/bigquery) – for real-time storage and querying
- [Looker Studio](https://lookerstudio.google.com/) – for data visualization

---

### 🧪 Sample Output Format:

| symbol | name     | current_price | market_cap   | market_cap_rank | fully_diluted_valuation | total_volume |
|--------|----------|----------------|---------------|------------------|--------------------------|---------------|
| btc    | Bitcoin  | 19494.84       | 374289077997  | 1                | 409756957292             | 23662114103   |
| eth    | Ethereum | 1328.6         | 160333583155  | 2                |                          | 8698392798    |
| usdt   | Tether   | 1.00           | 68488007086   | 3                |                          | 30216495050   |
| bnb    | BNB      | 274.46         | 44807811887   | 4                | 45312700938              | 44544105      |
| ...    | ...      | ...            | ...            | ...              | ...                      | ...           |

---

After fetching the data from the CoinGecko API, the function transforms the JSON response into a **clean, structured format** compatible with your BigQuery table schema.

The entire pipeline is powered by a **Python 3.8+ script** deployed on **Google Cloud Functions**, and executed via **HTTP trigger** using Cloud Scheduler every 5 minutes.

> 💡 Ideal for real-time market tracking, analytics dashboards, or trading bots.

---
