### Boring official defination

ORM stands for Object-Relational Mapping, a programming technique used in software development to convert data between incompatible type systems in object-oriented programming languages. This technique creates a "virtual object database" that can be used from within the programming language.

ORMs are used to abstract the complexities of the underlying database into simpler, more easily managed objects within the code

### [](https://projects.100xdevs.com/tracks/gZf9uBBNSbBR7UCqyyqT/prisma-1#7678e97e961d43429d058e46f00a6ed6 "2. Easier to digest defination")2. Easier to digest defination

ORMs let you easily interact with your database without worrying too much about the underlying syntax (SQL language for eg)

# Step 2 - Why ORMs?

### [](https://projects.100xdevs.com/tracks/gZf9uBBNSbBR7UCqyyqT/prisma-2#41656f7190304937b627897d6ba64e1e "1. Simpler syntax (converts objects to SQL queries under the hood)")1. Simpler syntax (converts objects to SQL queries under the hood)
### 2. Abstraction that lets you flip the database you are using. Unified API irrespective of the DB
###  3. Type safety/Auto completion
### 4. Automatic migrations

In case of a simple Postgres app, it’s very hard to keep track of all the commands that were ran that led to the current schema of the table.

CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100) UNIQUE NOT NULL
);

ALTER TABLE users
ADD COLUMN phone_number VARCHAR(15);
As your app grows, you will have a lot of these `CREATE` and `ALTER` commands.

ORMs (or more specifically Prisma) maintains all of these for you.

For example -[https://github.com/code100x/cms/tree/main/prisma/migrations](https://github.com/code100x/cms/tree/main/prisma/migrations)

# Step 3 - What is Prisma
it is a node JS  and TS specific ORM
### 1. Data model

In a single file, define your schema. What it looks like, what tables you have, what field each table has, how are rows related to each other.

### 2. Automated migrations

Prisma generates and runs database migrations based on changes to the Prisma schema.

###  3. Type Safety

Prisma generates a type-safe database client based on the Prisma schema.
### 4.Auto-Completion



[[PrismaAccelerate]]