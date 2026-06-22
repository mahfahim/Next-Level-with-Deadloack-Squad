<img width="1086" height="603" alt="image" src="https://github.com/user-attachments/assets/eb8929ea-2fe7-456b-a577-4b384018b602" />
<img width="1090" height="612" alt="image" src="https://github.com/user-attachments/assets/43c4a117-dce1-4869-a136-fcd6e8a3bfad" />
<img width="1045" height="639" alt="image" src="https://github.com/user-attachments/assets/12aade86-4f4a-419b-9cc0-5dcc1aa457f4" />
<img width="1100" height="632" alt="image" src="https://github.com/user-attachments/assets/2a64b4bc-0319-4f5b-8131-a4fea015fd18" />



### Prisma ORM কী?

Prisma হলো আধুনিক JavaScript এবং TypeScript অ্যাপ্লিকেশনের জন্য একটি ওপেন-সোর্স ORM (Object-Relational Mapper)। Next.js বা Node.js এর মতো টেকনোলজি ব্যবহার করে ফুল-স্ট্যাক ডেভেলপমেন্ট করার সময় ডাটাবেসের সাথে যোগাযোগ করার জন্য এটি একটি অত্যাধুনিক টুলকিট। এটি মূলত ডাটাবেসের সাথে কাজ করাকে অনেক সহজ, নিরাপদ এবং ডেভেলপার-বান্ধব করে তোলে।

### ORM কীভাবে কাজ করে?

ORM বা Object-Relational Mapping এর কাজ হলো আপনাকে সরাসরি ডাটাবেসের ভাষা বা Raw SQL (যেমন SELECT, INSERT, UPDATE) লেখার বদলে সাধারণ অবজেক্ট-ওরিয়েন্টেড কোড ব্যবহার করে ডাটাবেস পরিচালনা করার সুবিধা দেওয়া।

আপনার অ্যাপ্লিকেশন সরাসরি ডাটাবেসের সাথে কথা বলতে পারে না। Prisma এখানে একটি মাধ্যম হিসেবে কাজ করে। আপনি আপনার পরিচিত জাভাস্ক্রিপ্ট বা টাইপস্ক্রিপ্ট দিয়ে কমান্ড লিখবেন, আর Prisma সেটিকে স্বয়ংক্রিয়ভাবে SQL-এ রূপান্তর করে ডাটাবেসে পাঠাবে এবং ডাটাবেস থেকে সঠিক ফলাফল আপনাকে ফেরত দেবে।

**উদাহরণস্বরূপ পার্থক্যটি দেখুন:**

Raw SQL ব্যবহার করলে আপনাকে লিখতে হতো:

```sql
SELECT * FROM users
WHERE email = 'john@example.com' AND age > 18
ORDER BY name ASC;

```

কিন্তু Prisma ORM ব্যবহার করলে আপনি অবজেক্ট হিসেবে খুব সহজেই লিখতে পারবেন:

```javascript
const users = await prisma.user.findMany({
  where: {
    email: 'john@example.com',
    age: { gt: 18 }
  },
  orderBy: { name: 'asc' }
})

```

### Prisma এর প্রধান বৈশিষ্ট্যসমূহ

* **টাইপ-সেফ কোয়েরি (Type-Safe Queries):** Prisma ব্যবহার করার সবচেয়ে বড় সুবিধা হলো এটি পুরোপুরি টাইপ-সেফ। আপনি যখন কোড লিখবেন, তখন এটি অটো-কমপ্লিট সাজেশন দেবে এবং কোড রান করার আগেই (compile-time) সম্ভাব্য ভুলগুলো ধরিয়ে দেবে।
* **যেকোনো ডাটাবেসের সাথে ব্যবহারযোগ্য (Database Agnostic):** এটি নির্দিষ্ট কোনো একটি ডাটাবেসের ওপর নির্ভরশীল নয়। আপনি একই Prisma কোড ব্যবহার করে PostgreSQL, MySQL, SQLite, MongoDB এবং SQL Server-এর মতো বিভিন্ন ডাটাবেসের সাথে কাজ করতে পারবেন।
* **ডেভেলপার-বান্ধব (Developer-First):** এর ডাটাবেস স্কিমা পড়া এবং বোঝা মানুষের জন্য খুব সহজ। এছাড়া এটি ডাটাবেস মাইগ্রেশন স্বয়ংক্রিয়ভাবে তৈরি করতে পারে, যা প্রোডাকশন-লেভেল অ্যাপ্লিকেশনের জন্য খুবই উপকারী।

সংক্ষেপে, জটিল SQL স্টেটমেন্ট মুখস্থ রাখা বা লেখার ঝামেলা থেকে মুক্তি দিয়ে ডাটাবেস অপারেশনকে দ্রুত ও নির্ভুল করার জন্যই Prisma ORM ব্যবহার করা হয়।


