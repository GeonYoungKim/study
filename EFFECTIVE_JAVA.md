# effective-java
이펙티브 자바 책의 정리

1. 박싱타입을 사용하지마라고 기본 타입을 사용하라(기본타입 -> int, long, double ...)

2. 자원 해제가 필요한 클래스의 경우 AutoCloseable 인터페이스를 구현(void close만 있는 인터페이스 - ex = Bufferedreader) => 결국 close 메소드가 있다면 try-with-resources에서 호출해줌.

3. util 클래스의 경우 private한 생성자를 정의하여 객체 생성의 방어로직을 넣자.

4. 상속 클래스의 경우 문서화 하라.

5. 추상클래스로 만든것은 인터페이스로 대체하는게 나을지 고려!!

6. inner 클래스의 경우 바깥 인스턴스에 접근할일이 없다면 무조건 static으로 만들어서 사용.

7. 제네릭의 경우 로타입을 없애고 비한정적 와일드카드 타입을 사용하라.

8. 제네릭의 경고를 제거할 수는 없지만 타입안전하다고 확신할수 있다면 @SuppressWarning("unchecked")를 사용하자. -> 가능한한 좁은범위로 사용. 또한 경고를 무시해도 안전한 이유를 항상 주석으로 남긴다.

9. 배열보다는 리스트를 사용.

10. Object를 사용하는 코드는 되도록이면 제네릭을 활용하자.

11. ...String[] 배열보다는 List 사용

12. enum의 필드로 수행할일이 있을 경우 enum에 내부 메서드를 구현하자.

13. enum 타입을 key로 사용하는것은 EnumMap을 사용하자.

14. 어노테이션으로 수정할만한게 있는지 확인.

15. 정의하려는게 타입이라면 어노테이션을 활용.

16. 익명클래스 -> 람다 -> 메서드 참조

17. null 검사는 자바의 Objects.requireNonNull 사용하기

18. 컬렉션의 반환은 null이 아닌 빈 컬렉션을 반환해라. 반환시 클래스의 static 변수를 사용 ex) Collections.emptyList() -> 빈 컬렉션

19. 배열 또한 길이가 0인 배열을 사용!! -> 메서드 호출시마다 새로운 길이가 0인 배열을 만들어 반환하기 싫다면 private static final 로 클래스 변수를 선언한뒤 해당 데이터를 반환하라.

20. int, long, double을 반환하는 optional은 OptionalInt, OptionalLong, OptionalDouble을 사용하자.

21. 정확한 계산이 필요한 경우에는 double과 float는 버리고 int, long, BigDecimal을 사용해야 한다.

22. 문자열 연결의 경우 StringBuilder를 사용하자.

23. 객체는 인터페이스를 사용해서 참조하자 ex) List<String> list = new ArrayList<>(); - 좋은 예, ArrayList<String> list = new ArrayList<>(); - 나쁜 예

24. 리플렉션 코드는 인터페이스로 가능하면 대체해라, 또한 리플렉션은 인스턴스 생성에만 사용하자(메소드 호출은 자제.) 

25. Exception, RuntimeException, Throwable, Error는 직접사용하지 말고 이를 구현한 자식 예외 클래스 혹은 커스텀 예외를 사용하자.

26. 예외 코드를 만든다면 최대한 무시는 하지않으며 만약 무시해야한다면 그이유를 주석으로 설명하고, 예외 변수이름도 ignored로 변경하자.

27. 시간 간격을 잴때는 System.currentTimeMillis 보다는 System.nanoTime을 사용하자

28. 쓰레드 보다는 실행자, 태스크, 스트림을 애용하자.

29. 동기화 문제일때, Collections.synchronizedMap -> ConcurrentHashMap을 사용
