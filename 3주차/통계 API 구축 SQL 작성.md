### 통계 API 구축 SQL 작성

group by, union, substr, case when then 구문 사용

***

1. 월별 접속자 수

   ```sql
   select count(*) as totCnt
   from statistc.requestinfo ri
   where mid(ri.createDate, 7, 2) = #{month}
   ```

   

2. 일자별 접속자 수

   ```sql
   select count(*) as totCnt
   from statistc.requestinfo ri
   where mid(ri.creatDate, 5, 2) = #{date}
   ```

   

3. 평균 하루 로그인 수 //하루 평균 로그인 수

   ```sql
   select avg(cnt)
   from (
   	select count(*) as cnt
   	from statistc.requestinfo ri
   	where requestCode = 'L'
   	group by substr(ri.createDate, 6, 2)
   )loginCount;
   ```

   

4. 휴일을 제외한 로그인 수

5. 부서별 월별 로그인 수

   

   - 참고.년별 접속자수 

   ```sql
   select count(*) as totCnt
   from statistc.requestinfo ri
   where left(ri.createDate, 2) = #{year};
   ```

   