1) SELECT COUNT(*)
    FROM emp;

2) SELECT COUNT(*)
     FROM dept;

3) SELECT ENAME 
     FROM EMP;

4) SELECT DNAME 
    FROM dept;

5) SELECT SUM(SAL)
     FROM emp;

6) SELECT SUM(COMM)
      FROM emp;

7) SELECT *
     FROM emp
     WHERE COMM IS NOT NULL;

8) SELECT SYSDATE
     FROM dual;

9) SELECT AVG(SAL)
     FROM emp;

10) SELECT DEPTNO, COUNT(ENAME)
       FROM emp
       GROUP BY DEPTNO;

11) SELECT DEPTNO, SUM(SAL)
       FROM emp
       GROUP BY DEPTNO;

12) SELECT JOB, COUNT(ENAME)
       FROM emp
       GROUP BY JOB;

13) SELECT JOB, AVG(SAL)
       FROM emp
       GROUP BY JOB;

14) SELECT ENAME,
to_char(hiredate,'DAY') AS hire_day,
to_char(hiredate,'MM') AS hire_month,
to_char(hiredate,'YYYY') AS hire_year
FROM emp;

15) SELECT *
       FROM emp
       ORDER BY DEPTNO;

16) SELECT *
       FROM emp
       ORDER BY JOB;

17) SELECT *
       FROM emp
       ORDER BY SAL DESC;

18) SELECT * 
       FROM emp 
      ORDER BY DEPTNO ASC, 
      SAL DESC;

19) SELECT COUNT(*) AS nameswithsixletters
       FROM Emp
       WHERE LENGTH(EName) = 6;

20) SELECT MIN(sal),MAX(sal)
       FROM emp
       ORDER BY sal;

21) SELECT DEPTNO,MAX(SAL),MIN(SAL),AVG(SAL),SUM(SAL)
      FROM emp
      GROUP BY DEPTNO;

22) SELECT * 
       FROM EMP 
       ORDER BY HIREDATE ASC;

23) SELECT * 
       FROM EMP
       ORDER BY HIREDATE DESC
       FETCH FIRST 1 ROW ONLY;

24) SELECT *
       FROM EMP
       ORDER BY HIREDATE ASC 
       FETCH FIRST 1 ROW ONLY;

25) SELECT EMPNO,ENAME,DEPTNO,HIREDATE,TO_CHAR(HIREDATE,'YYYY') AS HIREYEAR
       FROM emp
       ORDER BY HIREYEAR DESC, DEPTNO ASC;

26) SELECT *
       FROM emp
       WHERE SAL >= (SELECT AVG(SAL) FROM EMP);

27) SELECT *
       FROM emp
       WHERE SAL <= (SELECT AVG(SAL) FROM EMP);

28) SELECT *
       FROM emp 
       WHERE sal between 2000 AND 4000;

29) SELECT ENAME, SAL
       FROM (
       SELECT ENAME, SAL
      FROM emp
      ORDER BY SAL ASC
      FETCH FIRST 1 ROW ONLY
       ) min_sal

      UNION ALL

    SELECT ENAME, SAL
    FROM (
       SELECT ENAME, SAL
       FROM emp
       ORDER BY SAL DESC
        FETCH FIRST 1 ROW ONLY
    ) max_sal;

30) SELECT COUNT(*)
       FROM(
	SELECT EMPNO, ENAME, HIREDATE, TO_CHAR(HIREDATE,'MM') AS JOINING_MONTH
FROM emp
WHERE TO_CHAR(HIREDATE,'MM') = 05
    );
