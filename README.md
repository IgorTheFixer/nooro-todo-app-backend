### 1. Install Dependencies
```sh
npm i
```

### 2. Create .env file with DATABASE_URL
```js
DATABASE_URL=''
```
Replace the empty string with the database connection string from your mysql provider

### 3. Initiate Prisma
```sh
npx prisma generate
npx prisma db push
```





