# WebFlux
WebFlux는 Servlet 기반이 아닌 Reactive 기반의 Spring Framework이다.

# WebFlux 시작
kotlin을 이용해 webflux spring application을 만들어보자.

WebFlux를 사용하기 위해서는 아래 dependency가 필요하다.
``` kotlin
implementation("org.springframework.boot:spring-boot-starter-webflux")
```

이 dependency를 추가하고 main class에 다음 annotation을 적용하고 build한 뒤 실행이 되는지 확인한다.
``` kotlin
@SpringBootApplication
@EnableWebFlux
class WebfluxTest

fun main(args: Array<String>) {
    runApplication<WebfluxTest>(*args)
}
```


