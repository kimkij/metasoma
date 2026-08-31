# 🎨 심리상담소 미니 CRM 웹앱 생성 프롬프트 (Stitch / Bolt.new / Lovable 용)

아래 프롬프트 전체를 복사하여 **Stitch.com, Bolt.new, Lovable.dev, v0.dev** 등 AI 웹앱 빌더에 그대로 입력하시면, 심리상담소에서 즉시 사용할 수 있는 아름답고 기능적인 미니 CRM이 완성됩니다.

---

```text
Create a modern, clean, and warm Single Page Application (SPA) for a "Psychological Counseling Center Mini CRM".
The app must have a calming, professional, and trustworthy aesthetic (Warm beige, soft sage green, pastel lavender, and slate gray colors; soft rounded corners, glassmorphism headers, and smooth micro-interactions).
Use LocalStorage to persist all client data, counseling types, and submission records so the app is fully functional immediately.

Here are the detailed features and page flows:

### 1. Database & State Schema (LocalStorage Persistence)
- **Clients**: id (UUID/Number), name (string), birthDate (YYYY-MM-DD), createdAt (timestamp)
- **Counseling Types**: id (UUID/Number), title (string), description (string), isActive (boolean)
  * Default 5 Types:
    1. 개인 심리 상담 (Personal Counseling) - 1:1 맞춤형 마음 치유 솔루션
    2. 부부 & 가족 상담 (Couple & Family) - 관계 회복과 소통을 위한 솔루션
    3. 우울 & 불안 치유 (Depression & Anxiety) - 감정 조절 및 마음 안정 프로그램
    4. 스트레스 & 번아웃 관리 (Stress & Burnout) - 일상 속 리프레시와 스트레스 해소
    5. 청소년 진로 & 학습 상담 (Youth Career & Study) - 자아 탐색 및 미래 설계
- **Counseling Records**: id (UUID/Number), clientId (number), counselingTypeId (number), submittedAt (timestamp), status (Pending/In Progress/Completed)

---

### 2. Client Portal (내담자/손님용 페이지)
- **Landing / Login Page**:
  - Calming, minimal UI with a welcome message (e.g., "마음의 휴식을 드리는 심리상담소입니다.")
  - Input fields:
    - "이름" (Name - text input)
    - "생년월일" (Date of Birth - text input with YYYY-MM-DD format guide, or clean date selector)
  - "로그인/상담 신청 시작" button.
  - Validation: It MUST check if the client is already registered in the Admin's "Clients" database (mocked in LocalStorage).
    - If registered: Store logged-in state and proceed to the next page.
    - If NOT registered: Show a soft, polite modal or toast alert: "등록되지 않은 내담자 정보입니다. 상담소 데스크에 문의하여 등록해 주세요."
  - Include a subtle, small button at the very bottom right: "관리자 로그인" (Admin Login) to route to the Admin Portal.

- **Counseling Selection Page**:
  - Displays the dynamic list of counseling types where `isActive` is true.
  - Display them as beautiful, interactive cards with descriptive icons.
  - Users can select one (or multiple) counseling cards (adds a highlight border/check icon when selected).
  - A clear "최종 제출" (Final Submit) button at the bottom.
  - Clicking submit shows a confirmation modal: "선택하신 상담 항목으로 신청서를 제출하시겠습니까?"

- **Submission Complete Page**:
  - A beautiful success check animation and calming message (e.g., "상담 신청이 완료되었습니다. 잠시 대기해 주시면 상담사가 안내해 드리겠습니다.").
  - Automatically log out and redirect back to the Client Login page after 5 seconds (with a visual countdown bar), or immediately when clicking the "처음 화면으로" (Go to Home) button.

---

### 3. Admin Portal (관리자 페이지)
- **Login Page**:
  - Standard admin login form.
  - Credentials: ID: `admin` / Password: `1q2w3e4r!`
  - Provide clear validation errors on incorrect inputs.

- **Admin Dashboard**:
  - Features a sidebar or top tabs to switch between:
    1. **내담자 리스트 (Client List)**
    2. **심리상담 관리 (Counseling Management)**
  - Header shows: Admin status, "로그아웃" (Logout) button.

- **Tab 1: 내담자 리스트 (Client List)**:
  - **"내담자 등록" (Register Client) Button**:
    - Clicking this opens a clean Modal/Layer.
    - Input fields: "이름" (Name) and "생년월일" (Date of Birth - YYYY-MM-DD format).
    - "등록" (Register) button to save the new client to LocalStorage and show a success toast.
  - **Search & Filter**: Search bar to filter clients by name or birthDate.
  - **Table / List**:
    - Displays: Name, Birthdate, Date Registered, Latest Counseling Applied.
    - **Clicking a Client Name**: Opens a sliding side-drawer or detail modal showing:
      - Client's personal details.
      - **상담 신청 내역 (Counseling History)**: List of all counseling types this client has submitted, with submission dates.
      - **상담 배정/진행 필드**: An admin can manually assign/select a new counseling type for this client right from the detail drawer and save it (adds a new Counseling Record).

- **Tab 2: 심리상담 관리 (Counseling Management)**:
  - Lists all counseling types.
  - Admins can:
    - **Add New Counseling Type**: Modal to input Title and Description.
    - **Edit**: Modify Title/Description.
    - **Toggle Status**: An ON/OFF switch (or checkbox) to change `isActive` status. Inactive items should not appear on the client selection page.
    - **Delete**: Remove a counseling type (with a warning if records exist).

---

### 4. Interactive Excellence & Polish
- Add simple mock data to LocalStorage on the first load so the app doesn't look empty (e.g., 3-4 registered clients, some sample submission records).
- Responsive Design: Client portal works seamlessly on tablets (often used at reception desks) and mobile. Admin dashboard is optimized for desktop and tablet screens.
- Use nice animations for modal popups, slide-out drawers, and active card selections.
```
