git clone

npm init -y
- "type": module
- ("script": {
  "dev": "nodemon src/server.ts",
  "start": "node src/server.ts",
  "build": "tsc src/server.ts",
  "prisma:seed": "npx prisma db seed",
  "test":"npx dotenv -e .env.test npx jest -- --forceExit",
  "coverage": "npm run test -- --coverage"
  }
- ("prisma":{
	"seed": "ts-node prisma/seed.ts"
  }
  

npm i express pg cors mongodb dotenv dotenv-expand dotenv-cli joi bcrypt uuid http-status @faker-js/faker ;
 
npm i -D nodemon typescript @types/express @types/node @types/cors @types/pg ts-node @prisma/client @types/bcrypt @types/uuid

tsconfig.json
{
	"compilerOptions":{
    	"outDir": "dist",
        "esModuleInterop": true,
        "module": "es6",
        "moduleResolution": "Node"
    },
    "ts-node": {
    	"esm": true
    }
}

faz o arquivo "server.ts"

npx prisma init
DATABASE_URL=postgres://postgres:12345@localhost:5432/groupbank

npx prisma db pull - trazer o banco
npx prisma generate - conectar com o banco

npx prisma migrate dev - trazer a pasta migrations e commitar as mudanças das  tabelas

npx nodemon src/server.ts

---
SE O PROJETO JA ESTIVER RODANDO

npx prisma init - ai configura o env
npx prisma db pull
npx prisma generate
