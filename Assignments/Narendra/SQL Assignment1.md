1. SELECT count(*) FROM dept;

2. SELECT count(*) FROM emp;

3. SELECT ename 
   FROM emp;

4. SELECT dname FROM dept;

5. SELECT sum(sal) 
   FROM emp;

6. SELECT sum(comm) FROM emp;

7. SELECT job,comm FROM emp
   WHERE comm is not null;

8. SELECT sysdate FROM dual;

9. SELECT avg(sal) FROM emp;

10. SELECT dept.DNAME,count(*) as count FROM emp 
    FULL OUTER JOIN dept on emp.DEPTNO = dept.DEPTNO 
    GROUP BY dept.DNAME;

11. SELECT dept.DNAME,sum(sal) FROM emp 
    FULL OUTER JOIN dept on emp.DEPTNO = dept.DEPTNO 
    GROUP BY dept.DNAME;

12. SELECT job as job_title, count(*) FROM emp
    group by job;

13. SELECT job as job_title, avg(sal) FROM emp
    group by job;

14. SELECT ename,to_char(hiredate,'MM-Day-YYYY')  FROM emp;

15. SELECT e.ename,d.dname 
    FROM emp e
    FULL OUTER JOIN dept d on e.deptno=d.deptno 
    ORDER BY dname;

16. SELECT job as job_title,ename FROM emp ORDER BY job;

17. SELECT ename,sal as salary FROM emp ORDER BY sal desc;

18. SELECT ename,d.dname,sal 
    FROM emp e
    FULL OUTER JOIN dept d on e.deptno=d.deptno 
    ORDER BY dname desc,sal;

19. SELECT count(ename) FROM emp WHERE length(ename)=6;

20. SELECT min(sal),max(sal) FROM emp;

21. SELECT d.dname,min(sal),max(sal),avg(sal),sum(sal)
    FROM emp e
    FULL OUTER JOIN dept d on e.deptno=d.deptno 
    GROUP BY dname;

22. SELECT ename,hiredate FROM emp ORDER BY hiredate;

23. SELECT ename FROM emp WHERE hiredate = (select max(hiredate) from emp);

24. SELECT ename 
    FROM emp 
    WHERE hiredate = (select min(hiredate) from emp);

25. SELECT e.ename,hiredate,d.dname
    FROM emp e
    FULL OUTER JOIN dept d on e.deptno=d.deptno 
    ORDER BY to_char(hiredate,'YYYY') desc,d.dname;

26. SELECT ename FROM emp WHERE sal >= (select avg(sal) from emp);

27. SELECT ename
    FROM emp
    WHERE sal <= (select avg(sal) from emp);

28. SELECT ename FROM emp WHERE sal between 2000 and 4000;

29. SELECT ename FROM emp where sal=(select max(sal) from emp) union select ename from emp where sal=(select min(sal) from emp);

30. SELECT count(*) 
    FROM emp 
    WHERE to_char(hiredate, 'mm') = to_char(add_months(current_date, 1), 'mm');
