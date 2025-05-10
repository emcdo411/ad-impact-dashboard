AdImpactDashboard

A dynamic Shiny dashboard analyzing the impact of US-China trade tensions on digital advertising, delivering actionable insights for ad professionals and executives.
Table of Contents

Summary
Features
Tech Stack
Installation
Usage
Code
Why This Matters
Conclusion

Summary
The AdImpactDashboard is a cutting-edge R Shiny application designed for digital advertising professionals and executive leadership navigating the complexities of geopolitical tensions, such as the US-China trade war. This dashboard visualizes critical trends—ad spend shifts, targeting strategy changes, and tariff impacts on big tech—empowering stakeholders to make data-driven decisions. For non-tech audiences, the intuitive interface and clear visualizations demystify market dynamics, while tech-savvy users benefit from robust data analysis powered by R’s ecosystem. Key insights include:

94% of ad leaders are concerned about tariff-driven budget cuts.
Chinese platforms (Shein, Temu) are outpacing US giants in ad- 25% ad spend shift to emerging markets in 2024.
Big tech strategies (Meta, Google, Apple) to counter revenue instability.

This tool bridges the gap between raw data and strategic action, making it indispensable for optimizing ad campaigns and forecasting revenue in turbulent times.
Features

Interactive Visualizations: Eight dynamic plots covering ad spend concerns, targeting shifts, and tariff impacts, built with ggplot2.
Responsive Design: Sleek, mobile-friendly UI with a cerulean theme and custom CSS for professional aesthetics.
Strategic Insights: Concise, square-shaped strategy cards highlighting Meta, Google, and Apple’s approaches to mitigate ad revenue risks.
User-Friendly: Intuitive tabbed interface for exploring data without technical expertise.
Hover Effects: Engaging UI with scaling and color-changing strategy cards for enhanced interactivity.

Tech Stack
The dashboard leverages a robust R ecosystem, ensuring powerful data processing and visualization:

🔵 shiny: Powers the interactive web application framework.
🟢 ggplot2: Creates high-quality, customizable data visualizations.
🟡 dplyr: Enables efficient data manipulation and transformation.
🔴 shinythemes: Provides a professional cerulean theme for the UI.
🟣 scales: Formats plot axes for clear percentage and dollar displays.
🟠 tidyr: Facilitates data tidying for pivot operations in visualizations.

Installation

Install R: Download and install R (version 4.4.1 or later).
Install Required Packages: Run the following in your R console:install.packages(c("shiny", "ggplot2", "dplyr", "shinythemes", "scales", "tidyr"))


Clone the Repository:git clone https://github.com/yourusername/AdImpactDashboard.git


Navigate to the Project Directory:cd AdImpactDashboard



Usage

Open R or RStudio.
Run the App:
Load the app.R file in RStudio and click Run App, or
Use the R console:shiny::runApp("app.R")




Explore the Dashboard:
View strategy cards for Meta, Google, and Apple.
Navigate tabs to analyze ad spend trends, tariff impacts, and more.
Hover over strategy cards for interactive effects.



The app will launch in your default web browser, providing a seamless experience.
Code
Below is the complete app.R code powering the AdImpactDashboard:
# Load necessary libraries
library(shiny)
library(ggplot2)
library(dplyr)
library(shinythemes)
library(scales)
library(tidyr)

# Define UI with custom CSS styling
ui <- fluidPage(
  theme = shinytheme("cerulean"),
  
  # Include custom CSS for styling
  tags$head(
    tags$style(HTML("
      body {
        background-color: #f4f6f9;
        font-family: 'Arial', sans-serif;
        color: #333333;
      }
      .container {
        max-width: 1200px;
        margin: auto;
        padding: 20px;
      }
      .navbar {
        background-color: #003366;
      }
      .navbar a {
        color: #ffffff !important;
        font-size: 18px;
      }
      .titlePanel h1 {
        font-size: 32px;
        font-weight: bold;
        color: #003366;
        margin-bottom: 20px;
      }
      .sidebarPanel {
        background-color: #f1f1f1;
        padding: 20px;
        border-radius: 8px;
      }
      .tabsetPanel {
        border: 2px solid #e1e1e1;
        padding: 10px;
        background-color: #ffffff;
        border-radius: 10px;
      }
      .nav-tabs {
        border-bottom: 2px solid #ddd;
      }
      .nav-item {
        margin-right: 10px;
      }
      .nav-link {
        color: #003366;
        font-weight: bold;
      }
      .nav-link.active {
        color: #ffffff;
        background-color: #003366;
        border-radius: 5px;
      }
      .plotOutput {
        background-color: #ffffff;
        border: 1px solid #e1e1e1;
        padding: 20px;
        border-radius: 10px;
      }
      .btn {
        background-color: #003366;
        color: #ffffff;
        font-size: 14px;
        padding: 10px 20px;
        border-radius: 5px;
      }
      .btn:hover {
        background-color: #004C99;
        color: #ffffff;
      }
      .dashboard-bullets {
        background-color: #ffffff;
        border: 1px solid #e1e1e1;
        padding: 20px;
        border-radius: 10px;
        margin-bottom: 20px;
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 15px;
      }
      .strategy-square {
        background-color: #f1f1f1;
        width: 200px;
        height: 200px;
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        padding: 15px;
        border-radius: 8px;
        box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        transition: transform 0.2s ease-in-out, background-color 0.2s ease-in-out;
        font-size: 14px;
        color: #333333;
        line-height: 1.5;
      }
      .strategy-square:hover {
        transform: scale(1.05);
        background-color: #e6e6e6;
        cursor: pointer;
      }
      @media (max-width: 768px) {
        .container {
          padding: 10px;
        }
        .navbar a {
          font-size: 16px;
        }
        .plotOutput {
          padding: 10px;
        }
        .dashboard-bullets {
          grid-template-columns: 1fr;
        }
        .strategy-square {
          width: 100%;
          height: 150px;
          font-size: 12px;
        }
      }
    "))
  ),
  
  # Main Content
  div(class = "container",
      titlePanel("Impact of Geopolitical Tensions on Digital Advertising"),
      
      # Dashboard Bullet Points (Updated to Squares)
      div(class = "dashboard-bullets",
          h3("Key Strategies to Mitigate Ad Revenue Instability"),
          div(class = "strategy-square", "Meta: Boosted AI ($64–$72B, 2025) to improve ad performance."),
          div(class = "strategy-square", "Google: Diversified ads (Search, YouTube, Cloud), Q1 2025 up 8.5% to $66.8B."),
          div(class = "strategy-square", "Apple: Moved manufacturing to India, Vietnam to cut tariff costs, boost App Store ads.")
      ),
      
      sidebarLayout(
        sidebarPanel(
          class = "sidebarPanel",
          h3("Data Visualizations"),
          p("This app shows the impact of the US-China trade war on digital advertising, including shifts in budgets, targeting strategies, and more.")
        ),
        
        mainPanel(
          class = "tabsetPanel",
          tabsetPanel(
            tabPanel("Ad Spend Concerns", plotOutput("budgetPlot")),
            tabPanel("Ad Targeting Changes", plotOutput("targetingPlot")),
            tabPanel("Chinese vs US Ad Spend", plotOutput("adSpendPlot")),
            tabPanel("Projected Ad Revenue Growth", plotOutput("revenuePlot")),
            tabPanel("Smaller vs Larger Platforms", plotOutput("platformPlot")),
            tabPanel("Big Tech Earnings", plotOutput("bigTechPlot")),
            tabPanel("Tariff Impact on Big Tech", plotOutput("tariffImpactPlot")),
            tabPanel("Ad Spend Cuts Post-Tariffs", plotOutput("adSpendCutsPlot"))
          )
        )
      )
  )
)

# Define Server logic
server <- function(input, output) {
  
  # Plot for Shifts in Advertising Budget Allocations
  output$budgetPlot <- renderPlot({
    data_budget <- data.frame(
      concern = c("Concerned", "Not Concerned"),
      percentage = c(94, 6)
    )
    
    ggplot(data_budget, aes(x = concern, y = percentage, fill = concern)) +
      geom_bar(stat = "identity", show.legend = FALSE) +
      labs(title = "Concerns Over Impact of Tariffs on Ad Spend", x = "Concern", y = "Percentage (%)") +
      scale_y_continuous(labels = scales::percent_format(scale = 1)) +
      scale_fill_manual(values = c("Concerned" = "#4B4B4D", "Not Concerned" = "#D1D0CE")) +
      theme_minimal() +
      theme(plot.title = element_text(size = 14, face = "bold", color = "#003366"),
            axis.title = element_text(size = 12, face = "bold"),
            axis.text = element_text(size = 10))
  })
  
  # Plot for Changes in Ad Targeting Strategies
  output$targetingPlot <- renderPlot({
    data_targeting <- data.frame(
      region = c("US", "Emerging Markets"),
      ad_spend_2023 = c(0.85, 0.15),
      ad_spend_2024 = c(0.75, 0.25)
    )
    
    data_long <- data_targeting %>%
      tidyr::pivot_longer(cols = c(ad_spend_2023, ad_spend_2024), 
                          names_to = "Year", values_to = "Ad_Spend") %>%
      mutate(Year = recode(Year, "ad_spend_2023" = "2023", "ad_spend_2024" = "2024"))
    
    ggplot(data_long, aes(x = region, y = Ad_Spend, fill = Year)) +
      geom_bar(stat = "identity", position = "dodge") +
      labs(title = "Changes in Ad Spend by Region: US vs Emerging Markets", 
           x = "Region", y = "Ad Spend Percentage") +
      scale_y_continuous(labels = scales::percent_format(scale = 1)) +
      scale_fill_manual(values = c("2023" = "#6D6A5E", "2024" = "#BDB6A4")) +
      theme_minimal() +
      theme(plot.title = element_text(size = 14, face = "bold", color = "#003366"),
            axis.title = element_text(size = 12, face = "bold"),
            axis.text = element_text(size = 10))
  })
  
  # Plot for Chinese vs US Ad Spend
  output$adSpendPlot <- renderPlot({
    data_chinese_ad_spend <- data.frame(
      company = c("Shein", "Temu", "Meta", "Amazon"),
      ad_spend_increase = c(0.85, 0.80, 0.16, 0.19)
    )
    
    ggplot(data_chinese_ad_spend, aes(x = company, y = ad_spend_increase, fill = company)) +
      geom_bar(stat = "identity") +
      labs(title = "Ad Spend Increase: Chinese E-Commerce vs US Tech Giants", 
           x = "Company", y = "Ad Spend Increase (%)") +
      scale_y_continuous(labels = scales::percent_format(scale = 1)) +
      scale_fill_manual(values = c("#4B4B4D", "#6D6A5E", "#BDB6A4", "#D1D0CE")) +
      theme_minimal() +
      theme(plot.title = element_text(size = 14, face = "bold", color = "#003366"),
            axis.title = element_text(size = 12, face = "bold"),
            axis.text = element_text(size = 10))
  })
  
  # Plot for Projected Ad Revenue Growth
  output$revenuePlot <- renderPlot({
    data_ad_revenue <- data.frame(
      Period = c("Pre-Tariff (Initial)", "Post-Tariff (Mar 2025)"),
      Madison_Wall = c(4.5, 3.6),
      MAGNA = c(7.3, 6.3)
    )
    
    data_long <- data_ad_revenue %>%
      tidyr::pivot_longer(cols = c(Madison_Wall, MAGNA), 
                          names_to = "Source", values_to = "Growth")
    
    ggplot(data_long, aes(x = Period, y = Growth, color = Source, group = Source)) +
      geom_line(size = 1.5) +
      geom_point(size = 3) +
      labs(title = "Impact of Tariffs on US Ad Spend Growth Projections", 
           x = "Period", y = "Ad Spend Growth (%)") +
      scale_y_continuous(labels = scales::percent_format(scale = 1)) +
      scale_color_manual(values = c("Madison_Wall" = "#4B4B4D", "MAGNA" = "#6D6A5E")) +
      theme_minimal() +
      theme(plot.title = element_text(size = 14, face = "bold", color = "#003366"),
            axis.title = element_text(size = 12, face = "bold"),
            axis.text = element_text(size = 10))
  })
  
  # Plot for Smaller vs Larger Platforms
  output$platformPlot <- renderPlot({
    data_smaller_vs_larger <- data.frame(
      company = c("Snap", "Pinterest", "Meta", "Google"),
      revenue_growth = c(0.12, 0.10, 0.16, 0.09)
    )
    
    ggplot(data_smaller_vs_larger, aes(x = company, y = revenue_growth, fill = company)) +
      geom_bar(stat = "identity") +
      labs(title = "Ad Revenue Growth: Smaller vs Larger Platforms", 
           x = "Company", y = "Revenue Growth (%)") +
      scale_y_continuous(labels = scales::percent_format(scale = 1)) +
      scale_fill_manual(values = c("#4B4B4D", "#6D6A5E", "#BDB6A4", "#D1D0CE")) +
      theme_minimal() +
      theme(plot.title = element_text(size = 14, face = "bold", color = "#003366"),
            axis.title = element_text(size = 12, face = "bold"),
            axis.text = element_text(size = 10))
  })
  
  # Plot for Big Tech Earnings
  output$bigTechPlot <- renderPlot({
    big_tech_data <- data.frame(
      company = c("Alphabet", "Amazon", "Meta", "Microsoft", "Apple"),
      earnings = c(100, 95, 85, 110, 65)
    )
    
    ggplot(big_tech_data, aes(x = company, y = earnings, fill = company)) +
      geom_bar(stat = "identity", show.legend = FALSE) +
      labs(title = "Big Tech Earnings (in billions)", 
           x = "Company", y = "Earnings (Billion $)") +
      scale_y_continuous(labels = scales::dollar_format(prefix = "$")) +
      scale_fill_manual(values = c("#4B4B4D", "#6D6A5E", "#BDB6A4", "#D1D0CE", "#8B8A7E")) +
      theme_minimal() +
      theme(plot.title = element_text(size = 14, face = "bold", color = "#003366"),
            axis.title = element_text(size = 12, face = "bold"),
            axis.text = element_text(size = 10))
  })
  
  # Plot for Tariff Impact on Big Tech Companies
  output$tariffImpactPlot <- renderPlot({
    tariff_impact_data <- data.frame(
      company = c("Alphabet", "Amazon", "Meta", "Microsoft", "Apple"),
      tariff_impact = c(0.05, 0.02, 0.03, 0.01, 0.15)
    )
    
    ggplot(tariff_impact_data, aes(x = company, y = tariff_impact, fill = company)) +
      geom_bar(stat = "identity", show.legend = FALSE) +
      labs(title = "Tariff Impact on Big Tech Companies (Earnings Reduction)", 
           x = "Company", y = "Impact (%)") +
      scale_y_continuous(labels = scales::percent_format(scale = 1)) +
      scale_fill_manual(values = c("#4B4B4D", "#6D6A5E", "#BDB6A4", "#D1D0CE", "#8B8A7E")) +
      theme_minimal() +
      theme(plot.title = element_text(size = 14, face = "bold", color = "#003366"),
            axis.title = element_text(size = 12, face = "bold"),
            axis.text = element_text(size = 10))
  })
  
  # Plot for Ad Spend Cuts Post-Tariffs (updated with Q2 2025 projections)
  output$adSpendCutsPlot <- renderPlot({
    data_ad_spend_cuts <- data.frame(
      Period = c("Pre-Tariff (Initial)", "Post-Tariff (Mar 2025)", "Q2 2025 (Projected)"),
      Madison_Wall = c(4.5, 3.6, 3.0),  # Further 0.6% cut
      MAGNA = c(7.3, 6.3, 5.5)          # Further 0.8% cut
    )
    
    data_long <- data_ad_spend_cuts %>%
      tidyr::pivot_longer(cols = c(Madison_Wall, MAGNA), 
                          names_to = "Source", values_to = "Growth")
    
    ggplot(data_long, aes(x = Period, y = Growth, color = Source, group = Source)) +
      geom_line(size = 1.5) +
      geom_point(size = 3) +
      labs(title = "US Ad Spend Growth Projections Post-Tariffs", 
           x = "Period", y = "Ad Spend Growth (%)") +
      scale_y_continuous(labels = scales::percent_format(scale = 1)) +
      scale_color_manual(values = c("Madison_Wall" = "#4B4B4D", "MAGNA" = "#6D6A5E")) +
      theme_minimal() +
      theme(plot.title = element_text(size = 14, face = "bold", color = "#003366"),
            axis.title = element_text(size = 12, face = "bold"),
            axis.text = element_text(size = 10))
  })
}

# Run the application
shinyApp(ui = ui, server = server)

Why This Matters
In an era of escalating geopolitical tensions, such as the US-China trade war, the digital advertising landscape is undergoing seismic shifts. The AdImpactDashboard matters because it equips ad professionals and executives with the tools to:

Anticipate Budget Cuts: With 94% of ad leaders concerned about tariffs and 62% of CFOs planning spend reductions by Q2 2025, this dashboard forecasts revenue impacts and growth projections.
Optimize Targeting: As 25% of ad spend shifts to emerging markets, the app highlights actionable strategies to reallocate budgets effectively.
Learn from Big Tech: By showcasing how Meta ($64–$72B AI investment), Google (8.5% ad revenue growth), and Apple (manufacturing diversification) adapt, the dashboard provides a playbook for resilience.
Stay Ahead of Competitors: Insights into Chinese platforms (Shein, Temu) outpacing US giants empower stakeholders to adjust campaigns and capture market share.

For non-tech executives, the dashboard’s intuitive visuals and concise strategy cards translate complex data into clear decisions. For tech-savvy professionals, the robust R-based analysis offers depth and precision, making it a critical asset for navigating economic uncertainty.
Conclusion
The AdImpactDashboard is more than a tool—it’s a strategic advantage for digital advertising leaders facing geopolitical disruption. By blending advanced data visualization with user-friendly design, it empowers both tech and non-tech audiences to turn insights into action. Whether you’re optimizing ad spend, forecasting revenue, or learning from industry giants, this dashboard is your guide to thriving in a volatile market.

License: MIT
Contribute: Feel free to fork, submit issues, or contribute to the repository. Let’s build smarter solutions for digital advertising together!
Contact: Connect with me on LinkedIn or email at your.email@example.com.
