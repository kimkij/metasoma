# 🐙 GitHub Pages를 이용한 무료 웹사이트 배포 가이드 (비개발자용)

깃허브(GitHub)가 제공하는 **GitHub Pages** 서비스를 이용하면 코딩이나 복잡한 프로그램 설치 없이, 웹 브라우저 상의 클릭 몇 번으로 우리의 CRM 웹페이지를 전 세계에 무료 배포할 수 있습니다.

---

## 1단계. 깃허브 가입 및 저장소(Repository) 생성
1. **GitHub 회원가입 및 로그인**
   - [GitHub 홈페이지](https://github.com/)에 접속하여 회원가입을 완료하고 로그인합니다.

2. **새로운 저장소(Repository) 만들기**
   - 로그인 후 화면 우측 상단의 **[+]** 아이콘을 클릭한 뒤 **[New repository]**를 선택합니다.
   - 설정값을 다음과 같이 입력합니다:
     - **Repository name**: 원하는 이름 기입 (예: `mind-crm`)
     - **Public/Private**: 반드시 **Public**으로 설정해야 무료 웹 호스팅(Pages)을 사용할 수 있습니다.
     - 다른 체크박스(Add a README, .gitignore 등)는 모두 해제한 상태로 유지합니다.
   - 최하단의 **[Create repository]** 버튼을 클릭합니다.

---

## 2단계. 웹페이지 파일 업로드하기 (웹 환경)
1. **파일 업로드 화면 진입**
   - 저장소가 생성되면 빈 화면이 나옵니다. 
   - 화면 중앙 근처의 파란색 글씨 중 **"uploading an existing file"** (기존 파일 업로드) 링크를 클릭합니다.

2. **드래그 앤 드롭으로 파일 올리기**
   - 탐색기를 열어 `c:\Users\hani\Desktop\antigravity\app\CRM app` 폴더 내부로 들어갑니다.
   - 다음 핵심 파일들을 마우스로 선택한 뒤 깃허브 웹 화면에 끌어다 놓습니다:
     - `index.html`
     - `app.js`
     - `firebase-config.js`
     - *(주의: `design` 폴더나 기타 가이드 파일은 올리지 않고 위 3개 핵심 파일만 올리는 것이 깔끔합니다.)*
   - 파일 목록이 하단에 다 올라간 것을 확인하고, 하단의 초록색 **[Commit changes]** (변경사항 커밋) 버튼을 클릭합니다.

---

## 3단계. GitHub Pages 활성화 및 배포 완료
1. **설정(Settings) 메뉴 접속**
   - 저장소 화면 우측 상단의 톱니바퀴 아이콘인 **[Settings]** 탭을 클릭합니다.

2. **Pages 설정 변경**
   - 좌측 사이드바 메뉴에서 **[Code and automation] > [Pages]** 메뉴를 클릭합니다.
   - **Build and deployment** 섹션의 설정을 아래와 같이 변경합니다:
     - **Source**: `Deploy from a branch`로 유지
     - **Branch**: `None`으로 되어 있는 부분을 클릭하여 `main` (또는 파일 업로드 시 설정된 기본 브랜치 명)으로 변경합니다.
     - 폴더 경로는 `/ (root)` 그대로 둔 후 우측의 **[Save]** 버튼을 누릅니다.

3. **배포 확인**
   - 약 1~2분 정도 기다린 후 브라우저 페이지를 새로고침(F5)합니다.
   - Pages 설정 페이지 최상단에 다음과 같은 안내 배너가 표시됩니다:
     > 🌐 **Your site is live at `https://[본인깃허브아이디].github.io/mind-crm/`**
   - 해당 주소를 클릭하면 웹앱이 실제 작동하는 것을 볼 수 있습니다!

---

## 💡 구매한 나만의 도메인 연결하기
구매하신 개인 도메인(예: `onmaeum.com`)이 있는 경우 아래 과정을 추가합니다.

1. **GitHub Pages 설정 창에서 도메인 기입**
   - Pages 메뉴 아래의 **Custom domain** 입력 칸에 내 도메인 주소(예: `www.onmaeum.com`)를 입력하고 **[Save]**를 클릭합니다.

2. **도메인 구매 사이트(가비아 등)에 CNAME 등록**
   - 구매한 도메인 설정 창의 DNS 관리 메뉴로 이동합니다.
   - 아래와 같이 레코드를 추가합니다:
     - **타입(Type)**: `CNAME`
     - **호스트(Host)**: `www`
     - **값(Value)**: `[본인깃허브아이디].github.io.` (마지막에 점을 붙여주어야 하는 경우가 많습니다.)
   - 등록 완료 후 GitHub Pages 설정 창의 **Enforce HTTPS** 옵션을 켜주면 보안 접속(HTTPS)까지 적용이 완료됩니다.
