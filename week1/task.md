# Problem statement
Imagine you are managing a store, and you want to calculate the total salary of your employees based on their sales performance. Each employee's salary is determined by different rules based on their sales.

# Assumptions
1. Each employee has a fixed base salary of KSh1000.
2. If an employee's total sales are less than Ksh500, they receive no bonus.
3. If an employee's total sales are between Ksh500 and Ksh1000 (inclusive), they receive a 5% bonus on their total sales.
4. If an employee's total sales are between Ksh1000 and KSh2000 (inclusive), they receive a 10% bonus on their total sales.
5. If an employee's total sales are more than Ksh2000, they receive a 15% bonus on their total sales.

# Steps
1. Random Sales Data: Generate random sales data for employees using RANDBETWEEN().
2. Calculate Bonus: Use nested IF() functions to calculate the bonus based on sales.
3. Calculate Total Salary: Use SUM() to calculate the total salary including the base salary and bonus for each employee.
4. Count Employees with Bonus: Use COUNTIF() to count the number of employees who received a bonus.

**example spreadsheet**

| Employee   | Total Sales                   | Bonus                                                      | Base Salary | Total Salary                |
|------------|--------------------------------|-------------------------------------------------------------|-------------|-----------------------------|
| Levi | =RANDBETWEEN(0, 3000)         | =IF(B2<500, 0, IF(B2<=1000, B2\*0.05, IF(B2<=2000, B2\*0.1, B2\*0.15))) | $1000       | =SUM(C2+D2)                 |
| Mukuha | =RANDBETWEEN(0, 3000)         | =IF(B3<500, 0, IF(B3<=1000, B3\*0.05, IF(B3<=2000, B3\*0.1, B3\*0.15))) | $1000       | =SUM(C3+D3)                 |
| ...        | ...                            | ...                                                         | ...         | ...                         |
| Kinungi | =RANDBETWEEN(0, 3000)         | =IF(BN<500, 0, IF(BN<=1000, BN\*0.05, IF(BN<=2000, BN\*0.1, BN\*0.15))) | $1000       | =SUM(CN+DN)                 |
|            | =COUNTIF(C2:CN, ">=0")         |                                                             |             |                             |
