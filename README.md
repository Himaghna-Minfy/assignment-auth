
# Secret Quote API

A simple Node.js + Express backend that demonstrates stateless authentication using JSON Web Tokens (JWT).

---

## 📦 Setup

1️⃣ Clone the repository:
```bash
git clone <your-repo-url>
cd secret-quote-api
```
2️⃣ Install dependencies:

```bash
npm install
```
3️⃣ Start the server:

```bash
node index.js
```
or if you’ve added a script:

```bash
npm start
```
🚀 API Endpoints
📌 POST /register
➡ Register a new user.

Body (JSON):

```json
{
  "username": "user1",
  "password": "pass1"
}
```

```json
{
  "message": "User registered successfully!"
}
```
📌 POST /login
➡ Login with credentials and receive a JWT token.

Body (JSON):

```json
{
  "username": "user1",
  "password": "pass1"
}
```
```json
{
  "accessToken": "YOUR_JWT_TOKEN_HERE"
}
```
📌 GET /api/secret-quote
➡ A protected route. Requires a valid JWT.

Headers:

```
Authorization: Bearer YOUR_JWT_TOKEN_HERE
```
```json
{
  "quote": "The secret to getting ahead is getting started."
}
```
If no or invalid token:

401 Unauthorized
or

403 Forbidden
🧪 How to Test (Postman or curl)
Register:
```bash
curl -X POST http://localhost:3000/register \
-H "Content-Type: application/json" \
-d '{"username":"user1","password":"pass1"}'
```
Login:
```bash
curl -X POST http://localhost:3000/login \
-H "Content-Type: application/json" \
-d '{"username":"user1","password":"pass1"}'
```
Access Secret Quote:
```bash
curl -X GET http://localhost:3000/api/secret-quote \
-H "Authorization: Bearer YOUR_JWT_TOKEN_HERE"
```

![image](https://github.com/user-attachments/assets/ab549449-e1c2-48dd-8f07-b445f9e65c24)

![image](https://github.com/user-attachments/assets/a94b363f-c640-4298-8488-75b1e13f342f)

![image](https://github.com/user-attachments/assets/eb923fd0-f0c4-4bcd-a2b8-3ee60dad10d2)
