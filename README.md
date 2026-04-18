# Hyewon Lee — Personal Homepage

개인 홈페이지 파일 묶음입니다. GitHub Pages에 무료로 호스팅하면 `https://2noweyh.github.io` 주소로 누구나 볼 수 있게 됩니다.

## 📁 파일 구성

```
homepage/
├── index.html     ← 메인 홈페이지 (단일 파일, 이것만 있으면 돌아감)
├── profile.jpg    ← (선택) 프로필 사진 — 이 파일명으로 폴더에 넣으면 자동 사용됨
└── README.md      ← 이 파일
```

> 📷 **프로필 사진**: `profile.jpg` 라는 이름으로 이 폴더에 넣어주세요. 파일이 없으면 GitHub 아바타로 자동 fallback 됩니다.

## 🚀 GitHub Pages 배포 방법 (5분 소요)

### 1단계 — 레포지토리 생성

1. GitHub에 로그인한 상태에서 [github.com/new](https://github.com/new) 로 이동
2. **Repository name**: `2noweyh.github.io` 로 정확히 입력 (본인 GitHub 아이디와 같아야 함)
3. **Public** 선택 (GitHub Pages 무료 사용을 위해)
4. "Create repository" 클릭

### 2단계 — 파일 업로드

**방법 A — 웹에서 바로 업로드 (간단)**

1. 방금 만든 레포 페이지에서 "uploading an existing file" 링크 클릭
2. `index.html` 과 `profile.jpg` 를 드래그해서 업로드
3. 아래 "Commit changes" 버튼 클릭

**방법 B — Git 명령어로 (익숙하면)**

```bash
cd "homepage 폴더 위치"
git init
git add index.html profile.jpg
git commit -m "Initial homepage"
git branch -M main
git remote add origin https://github.com/2noweyh/2noweyh.github.io.git
git push -u origin main
```

### 3단계 — GitHub Pages 활성화

1. 레포 페이지 상단 "Settings" 탭 클릭
2. 왼쪽 메뉴 "Pages" 클릭
3. "Build and deployment" 섹션에서
   - **Source**: `Deploy from a branch`
   - **Branch**: `main` / `/ (root)` 선택
4. "Save" 클릭
5. **약 1~2분 기다린 후** `https://2noweyh.github.io` 접속 → 홈페이지가 뜨면 끝!

> Settings → Pages 페이지 상단에 "Your site is live at ..." 녹색 박스가 뜨면 배포 성공입니다.

## 🌍 커스텀 도메인 (선택)

나중에 `hyewonlee.com` 같은 도메인을 사야 한다면:

1. 도메인 구매 (가비아, Namecheap, Cloudflare 등)
2. 레포 루트에 `CNAME` 파일 생성 후 도메인 이름만 기입 (예: `hyewonlee.com`)
3. 도메인 DNS 관리 페이지에서 `A` 레코드 4개를 GitHub IP로 설정:
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```
4. Settings → Pages → Custom domain 에 도메인 입력

## ✏️ 업데이트 / 수정 방법

`index.html` 은 단일 파일이라 원하는 대로 수정할 수 있습니다.

### 자주 건드릴 섹션

| 찾을 것 | 설명 |
|---|---|
| `<!-- =============== NEWS ===============` | 최신 소식 타임라인 — 새 논문 accept, 수상 등 추가 |
| `<!-- PUB 1 -->` ~ `<!-- PUB 9 -->` | 논문 카드 (맨 위가 최신) |
| `<!-- =============== AWARDS ===============` | 수상·장학 |
| `hyewon@kaeri.re.kr` | 이메일 주소 변경 시 |

### 프로필 사진 교체

1. 교체할 사진을 `profile.jpg` 로 이 폴더에 저장 (덮어쓰기)
2. `git push` 또는 GitHub 웹에서 재업로드
3. 1~2분 후 자동 반영

> 참고: HTML의 `<img src="profile.jpg">` 는 파일이 없으면 `https://avatars.githubusercontent.com/u/136467288?v=4` 로 fallback 됩니다.

### 수정 후 반영

- **방법 A**: GitHub 웹에서 `index.html` 파일 열고 연필 아이콘으로 직접 수정 → Commit
- **방법 B**: 로컬에서 수정 후 `git push`
- 1~2분 후 자동 배포됨

## 🎨 디자인 변경 팁

`index.html` 상단 `tailwind.config` 블록에서 색상을 조정할 수 있습니다:

```javascript
colors: {
  brand: {
    700: '#1a38dd',  // ← 메인 포인트 색 (링크, 버튼)
    ...
  }
}
```

- 파란색 대신 다른 색 원하면 [tailwindcss.com/docs/customizing-colors](https://tailwindcss.com/docs/customizing-colors) 에서 hex 코드 찾아서 바꿔주세요.
- 글꼴도 상단 `fontFamily` 에서 바꿀 수 있습니다.

## 🧪 로컬 미리보기

수정하기 전에 로컬에서 먼저 확인하고 싶다면:

```bash
# Python이 있다면
cd homepage
python3 -m http.server 8000
# 브라우저에서 http://localhost:8000 접속
```

또는 그냥 `index.html` 파일을 브라우저로 열어도 거의 동일하게 나옵니다.

## 📢 홈페이지 홍보 팁

완성되면 이런 곳에 링크를 추가하면 좋아요:

- **이메일 서명**: `Hyewon Lee | 2noweyh.github.io`
- **논문 저자 소개**: `https://2noweyh.github.io`
- **학회 발표 슬라이드 마지막**
- **LinkedIn / 명함 QR 코드**
- **Google Scholar 프로필의 "Homepage" 필드**

---

문제 있으면 `index.html` 을 다시 수정해서 push하면 됩니다. 모든 스타일은 CDN Tailwind로 불러오므로 빌드 과정 불필요 ✨
