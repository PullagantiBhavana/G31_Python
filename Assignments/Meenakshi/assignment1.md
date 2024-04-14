[1]. select count(*) from emp;

[2]. select count(*) from dept;

[3]. select ename from emp;

[4]. select dname from dept;

[5]. select sum(sal) from emp;

[6]. select sum(comm) from emp;

[7]. select job as job_title from emp where comm is not null;

[8]. select sysdate from dual;

[9]. select avg(sal) from emp;

[10]. select dname, count(*) 
      	from emp  full outer join dept  on emp.deptno = dept.deptno 
    	group by dept.dname;

[11]. select dname,sum(sal) 
    	from emp  full outer join dept  on emp.deptno = dept.deptno  
    	group by dept.dname;
	

[12]. select job,count(*)  from emp group by job;


[13]. select job,avg(sal) from emp group by job;


[14]. select ename,to_char(hiredate,'Day'),to_char(hiredate,'MM'),to_char(hiredate,'YYYY') 
    	from emp; 


[15]. select ename,dname 
    	from emp full outer join dept on emp.deptno=dept.deptno 
    	order by dname asc;


[16]. select ename,job from emp order by job asc;


[17]. select ename,sal from emp order by sal desc;


[18]. select ename,dname,sal 
    	from emp  full outer join dept  on emp.deptno=dept.deptno 
    	order by dname,sal desc;


[19]. select count(ename) from emp where length(ename)=6;


[20]. select max(sal),min(sal) from emp;


[21]. select dname,max(sal),min(sal),sum(sal),avg(sal) 
    	from emp full outer join dept  on emp.deptno=dept.deptno 
    	group by dname;


[22]. select ename,hiredate 
    	from emp 
    	order by hiredate;


[23]. select ename from emp where hiredate = (select max(hiredate) from emp);


[24]. select ename from emp where hiredate = (select min(hiredate) from emp);


[25]. select ename,hiredate,dname 
    	from emp full outer join dept  on emp.deptno=dept.deptno 
    	order by to_char(hiredate,'YYYY') desc,dname;


[26]. select ename from emp where sal>= (select avg(sal) from emp);


[27]. select ename from emp where sal<= (select avg(sal) from emp);


[28]. select ename from emp where sal between 2000 and 4000; 


[29]. select ename 
    	from emp 
    	where sal=(select max(sal) from emp) union select ename 
    	from emp 
    	where sal=(select min(sal) from emp);


[30]. select count(*) from emp where to_char(hiredate, 'mm') = to_char(add_months(current_date, 1), 'mm');
