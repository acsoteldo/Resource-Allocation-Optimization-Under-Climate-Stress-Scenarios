# Resource Allocation Optimization Under Climate Stress Scenarios
Simulate optimal allocation of limited resources (aid, shelters, funding) under climate stress conditions.

## Getting Started: 
1. Report and presentation
2. data/: Contains cleaned datasets used for the analysis
3. notebooks/: Jupyter notebooks
4. visualizations/: Tableau visualizations and dashboard
5. scripts/: Python and SQL scripts for data analysis

### Tools:
Excel, Jupyter, Python, SQL, Tableau

### Data Sources:
This analysis integrates the following cleaned and standardized datasets:
* American Community Survey (ACS)[^1] – demographic and socioeconomic characteristics at the census tract level
* CDC Social Vulnerability Index (SVI)[^2] – measures community vulnerability across socioeconomic status, household composition, minority status, and housing/transportation
* FEMA National Risk Index (NRI)[^3] – multi-hazard risk metrics and expected annual loss estimates
* FEMA National Flood Hazard Layer (NFHL)[^4] – spatial floodplain boundaries used to determine physical flood exposure
* NOAA Billion-Dollar Disasters[^5] – historical context on the frequency and cost of extreme climate events

All tract-level datasets are joined using a standardized GEOID, while flood exposure is derived through spatial intersection with FEMA floodplain polygons (see _data/_ for questions).

The analysis will be based on the cleaned master dataset, which has 84 fields, including:
* "geoid": 11-digit census tract GEOID (state+county+tract). Join key.
* "acs_median_hh_income": ACS median household income (USD).
* "acs_population": ACS total population estimate.
* "svi_overall_pctile": CDC SVI overall percentile (0-1, higher = more vulnerable).
* "nri_composite_score": FEMA NRI composite risk score.
* "nri_eal_total_usd": FEMA NRI expected annual loss (USD), composite.
* "nfhl_in_floodplain": Boolean: tract intersects FEMA NFHL flood zone polygons.

Geographic Note: All analysis is conducted at the census tract level. City and ZIP fields are provided for interpretability [^6].
  

## Problem Definition
Although South Florida is widely recognized as a climate-vulnerable region, climate risk is unevenly distributed across communities. Many households face elevated financial risk due to the combined effects of hazard exposure, limited adaptive capacity, and underlying social vulnerability.

### Relevance:
Understanding how climate-related hazards translate into household financial instability at the census tract level is crucial for several reasons:
* Policymakers and planners need tract-level insights into where climate hazards intersect with social vulnerability to make informed decisions about climate adaptation investments, land-use planning, and resilience funding allocation.
* Housing and financial stability stakeholders can use localized risk information to better assess potential wealth loss, housing instability, and displacement risks associated with flooding and extreme weather events.
* Community advocates and equity-focused organizations may leverage tract-level climate risk data to identify underserved communities facing disproportionate financial impacts and to support targeted resilience and mitigation efforts.
* Researchers and analysts can use integrated hazard, vulnerability, and exposure data to move beyond regional averages and develop more accurate, equity-centered models of climate risk and household financial outcomes.

## Hypothesis
Households located in census tracts with higher exposure to climate-related hazards (particularly flooding and hurricanes) experience greater financial instability due to elevated expected losses and higher social vulnerability, increasing the risk of wealth erosion and displacement.

## Vision
To support climate-informed, equity-focused policy decisions by revealing how climate hazards translate into household-level financial and wealth risk at the census tract scale.

## Objective
The primary objective of this analysis is to gain a comprehensive understanding of how climate-related hazards in South Florida expose households to financial instability and wealth risk at the census tract level. By integrating multiple federal datasets and examining the interaction between hazard exposure, expected losses, and social vulnerability, this report aims to address the following objectives:
* Visualize the spatial distribution of climate hazard exposure and floodplain overlap across South Florida census tracts to identify areas with heightened physical risk.
* Examine how social vulnerability varies across tracts with differing levels of climate hazard exposure, highlighting communities where limited adaptive capacity may amplify financial impacts.
* Assess expected annual losses as a proxy for household wealth risk, evaluating how financial exposure differs across tracts facing similar climate hazards.
* Identify census tracts where climate risk and social vulnerability intersect, highlighting priority areas for equitable climate adaptation, resilience planning, and policy intervention.

## Review of the Literature
The level of data science and machine learning talent within an organization positively correlates with the adoption of ML technologies. As highlighted in the LinkedIn article, the modern process industry is driven by big data, which includes vast amounts of structured and unstructured data posing significant challenges in efficient data interpretation and management. National AI adoption trends indicate that sectors with high current AI usage will maintain their lead, while sectors such as Accommodation and Food Services exhibit lower adoption rates. The BTOS AI findings, consistent with the 2019 Annual Business Survey (ABS), show that sectors with higher adoption rates have more established practices and experienced talent. In the EdTech industry, machine learning is revolutionizing learning experiences through adaptive learning systems, content recommendation systems, and predictive analytics, contributing to market growth projections by 2027. Despite these advancements, CompTIA identifies barriers to AI adoption, including a lack of skilled professionals, unclear ROI metrics, and the complexity of AI systems. Addressing these barriers through targeted strategies and education can facilitate wider AI and ML adoption, leading to enhanced efficiency and competitiveness in organizations. Consequently, fostering skilled talent within organizations is essential for driving successful ML and AI integration across various industries.

## Key Insights
* Across South Florida census tracts, flooding and hurricanes account for approximately 88% of total expected annual climate-related financial losses, confirming water-related hazards as the dominant driver of household financial risk in the region.

### Dashboard
![image](https://github.com/acsoteldo/Machine-Learning-Adoption-Across-Industries/assets/76544489/a5f8da18-98a8-490f-9fee-7e0dbdc8aece)

## Next Steps
* Design industry-specific workshops to highlight the benefits and applications of machine learning in various sectors.
* Organize events that promote collaboration and idea exchange among professionals to accelerate ML adoption within organizations.
* Provide training programs in machine learning to help professionals enhance their skills, stay current with industry trends, and boost their career prospects.
* Support regulations that encourage innovation while ensuring privacy, security, and fairness, fostering greater confidence in ML technologies.
* Continuously use dataset insights to update and improve the educational sessions, ensuring they remain relevant and effective.

## Contact
For any inquiries or feedback, please contact acsoteldo01@gmail.com.

## References
[^1]: Data Source: American Community Survey (ACS)
https://api.census.gov/data/key_signup.html

[^2]: Data Source: CDC Social Vulnerability Index (SVI)
https://svi.cdc.gov/dataDownloads/data-download.html

[^3]: Data Source: FEMA National Risk Index (NRI)
https://resilience.climate.gov/datasets/FEMA%3A%3Anational-risk-index-census-tracts/about

[^4]: Data Source: FEMA National Flood Hazard Layer (NFHL)
https://www.arcgis.com/home/item.html?id=2b245b7f816044d7a779a61a5844be23&sublayer=0 

[^5]: Data Source: NOAA Billion-Dollar Disasters
https://www.ncei.noaa.gov/access/metadata/landing-page/bin/iso?id=gov.noaa.nodc:0209268

[^6]: Data Source: Census Tiger
https://www.census.gov/geographies/mapping-files/time-series/geo/tiger-line-file.html
