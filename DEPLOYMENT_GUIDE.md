# 🌐 온마음 심리상담소 CRM 실서비스 배포 가이드 (비개발자용)

본 가이드는 개발 및 인프라 구축 경험이 없는 사용자분께서 로컬에서 테스트한 CRM 시스템을 실제 인터넷 주소(도메인)로 배포하고, 여러 기기(상담소 태블릿, 관리자 PC 등)에서 데이터를 연동하여 사용할 수 있도록 단계별로 안내합니다.

---

## 1단계. Firebase 클라우드 데이터베이스 세팅 (데이터 연동)
여러 기기에서 입력한 데이터가 실시간으로 동기화되려면 데이터가 내 브라우저가 아닌 인터넷 클라우드 공간(Firebase)에 저장되어야 합니다.

1. **Firebase 콘솔 접속 및 프로젝트 생성**
   - [Firebase Console](https://console.firebase.google.com/)에 구글 계정으로 로그인합니다.
   - **[프로젝트 만들기]** 버튼을 클릭하여 프로젝트 이름(예: `onmaeum-crm`)을 입력하고 프로젝트를 생성합니다. (구글 애널리틱스 연동은 비활성화하셔도 무방합니다.)

2. **웹 앱 등록 및 설정값 복사**
   - 프로젝트 대시보드 화면 중앙의 웹 아이콘(`</>`)을 클릭합니다.
   - 앱 닉네임을 적고 **[앱 등록]** 버튼을 누릅니다.
   - 화면에 표시되는 코드 중 `const firebaseConfig = { ... }` 객체 내부의 설정값을 복사합니다.

3. **코드 파일 수정**
   - 작업 폴더 내의 [firebase-config.js](file:///c:/Users/hani/Desktop/antigravity/app/CRM%20app/firebase-config.js) 파일을 열어 복사한 값으로 교체합니다.
   ```javascript
   const firebaseConfig = {
     apiKey: "복사한_값_입력",
     authDomain: "복사한_값_입력",
     projectId: "복사한_값_입력",
     storageBucket: "복사한_값_입력",
     messagingSenderId: "복사한_값_입력",
     appId: "복사한_값_입력"
   };
   ```

4. **Firestore 데이터베이스 생성**
   - Firebase 콘솔 좌측 메뉴에서 **[빌드] > [Firestore Database]**를 클릭한 후 **[데이터베이스 만들기]**를 클릭합니다.
   - 데이터베이스 위치는 **asia-northeast3 (서울)**로 선택합니다.
   - 보안 규칙 단계에서는 **[테스트 모드에서 시작]**을 선택하고 만들기 버튼을 클릭합니다.
   - *팁: 테스트 모드는 30일이 지나면 읽기/쓰기가 차단되므로, 실서비스 개시 시점에는 Firestore 메뉴의 [규칙(Rules)] 탭에서 다음과 같이 규칙을 상시 허용으로 변경해 줍니다.*
     ```javascript
     rules_version = '2';
     service cloud.firestore {
       match /databases/{database}/documents {
         match /{document=**} {
           allow read, write: if true;
         }
       }
     }
     ```

---

## 2단계. 무료 웹 호스팅에 웹사이트 업로드 (Netlify 사용)
작성된 파일들을 인터넷 서버에 올려 접속 가능한 주소를 발급받는 단계입니다. 드래그 앤 드롭 방식이라 마우스 클릭만으로 배포가 끝납니다.

1. **Netlify 가입**
   - [Netlify 공식 홈페이지](https://www.netlify.com/)에 접속하여 가입(Sign Up)합니다. (깃허브 계정이나 이메일로 가입 가능)

2. **폴더 드래그 앤 드롭 업로드**
   - 로그인 후 대시보드에서 **[Add new site] > [Deploy manually]** 메뉴를 차례로 클릭합니다.
   - 화면 중앙에 점선 박스(`Drag and drop your site folder here`)가 나타납니다.
   - 윈도우 탐색기를 열어 현재 작업 중인 `c:\Users\hani\Desktop\antigravity\app\CRM app` 폴더를 통째로 선택한 뒤, 해당 점선 박스 안으로 **드래그하여 내려놓습니다(Drag & Drop)**.
   - 파일 업로드 및 서버 배포가 약 10~20초 안에 완료되며, 화면 상단에 `https://random-name-12345.netlify.app` 형식의 무료 주소가 생성됩니다.

3. **고유 주소명 변경**
   - 생성된 사이트 대시보드에서 **[Site configuration] > [Site information] > [Change site name]**을 누릅니다.
   - 원하는 주소명(예: `onmaeum-crm`)으로 설정하면 `https://onmaeum-crm.netlify.app` 주소로 즉시 전 세계 어디서나 접속할 수 있게 됩니다.

---

## 3단계. 나만의 고유 도메인 구입 및 연결 (예: `onmaeum.com`)
상담소 로고나 브랜딩을 위해 구매한 전용 도메인을 앞서 만든 Netlify 웹사이트에 연결하는 방법입니다.

1. **도메인 구매**
   - 가비아(Gabia), 호스팅케이알(Hosting.kr), 후이즈(Whois) 등의 사이트에서 원하는 도메인 주소(예: `onmaeum.com`)를 검색하여 결제합니다. (연간 약 1~2만 원 수준)

2. **Netlify에 도메인 추가**
   - Netlify 내 사이트 대시보드에서 **[Domain management] > [Add custom domain]**을 클릭합니다.
   - 구매한 도메인 주소(예: `onmaeum.com`)를 입력하고 등록을 완료합니다.

3. **DNS 네임서버 설정 (구매한 사이트에서 설정)**
   - 가장 쉬운 방법은 도메인 구매 사이트(가비아 등)의 마이페이지에서 **[DNS 설정]** 또는 **[네임서버 설정]** 메뉴로 들어가는 것입니다.
   - Netlify에서 제공하는 4개의 네임서버 주소를 복사하여 가비아의 네임서버 목록(1차, 2차, 3차, 4차)에 입력하고 저장합니다.
   - 보통 5분에서 최대 24시간 이내에 전 세계 네트워크에 도메인 연결이 완료되며, Netlify가 도메인 주소에 무료 보안 인증서(HTTPS/SSL)도 자동으로 발급 및 설치해 줍니다.
