## System Objectives: 
Digitize Operations – Replace manual, paper-based processes with an automated platform.
Centralized Management – Provide one dashboard to manage tenants, rooms, and payments.
Improve Efficiency – Automate notifications, payment tracking, and reporting to save time.
Financial Insights – Provide filtering, charts, and reports for better financial analysis.
Data Security – Ensure tenant and financial data is encrypted and protected.
Decision Support – Help landlords plan and monitor long-term boarding house performance.

## System Scope:
The system will cover:
Tenant Management – Add, update, and track tenant information.
Room Management – Assign, manage, and monitor available/occupied rooms.
Payment Management – Record payments, send reminders, and track dues/overdues.
Financial Reports – Generate monthly, quarterly, and yearly reports.
Data Visualization – Charts for tenant distribution and financial performance.
Notifications – Automated email reminders for upcoming and overdue payments.
Security – Authentication (Laravel Breeze), encryption, and role-based access.

Stakeholder: Minsu Dormitory and Tejada's Boarding House

Tools/Technologies: Laravel, PHP, Laragon


## Integration Pattern
**Hub-and-Spoke

## Rationale
The Hub-and-Spoke pattern ensures all data in BoardEase travels through a single Integration Hub. When a Landlord creates or updates house information, the data flows to the Integration Hub, which routes it to House Management and then to Room Management for room updates. Tenants submit personal details or rent payments through the hub. Tenant profiles are sent to Tenant Management, while payments go to Payment Processing. After a successful payment, the hub triggers a Notification Request to the Email Notifications module, which uses the Google Email API to send receipts and reminders. The hub simultaneously forwards transaction details to Reporting/Analytics for inclusion in monthly and annual reports. Room and house updates also travel through the hub to keep all modules synchronized. Because every connection passes through the Integration Hub, modules remain decoupled and easy to scale or replace.