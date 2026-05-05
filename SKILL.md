---
name: biz-team3-fullstack
description: demo 프론트를 기준으로 biz-team3 프로젝트를 Spring Boot 3.x + Java 21 + Oracle DB + MyBatis 백엔드와 최신 React + JavaScript + Tailwind CSS 프론트엔드 구조로 구현할 때 사용한다.
---

# biz-team3 Fullstack

## 기본 스택

### 백엔드

- Spring Boot 3.x
- Java 21
- Oracle DB
- MyBatis
- REST API

### 프론트엔드

- React 최신 버전
- JavaScript
- Tailwind CSS

TypeScript는 사용하지 않는다.

## 기준

- 기존 `demo` 프론트의 설정과 `docs` 내용은 기준으로 삼지 않는다.
- 기존 `demo` 프론트에서 참조할 내용은 UI/UX와 mock 데이터뿐이다.
- 기능을 새로 추가하지 않는다.
- 기존 UI 흐름과 화면 동작을 보존하는 것을 우선한다.

## 프론트엔드 원칙

- React 함수형 컴포넌트를 사용한다.
- JavaScript로 작성한다.
- Tailwind CSS로 스타일링한다.
- mock 데이터는 실제 API 연동 전까지만 사용한다.
- API 호출은 별도 함수나 `api` 영역으로 분리한다.
- 전역 상태는 꼭 필요한 경우에만 사용한다.

## 백엔드 원칙

- Spring Boot 3.x 기준으로 작성한다.
- Oracle DB 기준 SQL을 작성한다.
- MyBatis로 DB 접근을 처리한다.
- Controller, Service, Mapper, DTO, Domain 구조를 따른다.
- Controller에는 요청/응답 처리만 둔다.
- 비즈니스 로직은 Service에 둔다.
- SQL 처리는 Mapper에 둔다.
- 프론트로 반환하는 데이터는 DTO로 분리한다.

## API 연동 원칙

- 먼저 프론트에서 필요한 데이터 구조를 확인한다.
- 그 구조에 맞춰 백엔드 DTO와 API 응답을 설계한다.
- mock 데이터를 실제 API 호출로 교체한다.
- 교체 후 기존 화면 동작이 유지되는지 확인한다.

## 작업 원칙

- 먼저 기존 코드를 확인한다.
- 사용 중인 파일과 이전 구조의 잔재를 구분한다.
- 한 번에 크게 갈아엎지 않는다.
- 사용자가 요청하지 않은 기능은 추가하지 않는다.
- 분석만 요청받은 경우 파일을 수정하지 않는다.
