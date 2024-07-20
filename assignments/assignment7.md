# Assignment 7:

Using Employee Database above perform the following queries

### Task Overview

Schema Reference
Dept: deptno, dname, loc
Emp: empno, ename, job, mgr, hiredate, sal, comm, deptno

## Questions and commands

### a Determine the names of employee, who earn more than their managers.

- SELECT e1.ename AS employee_name
  -> FROM Emp e1
  -> JOIN Emp e2 ON e1.mgr = e2.empno
  -> WHERE e1.sal > e2.sal;

### b Determine the names of employees, who take highest salary in their departments.

- SELECT e.ename AS employee_name
  -> FROM Emp e
  -> JOIN (
  -> SELECT deptno, MAX(sal) AS max_salary
  -> FROM Emp
  -> GROUP BY deptno
  -> ) dept_max
  -> ON e.deptno = dept_max.deptno AND e.sal = dept_max.max_salary;

### c Determine the employees, who are located at the same place.

- SELECT e1.ename AS employee_name_1, e2.ename AS employee_name_2, d.loc
  -> FROM Emp e1
  -> JOIN Dept d ON e1.deptno = d.deptno
  -> JOIN Emp e2 ON e1.deptno = e2.deptno AND e1.empno != e2.empno
  -> JOIN Dept d2 ON e2.deptno = d2.deptno AND d.loc = d2.loc;

### d Determine the employees, whose total salary is like the minimum Salary of any department.

- SELECT e.ename AS employee_name
  -> FROM Emp e
  -> JOIN (
  -> SELECT deptno, MIN(sal) AS min_salary
  -> FROM Emp
  -> GROUP BY deptno
  -> ) dept_min
  -> ON e.deptno = dept_min.deptno AND e.sal = dept_min.min_salary;

### e Determine the department which does not contain any employees.

- SELECT d.dname AS department_name
  -> FROM Dept d
  -> LEFT JOIN Emp e ON d.deptno = e.deptno
  -> WHERE e.empno IS NULL;
