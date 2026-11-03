# 프로필 유지보수

프로필: https://github.com/kyeong205

저장소: https://github.com/kyeong205/kyeong205

## 파일 구성

- `README.md`: GitHub 프로필에 표시되는 헤더, 기술 배지, 통계 및 기여도 이미지.
- `.github/workflows/snake.yml`: 실제 기여도 데이터로 SVG를 생성하고 `output` 브랜치에 배포.
- `output` 브랜치: 자동 생성된 라이트·다크 SVG. 직접 수정하지 않습니다.

주요 스택은 확인한 웹·서버·Unity 구현을 중심으로 표시하고, 세부 경험과 도구는 접을 수 있는 목록으로 분리합니다. 로컬 조사에서 실제 TypeScript 소스와 Nginx 설정을 확인하지 못해 두 기술은 공개 스택에서 보류했습니다. 프로젝트에 포함된 기술이 곧 개인의 숙련도나 단독 구현을 의미하지는 않습니다. 회사 프로젝트 정보나 확인되지 않은 경력·성과는 추가하지 않습니다.

## 자동 갱신과 권한

- 매일 **06:17 KST / 전날 21:17 UTC**에 스네이크 생성을 예약합니다. GitHub 실행 대기열에 따라 늦어질 수 있습니다.
- `main`의 README 또는 워크플로 변경 시 실행하며, Actions → **Generate contribution snake** → **Run workflow**에서도 실행할 수 있습니다.
- `output`에 SVG 두 개를 게시합니다. GitHub Pages 사이트 설정은 필요하지 않습니다.
- 기본 권한은 `contents: read`이며, 생성·게시 작업에만 `contents: write`를 부여합니다. 자동 발급되는 `GITHUB_TOKEN`만 사용하며 개인 토큰이나 별도 Secret은 필요하지 않습니다.
- 외부 Actions는 확인한 커밋 SHA로 고정했습니다. 버전을 바꿀 때 공식 릴리스와 변경 사항을 검토하고 SHA를 갱신합니다.
- 공개 저장소는 60일 동안 저장소 활동이 없으면 예약 워크플로가 비활성화될 수 있습니다. Actions에서 다시 활성화합니다.

## 외부 서비스

| 기능 | 프로젝트 / 서비스 | 가입·키 |
| --- | --- | --- |
| 애니메이션 헤더 | [Capsule Render](https://github.com/kyechan99/capsule-render) | 불필요 |
| 기술 배지 | [Shields.io](https://shields.io/) | 불필요 |
| GitHub Stats · Top Languages | [GitHub Stats Extended](https://github.com/stats-organization/github-stats-extended) 공개 인스턴스 | 불필요 |
| 동물농장 | [Gitanimals](https://www.gitanimals.org/) | 사용자가 생성한 농장 이미지 연동 |
| 기여도 SVG | [Platane/snk](https://github.com/Platane/snk) + GitHub Actions | 자동 발급 `GITHUB_TOKEN` |

Gitanimals는 사용자가 제공한 농장 URL을 그대로 사용합니다. 별도 Secret이나 API 키는 저장하지 않습니다.

통계는 외부 서비스가 자체 캐시에 따라 갱신합니다. 이 저장소의 Actions는 스네이크를 갱신합니다. 외부 서비스 장애나 GitHub 이미지 프록시 캐시로 이미지 표시가 지연될 수 있습니다.

Top Languages는 기본적으로 공개 소유 비포크 저장소를 대상으로 합니다. 조직·타인 저장소에 기여한 코드나 비공개 회사 코드를 이 카드로 추정하지 않습니다. 데이터가 없으면 서비스가 제공하는 `No languages data.` 상태를 그대로 표시하며 수치를 만들지 않습니다. 개인 토큰을 외부 통계 서비스에 전달하지 않습니다.

WakaTime 같은 업무 시간 측정 기능은 포함하지 않았습니다. 향후 추가하려면 별도 가입·수집 동의·API 키 관리가 필요합니다.

## 표시 확인

1. Actions 실행 결과가 `success`인지 확인합니다.
2. `output` 브랜치에 `github-contribution-grid-snake.svg`, `github-contribution-grid-snake-dark.svg`가 있는지 확인합니다.
3. 프로필에서 헤더, 배지, 통계, 스네이크를 확인합니다. `<picture>`는 브라우저의 `prefers-color-scheme`에 따라 이미지를 선택하고 라이트 이미지를 기본값으로 사용합니다.
4. 농장은 600px, 통계 카드는 480px 폭으로 지정하고 별도 고정 높이를 주지 않습니다. 통계와 추가 경험은 details 안에 배치합니다. GitHub의 반응형 이미지 스타일로 좁은 화면에서는 축소되며 배지는 줄바꿈됩니다.

참고: [프로필 README](https://docs.github.com/en/account-and-profile/how-tos/profile-customization/managing-your-profile-readme), [예약 이벤트와 비활성화](https://docs.github.com/en/actions/reference/workflows-and-actions/events-that-trigger-workflows#schedule).
