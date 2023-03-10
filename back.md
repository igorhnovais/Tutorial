USANDO MONGO

git clone

npm init -y
- "type": module
- (script)
- "dev": "nodemon index.js",
- "start": "node src/server.js"
npm i express cors mongodb dotenv joi;
npm i -D nodemon;
bcrypt; embaralhar senha
uuid; gerar string no token
nanoid; gerar um url pequena

roda o  - mongod --dbpath ~/.mongo
depois o - mongo (se quiser mexer no bd)
depois o - npm run dev

---
USANDO POSTGRES

npm init -y
- "type": module
- (script)"dev": "nodemon src/server.js"

npm i pg express cors dotenv joi
npm i -D nodemon;

sudo su -c "pg_dump NOME_DO_BANCO --inserts --no-owner" postgres > dump.sql


