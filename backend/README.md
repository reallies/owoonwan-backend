# Kakao Auth Backend

FastAPI backend for Kakao OAuth (PM-OHS-1 ~ PM-OHS-4).

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
# Edit .env: set KAKAO_CLIENT_ID, KAKAO_REDIRECT_URI (and optionally KAKAO_CLIENT_SECRET)
```

## .env 
```bash
# Kakao OAuth
KAKAO_CLIENT_ID=your_kakao_rest_apikey
KAKAO_REDIRECT_URI=http://localhost:8000/kakao-authentication/request-access-token-after-redirection
```
## .gitginore
```bash
.env
.idea
.venv
.DS_Store
```
## Run

```bash
python -m main
```

- Health: `GET /health`
- OAuth link: `GET /kakao-authentication/request-oauth-link`
- Token after redirect: `GET /kakao-authentication/request-access-token-after-redirection?code=...`
- User info: `GET /kakao-authentication/user-info?access_token=...` or `Authorization: Bearer <token>`
