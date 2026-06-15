---
title: "Healthcare Supply in France: Multivariate Analysis"
description: "Development of an interactive R Shiny dashboard to analyze and report territorial disparities in French healthcare using multivariate statistics (CA, HAC). Repository available on [GitHub](https://github.com/yanisstentzel/academicprojects/tree/main/Statistics%3AReport/SAE-Reporting)."
date: 2026-03-27
tags: ["R", "Shiny", "Data Analysis", "Multivariate Statistics", "Leaflet", "FactoMineR"]
categories: ["Academic Projects"]
weight: 3
showToc: true
TocOpen: false


---

## Context
This project was carried out as part of the SAÉ 4.02 module (Reporting of a multivariate analysis) during my Bachelor of Technology (BUT) in Data Science. Working alongside my classmates Adil Boukhari, Nessrine Rezgui, and Jonathan Wild, the objective was to design an automated reporting tool to present the results of an exploratory data analysis. 

The core problematic focused on open data regarding healthcare professionals and pathologies: *Can we highlight territorial inequalities in access to healthcare based on available indicators, and is it possible to identify typical territorial profiles?*

➔ **[View the complete repository and R code on GitHub](https://github.com/yanisstentzel/academicprojects/tree/main/Statistics%3AReport/SAE-Reporting)**

![Healthcare Dashboard Preview](/projects/SAE-Reporting.png)

## Statistical Methodology
To answer the problematic, we applied a complete exploratory data analysis workflow :
- **Correspondence Analysis (CA / AFC):** We analyzed the distribution of medical professions and pathologies across French departments. For professions, the first axis explained 69.1% of the total inertia and was heavily structured by General Medicine. For pathologies, the first axis explained 43.46% of the inertia, strongly driven by Endocrinology and Infectious Diseases.
- **Clustering (HAC & K-Means):** We used Hierarchical Agglomerative Clustering (CAH) and Partitioning Around Medoids (PAM) to group departments into distinct clusters (e.g., $k=3$ for professions and $k=4$ for pathologies). This clustering helped us highlight stark contrasts, showing that some rural departments appear medically "empty" compared to highly populated urban ones.

## The R Shiny Application
Instead of a static written report, the final deliverable was a user-friendly, interactive R Shiny application that guides the user through the data and the statistical findings. 

Key features of the dashboard include:
- **Interactive Cartography:** Integration of `leaflet` to display choropleth maps of France (including overseas territories/DOM), visualizing the workforce and density (per 100k inhabitants) of various medical specialties and pathologies.
- **Dynamic Filtering:** Users can filter data either by specific detail (e.g., a specific ALD or profession) or by broader, aggregated groups to simplify readability.
- **Real-Time Analysis Tab:** A dedicated section where users can trigger Correspondence Analysis (CA) or Hierarchical Clustering (HAC) on the fly, dynamically adjusting parameters like the number of clusters ($k$) through a slider. The app automatically generates the corresponding dendrograms, PCA projections, and class profiles.
- **Synthesis & Quality Control:** Automated generation of "Top N" charts (using `ggplot2`) for categories and departments, alongside a data quality panel checking for missing values and duplicates.

## Technologies Used
- **Language:** R[cite: 8]
- **Web Framework:** `shiny`, `shinymaterial` (for UI design)
- **Data Manipulation:** `dplyr`, `readr`
- **Multivariate Statistics:** `FactoMineR` (for CA/AFC), `stats` (for HAC)
- **Data Visualization:** `ggplot2`, `leaflet` (interactive mapping)
- **Spatial Data:** `sf`, `terra`