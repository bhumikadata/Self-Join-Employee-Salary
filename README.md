# Identifying Employees with Higher Salary than Managers

In today's competitive job market, identifying and retaining top talent is crucial for the success of any organization. One key aspect of this is ensuring that employees are fairly compensated relative to their responsibilities and contributions. However, as organizations grow, it becomes increasingly challenging to monitor and manage salary discrepancies, especially between employees and their managers.

# Use Case

Consider a scenario where a company wants to ensure equitable compensation practices and identify instances where employees earn more than their managers. This could be indicative of either exceptional performance or potential discrepancies in salary structures.

# Problem

![Day 22](https://github.com/bhumikadata/Self-Join-Employee-Salary/assets/131578649/38519de7-1f2b-4e1f-8909-1b070e7def69)
 

# SQL Solution

To address this requirement, the following SQL query can be employed:

```sql
SELECT 
    e.emp_name AS emp_name,
    e.salary,
    e.joining_date,
    m.salary AS manager_salary,
    m.joining_date AS manager_joining_date
FROM 
    employee e
INNER JOIN 
    employee m ON e.manager_id = m.emp_id
WHERE 
    e.salary > m.salary
    AND e.joining_date > m.joining_date;
```

# Explanation

## SELECT Clause: 
The query selects relevant columns from the employee table, including the employee's name, salary, joining date, manager's salary, and manager's joining date.

## FROM Clause: 
It utilizes a self-join on the employee table, aliasing it as 'e' for the employee and 'm' for the manager.

## JOIN Clause: 
The join condition matches employees with their corresponding managers based on the manager_id and emp_id relationship.

## WHERE Clause: 
This clause filters the results to include only those cases where an employee's salary exceeds that of their manager and where the employee joined the company after the manager did.


# Benefits
This SQL query provides a powerful tool for HR departments and organizational leaders to identify potential discrepancies in salary structures. By promptly addressing such instances, companies can foster a culture of fairness, transparency, and employee satisfaction, ultimately contributing to higher levels of engagement and retention.

# Conclusion
In today's dynamic business environment, where talent retention and fair compensation are paramount, leveraging data-driven approaches such as this SQL query can enable organizations to make informed decisions and maintain a competitive edge in the market.

By implementing this SQL query, companies can proactively address salary discrepancies.
