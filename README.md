# 피드백 게시판 (feedback.html)

이름 / 페이지 / 피드백 내용을 입력받아, **누가 어떤 기기·브라우저에서 작성하든**
모두 같은 메인 목록에 모여서 보이는 공유형 피드백 게시판입니다.

## 사용 방법

1. `feedback.html`을 웹 서버(GitHub Pages 등)에 올리거나 로컬에서 바로 엽니다.
2. 처음 한 번은 Firebase 설정이 필요합니다. 페이지 상단의 **"⚙️ 처음 사용 전 설정 방법"**을
   펼쳐서 순서대로 진행하세요. 요약하면:
   1. [Firebase 콘솔](https://console.firebase.google.com/)에서 무료 프로젝트 생성
   2. Build → Realtime Database 생성
   3. Rules 탭에서 `feedbacks` 경로에 대해 읽기/쓰기 허용
   4. 웹 앱 등록 후 발급되는 `firebaseConfig` 값을 `feedback.html` 안의
      `firebaseConfig` 객체에 붙여넣기
3. 설정이 끝나면 폼에 이름 / 페이지 / 피드백 내용을 입력하고 등록 버튼을 누르면
   실시간으로 메인 목록에 추가되고, 다른 사람이 봐도 동일하게 보입니다.

## 왜 Firebase를 사용하나요?

이 프로젝트에는 별도의 백엔드 서버가 없습니다. 브라우저 `localStorage`만 쓰면
작성한 기기에서만 내용이 남고 다른 사람에게는 보이지 않기 때문에, 서버 코드 없이도
여러 사람의 입력을 한 곳에 모을 수 있는 Firebase Realtime Database(무료 티어)를
사용했습니다.

## 보안 참고

예시 Rules(`.read: true, .write: true`)는 설정 편의를 위한 최소 설정입니다.
불특정 다수에게 공개되는 게시판이라면 스팸/악용 방지를 위해 Firebase App Check,
글자 수 제한, 간단한 인증 등을 추가로 검토하는 것을 권장합니다.
