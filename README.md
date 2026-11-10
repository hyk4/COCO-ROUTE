# COCO-ROUTE

이동 수단별 탄소 발자국을 기록하고, 친환경 활동 정보를 나누는 Android 앱입니다.

## 주요 기능

| 화면 | 설명 |
| --- | --- |
| 로그인 / 회원가입 / 비밀번호 찾기 | Firebase Authentication 기반 이메일 로그인, 가입 시 Firestore `users` 컬렉션에 사용자 정보 저장 |
| 메인 | 도보·자전거·자동차·버스·지하철·기차 버튼을 누르면 수단별 탄소 배출 값이 누적되어 표시 |
| 상점 | 포인트(마이 코코)로 교환 가능한 상품 목록, 상품 검색, 오늘의 상품·추천 상품, 상품 상세 |
| 기업 | 주요 기업 8곳의 소개와 탄소 배출 그래프, 기업명 검색 |
| 커뮤니티 | 인기 글 목록, 전체 글 보기, 글 작성·수정·삭제, 댓글 작성·수정·삭제, 추천, 친환경 관련 블로그 링크 |
| 이용 안내 | 상점·포인트·커뮤니티 FAQ와 탄소 줄이기 실천 방안 |

## 기술 스택

- Kotlin, Android (AppCompat, RecyclerView, Material Components)
- Firebase Authentication, Cloud Firestore
- Kotlin Coroutines

## 파일 구성

현재 저장소에는 소스 파일이 폴더 구분 없이 루트에 올라가 있습니다.

- `*.kt`: 화면(Activity)과 RecyclerView 어댑터
  - `Login`, `SignUp`, `ForgotPassword`: 인증
  - `MainActivity`: 탄소 발자국 기록 및 메뉴 이동
  - `ProductMain`, `ProductDetail`: 상점
  - `CompanyMain`, `CompanyDetail`: 기업 정보
  - `CommuMain`, `Viewfull`, `NewPost`, `PostDetail`, `EditPost`, `EditComment`, `PostAdapter`, `CommentAdapter`: 커뮤니티
  - `FAQMain`: 이용 안내
- `*.xml`: 각 화면과 리스트 아이템의 레이아웃
- `gitignore.txt`: Android 프로젝트용 gitignore

## 실행 방법

1. Android Studio에서 새 프로젝트(패키지명 `com.example.myapplication`)를 만들고, `.kt` 파일은 `app/src/main/java/com/example/myapplication/`에, `.xml` 파일은 `app/src/main/res/layout/`에 넣습니다.
2. Firebase 프로젝트를 만들어 `google-services.json`을 `app/`에 추가하고, Authentication(이메일/비밀번호)과 Firestore를 활성화합니다.
3. 빌드 후 실행합니다.

> 참고: 코드가 참조하는 `data.FirestoreService`, `Post` 등 데이터 클래스와 `AndroidManifest.xml`, Gradle 설정, 이미지·문자열 리소스는 이 저장소에 포함되어 있지 않습니다.
