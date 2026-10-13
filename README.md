# SafeOrbit 랜딩 페이지

스마트 여권 커버 **SafeOrbit**의 랜딩 페이지(2차-A · 데이 & 나이트)입니다.
빌드 과정이 없는 순수 HTML 사이트라서 GitHub에 올리고 Vercel에 연결하면 바로 배포됩니다.
콘셉트 디자인 프로젝트이며, 가격·사양·출시 일정은 실제 판매 정보가 아닙니다(사이트 하단에도 표기).

## 폴더 구성

```
safeorbit-site/
├── index.html                 사이트 전체 (스타일·스크립트 포함)
├── assets/
│   └── safeorbit-bgm.mp3      배경 음악 (64초 루프, 오리지널 곡)
└── README.md
```

## 들어 있는 내용

- 가격: 정가 50,000원 / 얼리버드 40,000원 (20% 할인, 10월 31일까지) / 11월 정식 출시
- 제품 사양: 100 × 140 × 9 mm, 약 68 g, 풀그레인 소가죽, USB-C 충전 최대 6개월, BLE 5.3,
  알림 거리 3단계(약 3m/10m/20m), RFID 차단(13.56MHz), 생활방수 IPX4, iOS 16+ / Android 10+,
  구성품(커버·USB-C 케이블·퀵 가이드·더스트 파우치), 1년 무상 A/S
- 제품·라이프스타일 사진 8장 (Higgsfield로 생성)
- 반응형: 휴대폰(360px)부터 태블릿, 데스크톱(1440px)까지 확인. 900px 이하에서는 햄버거 메뉴, 640px 이하에서는 앱 화면이 가로로 넘겨 보기 방식으로 바뀝니다.

## 사진 넣기

사이트는 `assets/img/` 폴더의 사진을 먼저 찾고, 없으면 Higgsfield 서버의 사진을 대신 보여줍니다.
그래서 아무것도 안 해도 사진은 보이지만, 사진을 내 사이트 안에 넣어 두면 더 빠르고 오래 안전합니다.

**사진 받는 방법 (더블클릭 한 번)**

- 윈도우: `download-images.bat` 더블클릭
- 맥: `download-images.command` 더블클릭
  (처음에 "확인되지 않은 개발자" 경고가 뜨면 파일을 우클릭 → **열기** → **열기**)

끝나면 `assets/img/` 폴더에 아래 8장이 생깁니다. 이 폴더까지 함께 GitHub에 올리면 됩니다.

| 파일 이름 | 사진 | 쓰이는 곳 |
| --- | --- | --- |
| product-hero.png | 받침대 위 네이비 커버 | 첫 화면, SNS 피드 |
| product-colors.png | 네이비·그레이 두 컬러 | 컬러 섹션 |
| product-detail.png | 펼친 커버 안쪽 트래커 | 내부 구조 섹션 |
| life-airport.png | 공항 탑승구 | 여행 시나리오 1, SNS 피드 |
| life-hotel.png | 호텔 체크인 카운터 | 여행 시나리오 2 |
| life-street.png | 유럽 광장 크로스백 | 여행 시나리오 3 |
| life-flatlay.png | 여행 준비물 플랫레이 | SNS 피드 |
| life-inflight.png | 노을 진 기내 | 사용 후 카드, SNS 피드 |

**다른 사진으로 바꾸고 싶다면** 같은 이름으로 `assets/img/`에 덮어쓰기만 하면 됩니다.
(직접 찍은 사진, Higgsfield에서 새로 만든 사진 모두 가능 · jpg라면 `index.html`에서 `.png`를 `.jpg`로 바꿔 주세요)

## 배경 음악(BGM)

- 이 사이트를 위해 새로 만든 오리지널 앰비언트 곡이라 저작권 걱정 없이 사용할 수 있습니다.
- 브라우저는 소리 나는 자동 재생을 막기 때문에, 오른쪽 아래 **BGM 켜기** 버튼을 눌러야 재생됩니다.
- 기본 볼륨은 `index.html` 아래쪽 스크립트의 `TARGET = 0.45` 값(0~1)으로 조절합니다.

## 방문자 분석 (Vercel Web Analytics)

코드는 이미 `index.html`에 들어 있습니다. 대시보드에서 켜기만 하면 됩니다.

1. Vercel 대시보드 → 프로젝트 선택 → 왼쪽 **Analytics** → **Enable** 을 누릅니다.
2. 한 번 다시 배포합니다. (GitHub에 아무 파일이나 수정해서 커밋하거나, Deployments 탭에서 **Redeploy**)
3. 사이트에 접속해 보고, 잠시 후 Analytics 화면에서 방문자 수·유입 경로·국가·기기 정보를 확인합니다.

- 쿠키를 쓰지 않는 방식이라 쿠키 동의 배너가 따로 필요 없습니다.
- 무료(Hobby) 플랜에서도 페이지 방문 집계가 됩니다. 버튼 클릭 같은 사용자 지정 이벤트 집계는 Pro 플랜부터입니다.
- Analytics를 켜면 대시보드에 프로젝트 전용 스크립트 주소가 안내될 수 있습니다. 그 경우 `index.html`의 `/_vercel/insights/script.js`를 안내된 주소로 바꿔 주세요.

## 배포 방법 (GitHub + Vercel)

### 1. GitHub에 올리기

**방법 A — 웹에서 업로드 (Git 설치 없이)**

1. https://github.com 에 로그인하고 오른쪽 위 **+** → **New repository** 를 누릅니다.
2. Repository name에 `safeorbit-site` 를 입력하고 **Create repository** 를 누릅니다.
3. **uploading an existing file** 링크를 누릅니다.
4. `safeorbit-site` 폴더 **안의** `index.html`, `README.md`, `assets` 폴더를 끌어다 놓습니다.
   (폴더 자체가 아니라 안의 내용물을 올려야 `index.html`이 저장소 맨 위에 놓입니다.)
5. **Commit changes** 를 누릅니다.

**방법 B — 터미널 사용**

```bash
cd safeorbit-site
git init
git add .
git commit -m "SafeOrbit 랜딩 페이지"
git branch -M main
git remote add origin https://github.com/<내-아이디>/safeorbit-site.git
git push -u origin main
```

### 2. Vercel에 연결하기

1. https://vercel.com 에서 **Continue with GitHub** 로 로그인합니다.
2. **Add New…** → **Project** → `safeorbit-site` 옆 **Import** 를 누릅니다.
3. Framework Preset은 **Other**, Build Command와 Output Directory는 비워 둡니다.
4. **Deploy** 를 누르면 `https://safeorbit-site.vercel.app` 같은 주소가 생깁니다.

### 3. 수정하고 다시 배포하기

GitHub의 `main` 브랜치에 변경 사항을 올리면 Vercel이 자동으로 다시 배포합니다.

## 참고

- 글꼴(Orbit, Noto Sans KR, IBM Plex Mono)은 Google Fonts에서 불러옵니다.
- 얼리버드 신청 폼은 디자인만 되어 있습니다. 실제로 이메일을 받으려면 Formspree, 스티비 같은 폼 서비스를 연결해야 합니다.
