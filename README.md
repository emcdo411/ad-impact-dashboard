# AdImpactDashboard

A dynamic Shiny dashboard analyzing the impact of US-China trade tensions on digital advertising, delivering actionable insights for ad professionals and executives.

---

## Table of Contents

* [Summary](#summary)
* [Features](#features)
* [Tech Stack](#tech-stack)
* [Installation](#installation)
* [Usage](#usage)
* [Code](#code)
* [Why This Matters](#why-this-matters)
* [Conclusion](#conclusion)

---

## Summary

**AdImpactDashboard** is a cutting-edge R Shiny application built for digital advertising professionals and executives navigating geopolitical complexities, such as the US-China trade war. It visualizes critical trends—like ad spend shifts, targeting strategy changes, and tariff impacts—empowering stakeholders to make informed decisions.

**Key insights:**

* 🚨 *94% of ad leaders are concerned about tariff-driven budget cuts.*
* 🇨🇳 *Chinese platforms (Shein, Temu) are outpacing US giants, with a 25% ad spend shift to emerging markets in 2024.*
* 💼 *Big tech (Meta, Google, Apple) are pivoting strategies to counter revenue instability.*

This tool bridges the gap between raw data and strategic action, making it indispensable for optimizing ad campaigns and forecasting revenue in turbulent times.

---

## Features

* 📊 **Interactive Visualizations:** Eight dynamic plots covering ad spend, targeting shifts, and tariff impacts.
* 📱 **Responsive Design:** Mobile-friendly UI with a cerulean theme and custom CSS for a sleek, professional look.
* 📝 **Strategic Insights:** Square-shaped strategy cards spotlighting Meta, Google, and Apple’s approaches.
* 🧭 **User-Friendly:** Intuitive tabbed interface for seamless exploration.
* ✨ **Hover Effects:** Engaging cards that scale and change color for better interactivity.

---

## Tech Stack

The dashboard leverages a powerful R ecosystem for data processing and visualization:

* 🔵 **shiny:** Powers the interactive web app framework.
* 🟢 **ggplot2:** Builds high-quality, customizable visualizations.
* 🟡 **dplyr:** Enables fast data wrangling and transformations.
* 🟣 **shinythemes:** Applies professional themes (cerulean) to the UI.
* 🟠 **scales:** Formats plot axes with percentages and dollar displays.
* 🔴 **tidyr:** Makes data tidy for smooth pivot operations in plots.

---

## Installation

1️⃣ **Install R:** Download and install [R (version 4.4.1+)](https://cran.r-project.org/).

2️⃣ **Install Required Packages:**

```R
install.packages(c("shiny", "ggplot2", "dplyr", "shinythemes", "scales", "tidyr"))
```

3️⃣ **Clone the Repository:**

```bash
git clone https://github.com/yourusername/AdImpactDashboard.git
```

4️⃣ **Navigate to the Project Directory:**

```bash
cd AdImpactDashboard
```

---

## Usage

1️⃣ Open **R** or **RStudio**.

2️⃣ Run the App:

* **Option 1:** Load `app.R` in RStudio and click ▶️ *Run App*.
* **Option 2:** In the R console:

```R
shiny::runApp("app.R")
```

3️⃣ **Explore the Dashboard:**

* View strategy cards for Meta, Google, and Apple.
* Navigate tabs to analyze ad spend trends, tariff impacts, and more.
* Hover over cards for interactive effects.

The app will launch in your default web browser.

---

## Code

*(Your full app.R code remains unchanged here—no edits necessary unless requested.)*

---

## Why This Matters

In an era of escalating geopolitical tensions, such as the US-China trade war, the digital advertising landscape is rapidly evolving. **AdImpactDashboard** equips ad professionals and executives with tools to:

* 🔎 **Anticipate Budget Cuts:** Identify risks early, with 94% of leaders voicing concerns over tariffs.
* 🌎 **Monitor Market Shifts:** Track how ad spend pivots toward emerging markets.
* 🧠 **Stay Ahead:** Learn from big tech’s strategic pivots (e.g., Meta’s AI surge, Apple’s manufacturing moves).

---

## Conclusion

The **AdImpactDashboard** is your go-to tool for understanding and responding to global ad market disruptions. Whether you're a CMO or a data analyst, this dashboard turns uncertainty into actionable intelligence.

---

Let me know if you want to add badges (e.g., for R version, license), screenshots, or additional formatting tweaks! 🚀


