# A/B Test Leaderboard: Automated Conversion Rate Uplift Ranking

👉 [Click here to view the live A/B Test Leaderboard](https://adamdandi.github.io/A-B-Test-Leaderboard_Automated-Conversion-Rate/leaderboard.html)

## Overview

This project focuses on the automated extraction and ranking of A/B test results from test report images.

It fits into the context of marketing and product experimentation. Teams run multiple A/B tests and need a fast and repeatable way to compare results.

The script conducts this analysis to help teams decide which product changes to prioritize. It ranks every A/B test by its conversion rate uplift from best to worst.

## Objectives

### Primary Goal

Extract A/B test data from 50 images and rank every test by the relative conversion rate uplift of its variant over its control.

### Specific Goals

- Extract the test name, traffic values, and conversion values from each image using OCR.
- Compute the control conversion rate, the variant conversion rate, and the relative uplift.
- Rank all 50 tests and export the results as a CSV file, a JSON file, and an HTML leaderboard.

**Data Source:** 50 image files. Each image shows one A/B test with a control group and a variant group.

**Success Criteria:** A ranked HTML leaderboard listing all 50 tests with their conversion rates and uplift values, along with structured data exports.

## Solution Approach

### Methodology

The script uses Optical Character Recognition (OCR) through EasyOCR to read text from each image. It then uses regular expressions to identify the required numbers. Finally, it uses pandas to calculate conversion metrics and generate the rankings.

### Key Steps

1. Locate all images in the input directory.
2. Run EasyOCR on each image to extract raw text.
3. Extract the test name and identify the traffic and conversion values.
4. Calculate the control conversion rate, variant conversion rate, and relative uplift.
5. Sort the tests by uplift score and save the output files.

### Tools Used

- Python
- EasyOCR
- pandas
- Regular expressions

### Rationale

EasyOCR performs well on clean digital images and does not require additional system-level installations, making the solution simple to deploy and easy to maintain.

## Expected Outcomes

- A single HTML leaderboard ranking all A/B tests by conversion rate uplift.
- Structured data exports in CSV and JSON formats.
- A repeatable and scalable code structure that can process future batches of similar A/B test images.
