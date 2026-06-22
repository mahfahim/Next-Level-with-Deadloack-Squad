<img width="1070" height="607" alt="image" src="https://github.com/user-attachments/assets/cc602887-42f5-4abe-9ebe-e360a6ac4d7d" />

# Introduction to Prisma

Prisma হলো Node.js এবং TypeScript-এর জন্য একটি আধুনিক ORM (Object Relational Mapping)।

এটি TypeScript/JavaScript Application এবং SQL Database-এর মধ্যে একটি Translator হিসেবে কাজ করে।

Developer সাধারণত TypeScript বা JavaScript ব্যবহার করে Application তৈরি করে, আর Database SQL ভাষা বোঝে। Prisma এই দুইয়ের মধ্যে সংযোগ তৈরি করে এবং TypeScript Code-কে SQL Query-তে রূপান্তর করে Database-এর সাথে যোগাযোগ করে।

---

## Prisma ছাড়া

Database থেকে Data আনতে বা সংরক্ষণ করতে সরাসরি SQL Query লিখতে হয়।

```sql
SELECT * FROM users;
```

```sql
INSERT INTO users(name, email)
VALUES ('Fahim', 'fahim@gmail.com');
```

---

## Prisma ব্যবহার করলে

একই কাজ TypeScript Code দিয়েই করা যায়।

```ts
const users = await prisma.user.findMany();
```

Prisma এই Code-কে প্রয়োজনীয় SQL Query-তে রূপান্তর করে Database-এ পাঠায়।

---

## Prisma কীভাবে কাজ করে

```text
Developer
    |
    | TypeScript / JavaScript
    v
Prisma
    |
    | SQL
    v
Database
```

Developer TypeScript Code লেখে, Prisma সেই Code বুঝে SQL Query তৈরি করে এবং Database থেকে Result এনে Application-এ ফেরত দেয়।

---

## Prisma-এর সুবিধা

### Type Safety

ভুল Field Name বা Data Type ব্যবহার করলে TypeScript Error দেখায়।

```ts
await prisma.user.findUnique({
  where: {
    email: "test@gmail.com"
  }
});
```

---

### Auto Completion

VS Code-এ Model এবং Method-এর Suggestion পাওয়া যায়।

```ts
prisma.user.findMany();
prisma.user.create();
prisma.user.update();
prisma.user.delete();
```

---

### Database Migration

Schema পরিবর্তন করলে সহজে Database Update করা যায়।

```bash
npx prisma migrate dev
```

---

### Schema-Based Development

Database Structure একটি Schema File-এ Define করা যায়।

```prisma
model User {
  id    Int    @id @default(autoincrement())
  name  String
  email String @unique
}
```

---

## উদাহরণ

ধরো `Food` নামে একটি Table আছে।

Prisma দিয়ে নতুন Food যোগ করা:

```ts
await prisma.food.create({
  data: {
    name: "Burger",
    price: 120
  }
});
```

Prisma এই Code-কে SQL Query-তে রূপান্তর করে Database-এ Execute করবে।

---

## সংক্ষেপে

Prisma হলো একটি ORM, যা TypeScript/JavaScript Application এবং SQL Database-এর মধ্যে Translator হিসেবে কাজ করে। এটি SQL Query লেখার ঝামেলা কমায়, Type Safety প্রদান করে এবং Database Management সহজ করে।
