# Express Server with TypeScript and Prisma

This guide walks you through setting up an Express server using TypeScript and Prisma for database management.

## Prerequisites
- Node.js installed
- npm (Node Package Manager) installed

## Setup Steps

### 1. Initialize a New Node.js Project in a New Repository from the Command Line
```sh
mkdir ts-express-prisma
cd ts-express-prisma
npm init -y
```
This creates a `package.json` file with default settings.

### 2. Install Express and TypeScript Dependencies
```sh
npm install express
npm install -D typescript ts-node @types/express@4
```

### 3. Initialize TypeScript Configuration
```sh
npx tsc --init
```
This generates a `tsconfig.json` file for TypeScript configuration. Below is the configuration being used:

```json
{
  "compilerOptions": {
    "target": "ES6",
    "module": "commonjs",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true,
    "forceConsistentCasingInFileNames": true,
    "outDir": "./dist"
  },
  "include": ["src/**/*.ts"],
  "exclude": ["node_modules"]
}
```

### 4. Create a src folder, then a `index.ts` File and Run the Server
1. Create an `index.ts` file with the following content:
```ts
import express from 'express';

const app = express();
const PORT = process.env.PORT || 3000;

app.use(express.json());

app.get('/', (req, res) => {
    res.send('Hello, Express with TypeScript!');
});

app.listen(PORT, () => {
    console.log(`Server is running on port ${PORT}`);
});
```

2. Add necessary scripts to `package.json`:
```json
"scripts": {
    "build": "tsc",
    "start": "node dist/index.js",
    "dev": "ts-node src/index.ts"
  },
```

3. Run the server:
```sh
npm run dev
```
### 5. Install Prisma and Set Up Database
```sh
npm install prisma @prisma/client
```

### 6. Initialize Prisma
```sh
npx prisma init --datasource-provider mysql
```
This creates a `prisma` directory and a `.env` file for database connection settings with a mysql provider. You will be able to connect to your mysql database by providing your database's connection string.

```js
DATABASE_URL=''
```

### 7. Generate Prisma Client and Push Schema to Database
```sh
npx prisma generate
npx prisma db push
```
### 8. Create the Desired API Routes in the index.ts file

## Your Express Server with TypeScript and Prisma is Ready! 🎉
You can now build and expand your API by adding more routes, controllers, and database models using Prisma.




