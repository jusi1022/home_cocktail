# home_cocktail

홈칵테일 앱의 **온라인 레시피 카탈로그 배포 저장소**입니다. 앱 소스 코드는 여기 없습니다.
GitHub Pages 로 공개되는 정적 JSON 파일만 있습니다.

```
catalog/
  manifest.json                  카탈로그 목차 (최신 버전, 릴리스 목록, 파일 크기·SHA-256)
  releases/<버전>/changes.json   직전 버전과의 차이 (증분)
  releases/<버전>/snapshot.json  그 버전의 온라인 카탈로그 전체
```

- 공개 주소: `https://jusi1022.github.io/home_cocktail/catalog/manifest.json`
- 앱은 하루 한 번 `manifest.json` 을 읽고, 새 버전이 있으면 필요한 파일만 받아 기기에 저장합니다.
  받은 파일은 크기·SHA-256·형식·참조 무결성을 확인한 뒤에만 적용되고, 인터넷이 없어도 쓸 수 있습니다.
- 릴리스 폴더는 한 번 올리면 바꾸지 않습니다. 되돌릴 때는 `manifest.json` 의 `latest` 만 옮깁니다.
- 여기 실리는 레시피는 관리자가 원본 영상과 대조해 검증하고 배포 승인한 것만입니다.
  릴리스가 없는 동안 `manifest.json` 의 `releases` 는 비어 있고 앱은 "최신 상태" 로 봅니다.

이 저장소의 파일은 앱 프로젝트의 `tool/catalog_release/` 도구가 생성하고 올립니다. 손으로 고치지 않습니다.
