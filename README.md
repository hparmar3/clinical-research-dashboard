# Guide Effort Tool
This folder contains the <b> Guide Effort Tool </b>, an interactive Shiny Flexdashboard application that imports, processess, and visualizes clinical guide participation data across multiple studies.

## Overview
This tool is built as a single R Markdown file that renders into a flexdashboard and uses <b> Shiny </b> runtime to create a responsive and dynamic interface.

This dashboard enables researchers and coordinators to explore and summarize data about clinical and secondary guide across multiple participant visits and studies.

## Major Sections
The R Markdown files is organized into several sections:
|Section|Description|
|------|-----------|
|<b> import_surveys </b>|Set up the environment. Loads required packages, imports local Excel logs, and retrieves clinical study data directly from REDCap via API. Includes a utility function to download REDCap data fro each study.|
|<b> clean_imported_surveys </b>| Cleans and standardizes data. Formats dates, assigns study phases, filters incomplete records, harmonizes variables, and exports cleaned datasets as CSVs.|
|<b> combines_studies </b>| Defines a helper function to extract and label relevant guide data from multiple cleaned studies and combines them into one unified data set for further analysis.|
|<b> guide_effort_table </b>| Maps event names to visit numbers, aggregates guide data by participant and study, estimates key study dates, merges with the guide log, and standardizes guide names.|
|<b> guide_summary </b>| Creates two summary table: one (`guide_summary_part1`) that aggregates visits and total hours per guide, and one (`guide_summary_part2`) that summarizes participant progress and compeletion rates per guide.|
|<b> display </b>| Creates the Shiny app UI and server logic. Filters options on the left, displays data tables and summary statistics on the right. Dynamically updates based on user inputs.|

## Adding or Updating Studies
This code contains sections marked with `***"CODE DEPENDENT ON STUDIES"***`.

If new studies are added:
- Search for `"CODE DEPENDENT ON STUDIES"` in the file
- Modify the listed study identifiers and associated mappings accordingly

## Built With
- R
- Shiny
- Flexdashboard
- Tidyverse
- DT
