# 자바 기초

## 0. Spring 소개

- Spring Framework
- 자바 플랫폼을 위한 오픈소스 애플리케이션 프레임워크
- 동적인 웹 사이트를 개발하기 위해 여러 서비스 제공
- **전자정부 표준** 프레임워크 기반 기술
- 엔터 프라이즈급 애플리케이션을 만들기 위한 경량솔류션(가벼운 프레임워크라는 뜻은 아님)
- 필요한 부분만 가져다 사용할 수 있도록 모듈화
- 각 모듈은 독립적으로 분리, 재사용이 가능
- DI/IoC와 AOP를 지원

| Spring      | Node.js                 |
| ----------- | ----------------------- |
| Java        | JavaScript              |
| 멀티 스레드 | 싱글 스레드 이벤트 루프 |

- Spring boot
  - Spring Project의 하나
  - 수작업으로 초기 셋팅하는 과정 없이 간단히 생성
  - 기본적으로 설정하게 되는 부분들을 이미 내부적으로 지님
  - Servlet Container를 기본 내장(Tomcat, Jetty)
  - pom.xml에서 의존 라이브러리의 버전을 자동으로 관리
  - 자주 사용하는 프로젝트 조합을 미리 만들어 놓아 스프링을 더욱 쉽고 간단하게 사용하기 위해 만들어짐
  - 설정을 자동으로 해줌

## 1. Spring Boot 시작하기

- 스프링의 장점
  - 다양한 Dependencies Library Maven에 등록되어 있는 다양한 라이브러리 사용
  - Node의 NPM과 비슷한 역할

##  2. Spring Boot 구성요소

- pom.xml : Project Object Model
- Maven이 해당 파일을 토대로 의존성 관리 및 배포까지 모든 것을 관리한다
- Spring boot는 pom.xml을 토대로 필요한 라이브러리나 프레임워크의 의존 관계 설정을 자동으로 해준다
- resources : 자원 파일 저장
  - static : 웹 정적 리소스 저장 위치, html, css, js, img
  - templates : 웹 동적 리소스 저장 위치, 뷰 템플릿 저장 위치, FreeMarker, Groovy, Thymeleaf, JSP
  - application.properties : Spring boot의 기본 설정 파일 : Spring boot가 Application 시작 시 이곳의 설정들을 자동으로 반영, 이곳에 DB정보, 서버 포트 번호 설정, 이럴 경우 반드시 git에 올리면 안됨. (.gitignore에 등록)
- 이곳에 Mapper(SQL) 곤련 파일이 저장될 예정
- 프로젝트Application 파일
  - @SpringBootApplication = @Configuration + @EnableAutoConfiguration + @ComponentScan
  - @Configuration : 현재 클래스가 스프링의 설정 파일임을 Spring Context에게 알려주는 Annotation
  - @EnableAutoConfiguration : Spring Boot가 설정을 자동으로 하도록 하는 Annotation
  - @ComponentScan : 다른 컴포넌트, 서비스, 설정 등을 찾을 수 있게 도와주는 Annotation
- ServletInitializer
  - Packaging을 War로 설정할 시 자동 생성되는 클래스 (Jar로 생성할 시엔 생성되지 않음)
  - WebApplicationInitializer Interface의 구현체
  - Tomcat 같은 Servlet Container 환경에서 Spring Boot Application이 동작될 수 있도록 하는 Web Application Context를 구성한다는 의미
- 단위 : Class < Jar < War < Ear
  1. Jar(Java Archive)
     1. 하나의 Application 기능이 가능하도록 java 파일 등을 압축
     2. 실행될 클래스를 명시해야 한다(main)
     3. 단독을 실행이 가능하다(JVM위에서)
     4. 라이브러리, 리소스, property 파일등을 포함
     5. Spring Boot는 WAS(Tomcat)을 내장하고 있기 때문에 jar 배포가 가능하다
  2. War(Web Archive)
     1. Web Application을 지원하기 위한 압축
     2. 단독으로 실행이 불가능(WAS필요)
     3. Jsp, Servlet, git, html, jar 등을 압축하고 지원
     4. WAS(Tomcat)이 알아서 압축을 해제해서 배포

##  3. Web Application 실행

- 127.0.0.1 / localhost
  - localhost는 네트워크에서 사용하는 루트 백 호스트명
  - 자신의 컴퓨터를 의미
  - IPv4에서 IP 주소는 127.0.0.1 / IPv6에서는 ::1
  - 로컬 컴퓨터를 마치 원격 컴퓨터인 것 같이 통신할 수 있어 테스트 목적으로 사용

## 4. Controller 생성