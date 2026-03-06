## Home Possessions CFA (PISA 2022)

This project evaluates the factor structure of the **home possessions component** of the OECD Programme for International Student Assessment (PISA) **Economic, Social, and Cultural Status (ESCS)** index using data from the **2022 PISA U.S. sample (n ≈ 4,552)**.

The ESCS index is a widely used proxy for socioeconomic status in international education research and includes measures of **parental education, parental occupational status, and household possessions**. Prior research has raised concerns regarding the **validity, reliability, and cross-national comparability** of the home possessions component of ESCS. In response, the OECD revised the ESCS index in the 2022 PISA administration by introducing more **polytomous response items and updated indicators of household resources**.

### Research Objective

The goal of this analysis is to test whether the **hypothesized three-factor structure** of the PISA home possessions index is supported in the United States sample.

The proposed factors include:

- **Household items** (e.g., material resources available in the home)
- **Digital resources** (e.g., computers and other digital devices)
- **Books in the home**

### Data

Data are drawn from the **PISA 2022 U.S. public-use dataset**. The home possessions scale includes **30 survey items** spanning three domains:

- Household possessions
- Digital devices
- Number of books in the home

### Data Processing

The script performs several preprocessing steps prior to model estimation:

- Removes `haven` variable labels by exporting and re-importing the dataset as `.csv`
- Selects only the variables used in the confirmatory factor analysis
- Recodes binary items into **0/1 indicators**
- Recodes polytomous items so that response scales begin at **0**
- Renames variables to create a cleaner and more interpretable dataset
- Constructs a final analysis dataset containing all items used in the factor model

### Analysis

The factor structure is evaluated using **Confirmatory Factor Analysis (CFA)** implemented in the `lavaan` package in R.

Model fit is assessed using multiple fit indices, including:

- Chi-square test
- Akaike Information Criterion (AIC)
- Bayesian Information Criterion (BIC)
- Root Mean Square Error of Approximation (RMSEA)
- Standardized Root Mean Square Residual (SRMR)
- Comparative Fit Index (CFI)
- Tucker-Lewis Index (TLI)

Model evaluation follows a **holistic approach**, considering the collective evidence from multiple fit statistics rather than relying on any single index.

### Output

The final dataset contains recoded and renamed variables for all home possession items and is used as the input for the CFA model testing the three-factor structure.