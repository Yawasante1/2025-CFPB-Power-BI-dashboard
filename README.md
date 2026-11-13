
# CFPB Consumer Complaints | 2025 Power BI Dashboard

An interactive Power BI report exploring published U.S. consumer complaints about financial products and services. The report uses the date the Consumer Financial Protection Bureau (CFPB) received each complaint and covers **1 January through 31 December 2025**.

<!-- Add the dashboard image to docs/dashboard.png, then uncomment the image below.
![2025 CFPB Consumer Complaints Power BI dashboard](docs/dashboard.png)
-->

## 2025 findings

| Metric | Result |
| --- | ---: |
| Total complaints | 5,442,931 |
| Timely response rate | 99.5% |
| Complaints marked as late | 24,517 |

- **Credit reporting or other personal consumer reports** accounted for **4,810,291 complaints**, about **88.4%** of the report total.
- **Incorrect information on your report** was the most common issue, with **2,834,674 complaints**.
- The monthly timely response rate ranged from **99.31% in March** to **99.69% in October**.
- **Closed with explanation** was the most common company response category, with **3,194,905 complaints**.

## Explore the report

Use the **Product**, **State**, and **Complaint Date Range** slicers to explore a subset. The overview includes monthly trends for complaint volume and response timeliness, plus breakdowns by financial product, issue, and company response. Monthly response-rate labels show two decimal places. The headline rate shows one decimal place.

## Data and methodology

The source is the [CFPB Consumer Complaint Database](https://www.consumerfinance.gov/data-research/consumer-complaints/). Power Query imports the CSV, keeps the fields used by the report, and omits free-text complaint narratives. The month labels use abbreviated names sorted by month number.

| Measure | Definition |
| --- | --- |
| Total Complaints | Distinct count of nonblank complaint IDs |
| Timely Response Rate | Distinct complaints marked `Yes` divided by distinct complaints marked `Yes` or `No` in `Timely response?` |
| Late Responses | Distinct complaints marked `No` in `Timely response?` |

The **Late Responses** card uses the timeliness flag. The **Untimely response** bar uses the separate `Company response to consumer` field. See the [CFPB field definitions](https://www.consumerfinance.gov/complaint/data-use/).


[Download the Power BI report (.pbix)](../../releases/latest)

## Open or reproduce the report

1. Open the project's `.pbix` file in **Power BI Desktop**.
2. To refresh from source, download and extract the CSV from the [CFPB Consumer Complaint Database](https://www.consumerfinance.gov/data-research/consumer-complaints/). Keep the raw CSV outside the repository. The extracted file used for this project was over 5 GB.
3. In **Transform data**, select the `complaints` query and update its **Source** step to point to your local CSV. Select **Close & Apply**.
4. Set the report's date range to **1 January through 31 December 2025**. A newer download can yield different counts because the CFPB updates its database.

## Interpretation

The CFPB database covers published complaints and is not a representative sample of consumer experiences. Complaint counts can reflect factors such as company size and market share. See the [CFPB guidance on interpreting complaint volume](https://www.consumerfinance.gov/data-research/consumer-complaints/).

## Author

**Yaw Asante** - Data Scientist, Statistician and Financial Economist

Email: vkpoasante@gmail.com

## License
**MIT**
