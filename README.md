# 감자튀김 짬뽕전형 원서 — GitHub Pages + Supabase

Google Apps Script와 Netlify 없이 운영하는 스타터 프로젝트입니다.

## 포함 파일
- `index.html`: 공개 지원서 및 관리자 로그인/명단 관리 화면
- `fries-holder.png`: 빨간 감자튀김 홀더 이미지
- `supabase_setup.sql`: 데이터베이스 테이블과 접근 정책

## 1. Supabase 설정
1. https://supabase.com 에서 새 프로젝트를 만듭니다.
2. SQL Editor에서 `supabase_setup.sql` 전체를 실행합니다.
3. Project Settings → API에서 Project URL과 anon/public key를 복사합니다.
4. `index.html`에서 `YOUR_SUPABASE_PROJECT_URL`, `YOUR_SUPABASE_ANON_KEY`를 실제 값으로 교체합니다.
   **service_role 또는 secret key는 절대 HTML에 넣지 마세요.**

## 2. 관리자 계정
Supabase → Authentication → Users에서 운영자 계정을 생성합니다. 관리자 로그인은 Supabase Auth 이메일/비밀번호를 사용합니다. RLS 정책으로 비로그인 사용자는 명단을 조회할 수 없고, 인증된 사용자는 조회/삭제할 수 있습니다. 관리자 계정은 신뢰하는 운영자에게만 발급하세요.

## 3. GitHub Pages 게시
1. GitHub에서 새 저장소(repository)를 만듭니다(예: `gamjatwig-application`).
2. `index.html`, `fries-holder.png`, `supabase_setup.sql`, `README.md`를 저장소 최상위에 업로드합니다.
3. 저장소 Settings → Pages → Build and deployment에서 `Deploy from a branch`를 선택합니다.
4. Branch `main`, folder `/(root)`를 선택하고 Save를 누릅니다.
5. 게시가 끝나면 `https://사용자명.github.io/저장소명/` 형태의 주소를 공유합니다.

GitHub Pages는 정적 호스팅이므로 다중 사용자 저장은 Supabase가 담당합니다. 실제 접수를 시작하기 전에 테스트 제출과 관리자 로그인을 확인하세요.
