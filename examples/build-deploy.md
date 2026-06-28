# ErrorNote — 빌드/배포 예시

---

### [2026-06-28] Unity AAB 빌드 후 서명 키 누락
- **상황**: Release AAB 빌드 후 Play Console 업로드 시도
- **문제**: 서명되지 않은 AAB로 업로드 거부
- **원인**: Build Settings에서 Keystore 설정 초기화됨
- **시도했지만 실패한 방법**: 그냥 재빌드, Build And Run으로 시도
- **해결**: Project Settings > Player > Publishing Settings에서 Keystore 재설정 후 빌드
- **검증**: Play Console에서 업로드 성공 메시지 확인
- **재사용 조건**: Unity에서 Release AAB 빌드할 때마다
- **재발 방지**: 빌드 전 Keystore 설정 먼저 확인
- **태그**: #unity #build #keystore #google-play
