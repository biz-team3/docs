# Preferences API 메모

`app/src/api/preferencesApi.js`는 서버 REST API가 아니라 프론트 로컬 설정이다.

```text
localStorage["app.preferences"]
```

## 현재 저장 값

```json
{
  "theme": "light",
  "language": "ko",
  "location": "South Korea"
}
```

## 문서화 기준

- HTTP `.http` 파일로 만들지 않는다.
- 서버 저장이 필요한 설정으로 바뀌기 전까지 백엔드 API 대상에서 제외한다.
- 다크모드, 언어 설정은 프론트 로컬 상태로 유지한다.
