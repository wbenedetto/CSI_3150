# CSI 3150: Assignment 1A

**Bryce Benedetto**  
**Professor Amartya Sen**  
**9-20-26**

## Section 1: The Less-than-equal-4-Click User Journey Funnel

- **Starting State:** User enters the webpage and sees a header with a high-contrast “Deploy Free Cluster” CTA, a navigation bar with landmark links, and a hero section with core value metrics.
- **Action 1:** User reviews the features section (containing Latency Tracking, Log Aggregation, and Auto-Remediation) and selects the navigation link to the pricing matrix section.
- **Action 2:** User compares the "Developer", "Pro Cluster", and "Enterprise Dedicated" tiers, noticing that the “Pro Cluster” tier is highlighted and denoted as the most popular. User selects their preferred tier card.
- **Action 3:** User inputs node count and log throughput into the workload estimator form to determine whether their preferred tier is compatible.
- **Action 4:** User completes and submits the pre-registration form to request API sandbox provisioning details.
- **Terminal State:** User receives visual feedback that their pre-registration form was submitted.

## Section 2: Don Norman Usability & Constraint Audit

| Norman Principle           | UI Component / Feature Context         | Specific HTML Element or Attribute Used to Enforce Principle                                                                                                                                                                                                               |
| -------------------------- | -------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Signifier                  | Primary Action Button (Above the fold) | `<a href="#register">Deploy Free Cluster</a>`                                                                                                                                                                                                                              |
| Signifier                  | Recommended Tier Indicator             | `<div>Most Popular</div>`                                                                                                                                                                                                                                                  |
| Physical/System Constraint | Workload Estimator: Node Count         | `<input type="number" name="node-count" id="node-count" min="100" max="10000" step="50" required />`                                                                                                                                                                       |
| Physical/System Constraint | Operator Contact Field                 | `<input type="email" name="operator-email" id="operator-email" required />`                                                                                                                                                                                                |
| Feedback Loop              | Form Submission / Live Anchors         | We can use anchor links where `href="#..."` to navigate the user to the corresponding sections. A native browser provides feedback when the user attempts to submit a form with invalid input (such as a string in a number input), or when a required field isn’t filled. |

## Section 3: Semantic Component & Layout Tree

- `index.html`
  - `<head>`
    - `<meta>`
    - `<link>`
  - `<body>`
    - `<header>`
      - `<a href="#hero">` DevPulse logo/home link
      - `<nav>`
        - `<a href="#features">` Features
        - `<a href="#pricing">` Pricing
        - `<a href="#calculator">` Workload Estimator
        - `<a href="#register">` Deploy Free Cluster
    - `<main>`
      - `<section id="hero">`
        - `<h1>` Cloud Infrastructure Made Easy
        - `<p>` Core Value Metrics
        - `<a href="#register">` Deploy Free Cluster
      - `<section id="features">`
        - `<header>`
          - `<h2>` Platform Capabilities
          - `<p>` Infrastructure Features Overview
        - `<div>`
          - `<article>`
            - `<h3>` Latency Tracking
            - `<p>` Latency Tracking Description
          - `<article>`
            - `<h3>` Log Aggregation
            - `<p>` Log Aggregation Description
          - `<article>`
            - `<h3>` Auto-Remediation
            - `<p>` Auto-Remediation Description
      - `<section id="pricing">`
        - `<header>`
          - `<h2>` Tier Comparison
          - `<p>` Tier Comparison Description
        - `<div>`
          - `<article>`
            - `<h3>` Developer
            - `<p>` Developer Description
            - `<p>` $49/Month
            - `<ul>`
              - `<li>` Feature #1
              - `<li>` Feature #2
              - `<li>` Feature #3
            - `<a href="#calculator">` Select Developer
          - `<article>`
            - `<div>` Most popular
            - `<h3>` Pro Cluster
            - `<p>` Pro Cluster Description
            - `<p>` $99/Month
            - `<ul>`
              - `<li>` Feature #1
              - `<li>` Feature #2
              - `<li>` Feature #3
            - `<a href="#calculator">` Select Pro Cluster
          - `<article>`
            - `<h3>` Enterprise Dedicated
            - `<p>` Enterprise Dedicated Description
            - `<p>` Custom
            - `<ul>`
              - `<li>` Feature #1
              - `<li>` Feature #2
              - `<li>` Feature #3
            - `<a href="#calculator">` Select Enterprise Dedicated
      - `<section id="calculator">`
        - `<header>`
          - `<h2>` Workload Estimator
          - `<p>` Workload Estimator Description
        - `<form action="#" method="post">`
          - `<label for="node-count">` Node Count
          - `<input type="number" name="node-count" id="node-count" min="100" max="10000" step="50" required>`
          - `<label for="log-throughput">` Log Throughput
          - `<input type="number" name="log-throughput" id="log-throughput" min="100" max="10000" step="50" required>`
          - `<label for="target-tier">` Tier Selection
          - `<select name="target-tier" id="target-tier" required>`
            - `<option value="developer">` Developer
            - `<option value="pro-cluster">` Pro Cluster
            - `<option value="enterprise-dedicated">` Enterprise Dedicated
          - `<button type="submit">` Verify Tier Compatibility
          - `<p>` Registration Submission Confirmation
        - `<p>` Tier Compatibility Result
      - `<section id="register">`
        - `<header>`
          - `<h2>` Request API Sandbox Access
          - `<p>` API Sandbox Provisioning Description
        - `<form action="#" method="post">`
          - `<label for="operator-name">` Operator Name
          - `<input type="text" name="operator-name" id="operator-name" required>`
          - `<label for="operator-email">` Operator Email
          - `<input type="email" name="operator-email" id="operator-email" required>`
          - `<button type="submit">` Request API Sandbox Provisioning Details
    - `<footer>`
      - `<p>` Copyright 2026 DevPulse Technologies Inc.
      - `<nav>`
        - `<a href="#hero">` Back to Top
        - `<a href="#features">` Features
        - `<a href="#pricing">` Pricing
        - `<a href="#calculator">` Workload Estimator

## System Requirements

- Core metrics reviewer
- Nav bar
- “Deploy Free Cluster” CTA (High contrast and easy to see)
- Application features (Latency Tracking, Log Aggregation, Auto-Remediation) in an organized fashion
- Pricing matrix for 3 tiers ("Developer", "Pro Cluster", "Enterprise Dedicated") with the most popular tier highlighted
- Verifier calculator (node count and log throughput inputs with numerical bounds) that verifies tier compatibility
- Registration form with required fields that provides API sandbox provisioning details
