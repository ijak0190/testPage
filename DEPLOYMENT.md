# 배포 가이드

## 🚀 Vercel 배포 (가장 추천)

### 방법 1: GitHub 연동 (권장)

1. **GitHub에 프로젝트 업로드**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/your-username/your-repo-name.git
   git push -u origin main
   ```

2. **Vercel 배포**
   - [vercel.com](https://vercel.com) 접속
   - "Sign Up" → GitHub 계정으로 로그인
   - "Add New Project" 클릭
   - GitHub 저장소 선택
   - 자동으로 설정 감지 (Next.js)
   - "Deploy" 클릭
   - 완료! 🎉

### 방법 2: Vercel CLI 사용

```bash
# Vercel CLI 설치
npm i -g vercel

# 배포
vercel

# 프로덕션 배포
vercel --prod
```

### Vercel 무료 플랜 제한
- ✅ 무제한 프로젝트
- ✅ 자동 HTTPS
- ✅ 커스텀 도메인
- ✅ 자동 배포 (Git push 시)
- ⚠️ 대역폭: 100GB/월
- ⚠️ 빌드 시간: 6000분/월
- ⚠️ 서버리스 함수: 100GB-시간/월

---

## 🌐 Netlify 배포

### 방법
1. [netlify.com](https://netlify.com) 접속
2. GitHub 계정으로 로그인
3. "Add new site" → "Import an existing project"
4. GitHub 저장소 선택
5. 빌드 설정:
   - Build command: `npm run build`
   - Publish directory: `.next`
6. "Deploy site" 클릭

### Netlify 무료 플랜
- ✅ 100GB 대역폭/월
- ✅ 300분 빌드 시간/월
- ✅ 자동 HTTPS

---

## 🚂 Railway 배포

### 방법
1. [railway.app](https://railway.app) 접속
2. GitHub 계정으로 로그인
3. "New Project" → "Deploy from GitHub repo"
4. 저장소 선택
5. 자동 배포 시작

### Railway 무료 플랜
- ✅ $5 크레딧/월 (자동 충전)
- ✅ 무제한 프로젝트
- ⚠️ 사용량에 따라 과금

---

## 📦 Render 배포

### 방법
1. [render.com](https://render.com) 접속
2. GitHub 계정으로 로그인
3. "New" → "Web Service"
4. GitHub 저장소 선택
5. 설정:
   - Build Command: `npm install && npm run build`
   - Start Command: `npm start`
6. "Create Web Service" 클릭

### Render 무료 플랜
- ✅ 무료 SSL
- ✅ 자동 배포
- ⚠️ 15분 비활성 시 슬리프 모드
- ⚠️ 슬리프 모드에서 깨어나는데 시간 소요

---

## 🎯 추천 순서

1. **Vercel** - Next.js에 최적화, 가장 쉬움
2. **Netlify** - 좋은 대안
3. **Railway** - 더 많은 제어 필요
4. **Render** - 슬리프 모드 주의

---

## 📝 배포 전 체크리스트

- [ ] `package.json`에 빌드 스크립트 확인
- [ ] 환경 변수 확인 (필요시)
- [ ] `.env.local` 파일은 `.gitignore`에 포함
- [ ] 빌드 테스트: `npm run build`
- [ ] 프로덕션 테스트: `npm start`

---

## 🔧 환경 변수 설정

Vercel/Netlify 등에서 환경 변수가 필요하면:

1. 대시보드 → Project Settings → Environment Variables
2. 변수 추가
3. 재배포

---

## 💡 팁

- Vercel은 Next.js를 만든 회사라 가장 최적화되어 있습니다
- GitHub에 코드를 올리면 자동 배포가 가능합니다
- 커스텀 도메인도 무료로 연결 가능합니다
- Analytics는 이미 `@vercel/analytics`가 설치되어 있어 자동 작동합니다

