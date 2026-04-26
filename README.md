REQUIREMENTS
R1. Company XYZ needs an online invoicing system to manage the invoices of its employees.
R2. The company&#39;s invoicing system is managed by designated invoice managers who are also employees of
the company.
R3. An employee is identified by their first and last name as well as with a unique employee identifier.
R4. Every employee has a contract and each contract has a validity period specified as a date range. The
contract is not valid outside of the specified validity period.
R5. Every employee&#39;s daily pay rate is defined in their contract. Once their contract ends, an employee is given
a new contract with a new validity period. An employee cannot have more than one valid contract at a time –
validity periods of two contracts for the same employee should not overlap.
R6. Every employee submits invoices in order to get paid. The invoice specifies the invoicing period as a date
range, the number of days worked during the period, as well as the total amount invoiced. For simplicity, let&#39;s
assume that every employee only works full days and not fractions.
R7. The system accepts only invoices from employees with a contract which is valid for the entire invoicing
period. I.e. if the invoicing period specified in the invoice is from March 5 until March 27, the employee must have
a contract with a start date of at least March 5 and an end date on or after March 27.
R8. The system should also check whether the number of days invoiced fits within the invoice period. If the
invoice specifies 30 days worked while the invoice period is from March 5 until March 27, this should fail the
validation test. For simplicity, let’s assume that all days in the invoice period are billable at the same rate
including weekends and holidays. No special treatment for weekends or holidays is necessary.
R9. The system must also validate the total amount invoiced against the daily rate specified in the employee&#39;s
contract matching the invoice period. If the daily rate in the contract is USD 100 and the number of days
invoiced is 10, the system should not accept an invoice for an amount other than USD 1000.
R10. An employee can submit only one invoice in any billing period. Before accepting an invoice, the system
must check that no other invoice was already submitted by that employee, overlapping fully or partially with the
invoicing period of this invoice.
IMPORTANT As a general rule, you are not required to cater for all possible scenarios and complications a real-
life invoicing system may need to handle. Make sure that your code validates only against the rules specifically
described above and don&#39;t worry about edge cases and other possible real-life scenarios which you may think of
that are not explicitly mentioned above. This test is not about billing, but about software development and
architecture.
