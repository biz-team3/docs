# HTTP API 문서

현재 `app` 프론트에서 사용하는 1차 MVP REST API를 기능 단위 디렉터리로 분리한다.

## 작성 규칙

- 하나의 REST API는 하나의 `.http` 파일로 작성한다.
- 파일명은 `get-feed-posts.http`, `create-comment.http`처럼 행위가 드러나게 작성한다.
- 각 파일에는 REST 기본 정의, 요청 파라미터, 요청 본문, 제한 조건, 테스트 필요 조건, 성공/실패 응답 예시를 포함한다.
- 보호 API는 `Authorization: Bearer {{accessToken}}` 헤더를 기준으로 작성한다.
- 백엔드 구현 시 프론트 응답 형태를 깨지 않도록 API 계층에서 DTO 변환을 우선한다.

## 공통 변수

각 `.http` 파일은 독립 실행을 우선하므로 아래 변수를 파일마다 반복해서 둔다.

```http
@baseUrl = http://localhost:8080
@accessToken = replace-me
```

## 공통 에러 응답

```json
{
  "code": "ERROR_CODE",
  "message": "사용자에게 보여줄 수 있는 에러 메시지",
  "errors": [
    {
      "field": "fieldName",
      "message": "필드별 검증 메시지"
    }
  ]
}
```

## 문서 대상

```text
auth           로그인, 로그아웃, 현재 사용자
users          사용자 생성/조회/수정/삭제
profiles       프로필 조회/수정, 프로필 게시물
posts          피드, 게시물 상세, 게시물 CRUD, 좋아요, 저장
comments       댓글 CRUD
stories        스토리 피드, 사용자 스토리 묶음, 생성/삭제
follows        팔로워/팔로잉 목록, 팔로우/언팔로우
notifications  알림, 팔로우 요청
media          게시물/프로필 이미지 업로드
```

`preferencesApi`는 서버 REST API가 아니라 프론트 `localStorage["app.preferences"]` 기반 설정이므로 `.http` 호출 문서 대상에서 제외한다.
