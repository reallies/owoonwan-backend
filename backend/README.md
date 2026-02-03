# Kakao Auth Backend

FastAPI backend for Kakao OAuth (PM-OHS-1 ~ PM-OHS-4).

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
cp .env.example .env
# Edit .env: set KAKAO_CLIENT_ID, KAKAO_REDIRECT_URI (and optionally KAKAO_CLIENT_SECRET)
```

## Run

```bash
uvicorn main:app --reload
```

- Health: `GET /health`
- OAuth link: `GET /kakao-authentication/request-oauth-link`
- Token after redirect: `GET /kakao-authentication/request-access-token-after-redirection?code=...`
- User info: `GET /kakao-authentication/user-info?access_token=...` or `Authorization: Bearer <token>`
