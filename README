# Startup Closure Analysis

This project looks at which factors are linked to startup closure. The dataset records each company's status (operating, acquired, or closed), market, country, funding, and founding date. The goal is to find out which characteristics go along with a company closing.

## Data cleaning

- Dropped rows with no status, since a company without an outcome can't be analyzed.
- Dropped rows with no `founded_at` (about 29% of the data). The status mix of these rows was the same as the rest of the data, so this shouldn't bias the results. Rows with founding dates before 1900 were also dropped.
- Dropped the few rows (0.27%) with no company name.
- Filled missing `country_code`, `region`, and `market` with "Unknown" so those companies stay in.
- Converted `funding_total_usd` from text to numeric and filled blanks with 0, assuming a blank means no recorded funding.
- Converted `founded_at` and `first_funding_at` to dates.
- Where name, founding date, and country matched, kept one row (the one with the most funding).
- Dropped identifiers (`permalink`, `homepage_url`), columns that give away the outcome (`post_ipo_equity`, `post_ipo_debt`, `last_funding_at`), and redundant or high-cardinality columns (`founded_year`, `founded_month`, `founded_quarter`, `category_list`, `state_code`, `city`).

## Findings

Overall, 86.8% of startups are operating, 7.9% were acquired, and 5.3% closed. The 5.3% closure rate is the baseline for everything below.

### Market

Market is the strongest categorical factor. Closure is highest in Curated Web (14.7%), Games (9.9%), Mobile (7.5%), and Advertising (7.1%). It is lowest in Biotechnology (3.2%), Health Care (3.5%), and Enterprise Software (3.6%).

### Funding

Closed companies had the lowest median funding at $400,000, compared with $1,000,000 for operating companies and $6,465,000 for acquired ones. Closure also drops as the number of funding rounds goes up: 6.4% at one round, 2.9% at three, and 1.3% at six.

### Founding year

The closure rate falls from about 7% for companies founded in 2005-2008 to 0.7% for those founded in 2013. This mostly reflects exposure time, since newer companies have had less time to close.

### Country

Country has little effect. Nearly all of the top 10 countries are within about one point of the 5.3% baseline. Companies with an unknown country close more often (8.7%), and China is lower (3.1%), though China's younger companies may explain that.

## Conclusion

Market and funding are the factors most strongly linked to closure. Web and consumer-facing markets close more often, while biotech, health care, and enterprise software close less. Companies with more funding and more funding rounds are less likely to close. Country has little effect, and founding year mostly reflects how long a company has had to close.

## Limitations

- This shows association, not causation. Companies that survive longer have more time to raise money, so funding may partly be a result of survival rather than a cause.
- There is no closure date, so the analysis can't measure how long companies lasted before closing.
- Removing rows without a founding date cut the dataset by about 29%.
- Missing funding was treated as 0, but some of those companies may have raised money without disclosing the amount.
- Results for markets or countries with few companies are unreliable.
