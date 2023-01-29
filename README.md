# jdbc-practice
## DBCP (Database Connection Pool)
- 미리 일정량의 DB 커넥션을 생성해서 풀에 저장해 두고 있다가 HTTP 요청에 따라 필요할 때 풀에서 커넥션을 가져다 사용하는 기법
- 참고로 스프링 부터 2.0부터는 디폴트 커넥션 풀로 HikariCP 사용
## 커넥션 풀 사용 시 유의 사항
- 커넥션의 사용 주체는 WAS 스레드이므로 커넥션 개수는 WAS 스레드 수와 함께 고려해야 함
- 커넥션 수를 크게 설정하면 메모리 소모가 큰 대신 동시 접속자 수가 많아지더라도 사용자 대기 시간이 상대적으로 줄어들게 되고, 반대로 커넥션 개수를 작세 설정하면 메모리 소모는 적은 대신 그만큼 대기시간이 길어질 수 있음
. 따라서 적정량의 커넥션 객체를 생성해 두어야함
## DataSource
- 커넥션 획득하기 위한 표준 인터페이스
- HikariCP의 DataSource 사용
