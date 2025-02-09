# 체스 리뷰어 가이드

## 미션 안내
사전 준비 단계에서는 레벨1에서 구현한 체스 애플리케이션 코드를 가져옵니다. 1단계에서는 Spark 기반의 애플리케이션을 스프링 프레임워크 기반의 애플리케이션으로 전환하고, 2단계에서 리소스 생성, 조회, 삭제와 관련된 새로운 요구사항을 구현합니다.

## 목표하는 학습 경험
- 레벨1에서 구현한 체스 애플리케이션을 토대로 스프링 프레임워크를 활용하여 구현하는 경험
- 핵심 로직은 프레임워크에 종속되지 않는게 중요하다는 점을 인지하고 이를 고려하여 개발을 하는 경험
- 학습 테스트를 통해 스프링 프레임워크를 익히고 미션을 통해 실제로 적용해보는 경험

## 리뷰 포인트
### 사전 준비, 1단계
1단계에서는 레벨1의 마지막 미션인 스파크 기반의 체스 애플리케이션을 스프링 프레임워크로 전환합니다. 적절한 애노테이션 사용과 설정을 통해 요청을 처리하도록 구현했는지를 중점적으로 피드백하여 1단계는 빠르게 merge될 수 있도록 해주세요.
- 적절한 애노테이션을 사용해서 Bean을 생성하고(`@Controller`, `@RestController` 등) 요청을 처리하는지(`@RequestMapping`, `@RequestParam`, `@ResponseEntity` 등) 확인해주세요.
- DB 연결과 관련된 요구사항을 잘 지켰는지 확인해주세요.
    - Spring JDBC에서 제공하는 JdbcTemplate를 이용하여 Connection을 직접 만들어 주는 로직을 대체한다.
    - JdbcTemplate는 매번 새로 생성하지 않고 빈 주입을 받아서 사용한다.
- 프레임워크 전환 시 발생한 기존 도메인, 비즈니스 로직의 변경과 관련된 피드백을 주세요. 
   - 레벨1 때 객체간의 결합도가 낮은 설계를 했다면 이번 미션에서 기존에 있던 코드의 변경은 크지 않을 것입니다. 기존의 도메인이나 비즈니스 관련된 로직의 변경이 컸다면 어려움이 없었는지 혹은 왜 변경이 많았는지를 묻거나, 변경이 적다면 칭찬 코멘트와 함께 프레임워크 전환이 수월했던 이유를 물어 이에 대해 생각해볼 수 있는 기회를 주세요.
- 이번 미션의 주된 목표는 프레임워크를 전환하는 경험을 해보는 것이니 체스 도메인 혹은 계층 구조에 관한 피드백은 2단계에 주셔도 괜찮습니다.

### 2단계
2단계에서는 체스방을 만들고, 목록을 조회하고, 체스방에 참여하고, 삭제하는 새로운 요구사항을 구현합니다. 일반적인 스프링 기반의 웹 애플리케이션의 구조를 갖췄는지를 위주로 피드백해주세요.
- 1단계의 리뷰 포인트와 피드백 주셨던 사항들이 잘 반영되어있는지 확인해주세요.
- CustomException과 `@ExceptionHandler`, `@ControllerAdvice` 등을 사용해서 적절한 예외처리를 하였는지 피드백 주세요.
- 서로 토론해보거나 깊게 생각해볼 수 있는 주제를 던져주세요.
   - ex. Service 레이어를 왜 나눴는지 혹은 왜 안나눴는지
   - ex. 어떤 객체를 Bean으로 관리하는 것이 좋을지 
- 적절한 HTTP Method나 Status를 사용 했는지, 더 나아가 REST API 설계와 관련된 내용을 추가로 피드백 주셔도 좋습니다.

### 공통
- 레벨1에서 학습한 객체지향 생활 체조 원칙을 잘 지키며 구현하는지 확인해주세요.
