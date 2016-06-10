Employees Earning More Than Their Managers
==========================================
:date: 2016-06-07 20:40
:modified: 2016-06-07 20:40
:category: LeetCode
:tags: Database
:author: Bianchenglangzi
:summary: LeetCode Database 181

Problem Description
-------------------

The Employee table holds all employees including their managers. Every employee has an Id, and there is also a column for the manager Id.

.. table:: Employee Table

	+----+-------+--------+-----------+
	| Id | Name  | Salary | ManagerId |
	+----+-------+--------+-----------+
	| 1  | Joe   | 70000  | 3         |
	+----+-------+--------+-----------+
	| 2  | Henry | 80000  | 4         |
	+----+-------+--------+-----------+
	| 3  | Sam   | 60000  | NULL      |
	+----+-------+--------+-----------+
	| 4  | Max   | 90000  | NULL      |
	+----+-------+--------+-----------+


Given the Employee table, write a SQL query that finds out employees who earn more than their managers. For the above table, Joe is the only employee who earns more than his manager.

.. table:: Result

	+----------+
	| Employee |
	+----------+
	| Joe      |
	+----------+

Solution
--------
.. code:: sql
	:number-lines:

	select a.Name Employee
	from Employee a, Employee b
	where a.ManagerId = b.Id
	and a.Salary > b.Salary;
