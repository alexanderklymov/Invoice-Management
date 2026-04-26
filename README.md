Online Invoicing System

Overview
This document describes the business requirements for an online invoicing system used by Company XYZ to manage employee invoices.

Domain Entities
Employee

Identified by first name, last name, and a unique employee identifier
Has one active contract at any given time
Can submit invoices to get paid

Contract

Belongs to a single employee
Has a validity period defined as a date range (start date – end date)
Defines the employee's daily pay rate
Cannot overlap with another contract for the same employee
An employee receives a new contract once the previous one expires

Invoice

Submitted by an employee
Specifies:

Invoicing period (date range)
Number of days worked
Total amount invoiced


Invoice Manager

A designated employee with elevated access
Responsible for managing the invoicing system


Business Rules
IDRuleR1The system manages invoices for Company XYZ employees.R2Invoice managers are employees with designated access.R3Each employee is identified by first name, last name, and a unique employee ID.R4Every employee has a contract with a validity period (date range). The contract is only valid within that period.R5Each contract defines a daily pay rate. An employee may not have more than one valid contract at a time — validity periods must not overlap.R6Invoices specify the invoicing period (date range), number of full days worked, and total amount. Only full days are allowed (no fractions).R7The system only accepts invoices where the employee has a valid contract covering the entire invoicing period.R8The number of days invoiced must not exceed the number of days in the invoicing period. All days (including weekends and holidays) are billable.R9The total amount invoiced must equal daily rate × number of days worked. Any other amount is rejected.R10An employee may only submit one invoice per billing period. A new invoice must not overlap — fully or partially — with any existing invoice from the same employee.

Validation Summary
Before accepting an invoice, the system performs the following checks:

Contract validity — the employee has a contract valid for the entire invoicing period (R7)
Days worked — the number of days does not exceed the length of the invoicing period (R8)
Amount correctness — total amount equals daily rate × days worked (R9)
No duplicate invoices — no existing invoice from the same employee overlaps with the new invoicing period (R10)
