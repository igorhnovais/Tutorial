sudo -i -u postgres
sudo -i -u postgres pg_dump shortly > dump.sql

psql

CREATE DATABASE banco

ou

\c banco   -- entra no banco

CREATE TABLE users(
	id SERIAL PRIMARY KEY,
    name TEXT ou VARCHAR(50) UNIQUE,
    data DATE DEFAULT NOW(),
    active BOOLEAN DEFAULT FALSE,
    numero DECIMAL,
    price INTEGER NOT NULL
    UserId INTEGER NOT NULL REFERENCES "products"("id"),
    datePosted TIMESTAMP DEFAULT NOW()
)

DROP TABLE users

ALTER TABLE users ADD CONSTRAINT 

SELECT * FROM receitas

INSERT INTO receitas (titulo, preparo) VALUES (oi, tchau)

\q --
exit -- ^ pra sair do banco

\! clear -- pra limpar

---
avg() - media
min() - menor
max() - maior
sum() - soma
count() - quantidade

---
sudo -i -u postgres pg_dump NomeBanco > dump.sql

