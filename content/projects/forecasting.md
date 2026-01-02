---
title: "House Rental Revenue Index – Time Series Analysis & Forecasting" 
date: 2025-10-15
order: 2
show_date: false
url: /forecasting/
aliases: 
    - /forecasting.html
tags: []
author: "Yanis Stentzel, Academic Project @IUT2 Grenoble"
summary: "Comprehensive statistical analysis of the French housing rental revenue index (2010–2015). This project involves seasonal decomposition, trend modeling using linear regression, and short-term forecasting using the Holt-Winters method to predict market evolution."
cover:
    image: "/projects/house_rental.png#center"
    alt: "Time Series Analysis Graph"
    relative: true 

---

---

##### Abstract

This project focuses on the study of the **Revenue Index (ICA)** for the housing rental sector in France from January 2010 to December 2015. The analysis follows a rigorous statistical workflow:
1. **Decomposition**: Implementation of a multiplicative model to separate the trend from marked seasonal variations.
2. **Modeling**: The underlying trend was modeled using simple linear regression ($\hat{T}t = 71.40 + 0.356 \times t$), validated by a detailed residual analysis to ensure model reliability.
3. **Forecasting**: Comparison between parametric modeling and the **Holt-Winters** non-parametric method. The study concludes with a 2016 growth forecast, anticipating a peak index of approximately 126.85 by year-end.

---

##### Links

+ [Full Technical Report (in French)](/ReportHouseRental-YanisSTENTZEL.pdf)

---

##### Key Methodology

The project was developed as part of the **BUT Science des Données** (**Bachelor of Data Science**). It demonstrates proficiency in handling real-world economic indicators and applying advanced smoothing techniques.

* **Data Source**: INSEE (National Institute of Statistics and Economic Studies).
* **Software**: Fully conducted using **R** for data processing, decomposition, and visualization.