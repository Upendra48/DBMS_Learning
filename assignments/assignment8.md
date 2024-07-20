# Assignment 8:

“DEPARTMENTS” and “EMPLOYEES”

Schema Reference
DEPARTMENTS: deptno, dname, loc
EMPLOYEES: empno, ename, job, mgr, hiredate, sal, comm, deptno

### Task Overview

### a. Display the employee details for departments that are the same in both EMPLOYEES and DEPARTMENTS.

- SELECT e.\*
  -> FROM emp e
  -> JOIN dept d ON e.deptno = d.deptno;

### b. Display the employee name and department name by implementing a left outer join.

- SELECT e.ename AS employee_name, d.dname AS department_name
  -> FROM emp e
  -> LEFT JOIN dept d ON e.deptno = d.deptno;

### c. Display the employee name and department name by implementing a right outer join.

- SELECT e.ename AS employee_name, d.dname AS department_name
  -> FROM emp e
  -> RIGHT JOIN dept d ON e.deptno = d.deptno;

### d. Display the details of those who draw a salary greater than the average salary.

- SELECT \*
  -> FROM emp
  -> WHERE sal > (SELECT AVG(sal) FROM emp);
