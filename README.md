# next_level_assignment_2

# ১. PostgreSQL কী?

PostgreSQL হলো একটি অত্যন্ত শক্তিশালী এবং উন্নত রিলেশনাল ডাটাবেস ম্যানেজমেন্ট সিস্টেম (RDBMS), যা স্ট্রাকচারড কুয়েরি ল্যাঙ্গুয়েজ (SQL) ব্যবহার করে ডেটা সংরক্ষণ, পরিচালনা এবং পুনরুদ্ধার করতে ব্যবহৃত হয়। এটি একটি ওপেন-সোর্স ডাটাবেস, অর্থাৎ এটি সম্পূর্ণ বিনামূল্যে এবং এর সোর্স কোড যে কেউ ডাউনলোড করে পরিবর্তন বা কাস্টমাইজ করতে পারে। PostgreSQL-এর উৎপত্তি ১৯৮৬ সালে ক্যালিফোর্নিয়া বিশ্ববিদ্যালয়ে শুরু হয়েছিল এবং এটি এখন বিশ্বের সবচেয়ে জনপ্রিয় এবং নির্ভরযোগ্য ডাটাবেস সিস্টেমগুলোর একটি।

PostgreSQL-এর মাধ্যমে আপনি বিভিন্ন ধরনের ডেটা সংরক্ষণ করতে পারেন, যেমন টেক্সট, নাম্বার, তারিখ, এবং এমনকি জটিল ডেটা ফরম্যাট যেমন JSON, XML বা জিওস্পেশিয়াল ডেটা। এটি শুধুমাত্র রিলেশনাল ডেটা নয়, বরং নন-রিলেশনাল (NoSQL) ডেটাও সাপোর্ট করে, যা এটিকে অত্যন্ত বহুমুখী করে তোলে। উদাহরণস্বরূপ, এই অ্যাসাইনমেন্টে আমরা `rangers`, `species`, এবং `sightings` টেবিল তৈরি করেছি, যেখানে রিলেশনাল ডেটা ফরেন কী এবং প্রাইমারি কী দিয়ে সংযুক্ত করা হয়েছে।

PostgreSQL-এর কিছু উল্লেখযোগ্য বৈশিষ্ট্য হলো:

- **রিলায়েবল (reliable)**: এটি ডেটা ইন্টেগ্রিটি এবং সঠিকতা নিশ্চিত করে। উদাহরণস্বরূপ, এটি ACID (Atomicity, Consistency, Isolation, Durability) ট্রানজ্যাকশন সমর্থন করে, যা ডেটা হারানো বা দূষিত হওয়ার ঝুঁকি কমায়।
- **নিরাপদ (secure)**: PostgreSQL-এ শক্তিশালী সিকিউরিটি ফিচার রয়েছে, যেমন ইউজার অথেনটিকেশন, এনক্রিপশন, এবং রোল-বেসড অ্যাক্সেস কন্ট্রোল, যা ডেটাকে বাইরের হুমকি থেকে রক্ষা করে।
- **স্কেলযোগ্য (scalable)**: এটি ছোট স্কেলের প্রজেক্ট থেকে শুরু করে বড় এন্টারপ্রাইজ-লেভেল অ্যাপ্লিকেশন পর্যন্ত সহজে ব্যবহার করা যায়। উদাহরণস্বরূপ, Netflix, Instagram, এবং Uber-এর মতো বড় কোম্পানিগুলো তাদের বিশাল ডেটা পরিচালনার জন্য PostgreSQL ব্যবহার করে।
- **কাস্টমাইজেবল**: ডেভেলপাররা নিজেদের প্রয়োজন অনুযায়ী ফাংশন, ট্রিগার, এবং এক্সটেনশন তৈরি করতে পারে।

PostgreSQL-এর আরেকটি বড় সুবিধা হলো এটি বিভিন্ন প্ল্যাটফর্মে (Windows, Linux, macOS) কাজ করে এবং এর কমিউনিটি সাপোর্ট অত্যন্ত শক্তিশালী। এই অ্যাসাইনমেন্টে আমরা PostgreSQL ব্যবহার করে ডাটাবেস তৈরি, টেবিল সেটআপ, এবং বিভিন্ন কুয়েরি (যেমন INSERT, SELECT, UPDATE, DELETE) সম্পাদন করেছি, যা এর ব্যবহারিক প্রয়োগের একটি উদাহরণ।

এটি ওয়েব অ্যাপ্লিকেশন, ডেটা অ্যানালিটিক্স, এবং এমনকি মেশিন লার্নিংয়ের জন্য ডেটা স্টোরেজে ব্যবহৃত হয়। এর বহুমুখিতা এবং শক্তিশালী ফিচার এটিকে আধুনিক ডেটাবেস ম্যানেজমেন্টের জন্য আদর্শ করে তুলেছে।

# ২. প্রাইমারি কী এবং ফরেন কী কনসেপ্ট PostgreSQL-এ কীভাবে কাজ করে?

PostgreSQL-এ প্রাইমারি কী (Primary Key) এবং ফরেন কী (Foreign Key) হলো রিলেশনাল ডাটাবেসের দুটি মৌলিক ধারণা, যা ডাটাবেসের টেবিলগুলোর মধ্যে ডেটার সঠিকতা এবং সম্পর্ক নিশ্চিত করতে ব্যবহৃত হয়। এই দুটি কনসেপ্ট ডাটা ইন্টেগ্রিটি এবং রিলেশনাল স্ট্রাকচার বজায় রাখতে গুরুত্বপূর্ণ ভূমিকা পালন করে। নিচে এদের বিস্তারিত ব্যাখ্যা দেওয়া হলো :

## প্রাইমারি কী (Primary Key)

প্রাইমারি কী হলো একটি টেবিলের এমন একটি কলাম বা কলামের সমষ্টি, যা টেবিলের প্রতিটি রেকর্ড বা রো কে unique ভাবে চিহ্নিত করে। এটি ডাটাবেসে প্রতিটি রেকর্ডের পরিচয় নিশ্চিত করে এবং ডুপ্লিকেট রেকর্ড প্রতিরোধ করে।

### প্রাইমারি কী-এর বৈশিষ্ট্য:

- **ইউনিকনেস (Uniqueness)**: প্রাইমারি কী-এর মান প্রতিটি রেকর্ডের জন্য আলাদা হতে হবে। কোনো দুটি রেকর্ডের প্রাইমারি কী-এর মান একই হতে পারবে না।
- **নট নাল (NOT NULL)**: প্রাইমারি কী কলামে কোনো মান ফাঁকা (NULL) থাকতে পারবে না।
- **একক বা যৌগিক**: এটি একটি কলাম (যেমন, `ranger_id`) বা একাধিক কলামের সমন্বয় (composite key) হতে পারে।

### উদাহরণ (এই অ্যাসাইনমেন্ট থেকে):

এই অ্যাসাইনমেন্টে `rangers` টেবিলে `ranger_id` হলো প্রাইমারি কী। এটি প্রতিটি রেঞ্জারকে uniquely চিহ্নিত করে।

```sql
CREATE TABLE rangers (
    ranger_id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    region VARCHAR(100) NOT NULL
);
```

এখানে:

- `ranger_id` হলো প্রাইমারি কী, যা `SERIAL` টাইপ ব্যবহার করে ১, ২, ৩... এর মতো মান জেনারেট করে।
- এটি নিশ্চিত করে যে প্রতিটি রেঞ্জারের একটি ইউনিক আইডি আছে, এবং কোনো রেকর্ডে `ranger_id` ফাঁকা থাকতে পারবে না।

## ফরেন কী (Foreign Key)

ফরেন কী হলো একটি টেবিলের এমন একটি কলাম বা কলামের সমষ্টি, যা অন্য একটি টেবিলের প্রাইমারি কী বা ইউনিক কী-এর সাথে সম্পর্ক স্থাপন করে। এটি দুটি টেবিলের মধ্যে রিলেশন বা সংযোগ তৈরি করে এবং রেফারেন্সিয়াল ইন্টেগ্রিটি (referential integrity) নিশ্চিত করে।

### ফরেন কী-এর বৈশিষ্ট্য:

- **রেফারেন্সিয়াল ইন্টেগ্রিটি**: ফরেন কী-এর মান অবশ্যই রেফারেন্স করা টেবিলের প্রাইমারি কী-এর মানের সাথে মিলতে হবে, অথবা এটি `NULL` হতে পারে (যদি ফরেন কী-এর জন্য `NOT NULL` বাধ্যতামূলক না হয়)।
- **টেবিলের মধ্যে সম্পর্ক**: ফরেন কী দুটি টেবিলের মধ্যে সম্পর্ক তৈরি করে, যেমন একটি `sightings` টেবিলের রেকর্ড কোন রেঞ্জার বা প্রজাতির সাথে যুক্ত তা নির্দেশ করে।
- **ক্যাসকেডিং অপশন**: ফরেন কী-এর সাথে `ON DELETE CASCADE` বা `ON UPDATE CASCADE` এর মতো অপশন ব্যবহার করে রেফারেন্সড রেকর্ড মুছে গেলে বা আপডেট হলে স্বয়ংক্রিয়ভাবে সম্পর্কিত রেকর্ড আপডেট বা মুছে ফেলা যায়।

### উদাহরণ (এই অ্যাসাইনমেন্ট থেকে):

এই অ্যাসাইনমেন্টে `sightings` টেবিলে দুটি ফরেন কী রয়েছে: `ranger_id` এবং `species_id`। এগুলো যথাক্রমে `rangers` এবং `species` টেবিলের প্রাইমারি কী-এর সাথে যুক্ত।

```sql
CREATE TABLE sightings (
    sighting_id SERIAL PRIMARY KEY,
    ranger_id INTEGER NOT NULL REFERENCES rangers(ranger_id),
    species_id INTEGER NOT NULL REFERENCES species(species_id),
    location VARCHAR(100) NOT NULL,
    sighting_time TIMESTAMP NOT NULL,
    notes TEXT
);
```

এখানে:

- `ranger_id` ফরেন কী হিসেবে `rangers` টেবিলের `ranger_id` (প্রাইমারি কী) কে রেফার করে।
- `species_id` ফরেন কী হিসেবে `species` টেবিলের `species_id` (প্রাইমারি কী) কে রেফার করে।
- `REFERENCES` কীওয়ার্ড দিয়ে ফরেন কী সম্পর্ক স্থাপন করা হয়েছে, এবং `NOT NULL` নিশ্চিত করে যে এই কলামগুলো ফাঁকা থাকতে পারবে না।

## প্রাইমারি কী এবং ফরেন কী-এর মধ্যে সম্পর্ক

প্রাইমারি কী এবং ফরেন কী একসাথে কাজ করে টেবিলগুলোর মধ্যে রিলেশনাল সংযোগ তৈরি করে। উদাহরণস্বরূপ, এই অ্যাসাইনমেন্টে:

- `rangers` টেবিলের `ranger_id` হলো প্রাইমারি কী, যা প্রতিটি রেঞ্জারকে ইউনিকভাবে চিহ্নিত করে।
- `species` টেবিলের `species_id` হলো প্রাইমারি কী, যা প্রতিটি প্রজাতিকে ইউনিকভাবে চিহ্নিত করে।
- `sightings` টেবিলে `ranger_id` এবং `species_id` ফরেন কী হিসেবে এই দুটি টেবিলের সাথে সংযোগ স্থাপন করে। এটি নিশ্চিত করে যে প্রতিটি সাইটিং বৈধ রেঞ্জার এবং প্রজাতির সাথে যুক্ত।

সুতরাং, PostgreSQL-এ প্রাইমারি কী এবং ফরেন কী ব্যবহার করে আমরা ডাটাবেসে ডেটার সঠিকতা, সংগঠন এবং সম্পর্ক নিশ্চিত করতে পারি।

# ৩. VARCHAR এবং CHAR ডাটা টাইপের মধ্যে পার্থক্য কী?

PostgreSQL-এ `VARCHAR` এবং `CHAR` হলো দুটি ডাটা টাইপ যা টেক্সট বা স্ট্রিং ডেটা সংরক্ষণের জন্য ব্যবহৃত হয়। যদিও উভয়ই টেক্সট ডেটা স্টোর করে, তাদের মধ্যে কিছু গুরুত্বপূর্ণ পার্থক্য রয়েছে যা স্টোরেজ, পারফরম্যান্স এবং ব্যবহারের ক্ষেত্রে প্রভাব ফেলে। নিচে এই দুটি ডাটা টাইপের বিস্তারিত তুলনা দেওয়া হলো।

## সংজ্ঞা এবং মৌলিক পার্থক্য

- **CHAR**:
  - `CHAR` হলো নির্দিষ্ট দৈর্ঘ্যের (fixed-length) ডাটা টাইপ। এটি একটি নির্দিষ্ট সংখ্যক ক্যারেক্টার সংরক্ষণের জন্য স্থান বরাদ্দ করে, এবং যদি প্রবেশ করানো ডেটার দৈর্ঘ্য নির্দিষ্ট স্থানের চেয়ে কম হয়, তবে বাকি স্থান ফাঁকা (space) দিয়ে পূর্ণ হয়।
  - উদাহরণ: `CHAR(10)` মানে ঠিক ১০টি ক্যারেক্টারের জন্য স্থান বরাদ্দ করা হবে। যদি আপনি "Hello" (৫ ক্যারেক্টার) স্টোর করেন, তবে বাকি ৫টি স্থান স্পেস (" ") দিয়ে পূর্ণ হবে।
- **VARCHAR**:
  - `VARCHAR` হলো পরিবর্তনশীল দৈর্ঘ্যের (variable-length) ডাটা টাইপ। এটি শুধুমাত্র প্রকৃত ডেটার জন্য স্থান ব্যবহার করে এবং কোনো অতিরিক্ত ফাঁকা স্থান যোগ করে না।
  - উদাহরণ: `VARCHAR(10)` মানে সর্বোচ্চ ১০টি ক্যারেক্টার স্টোর করা যাবে। যদি আপনি "Hello" স্টোর করেন, তবে শুধুমাত্র ৫টি ক্যারেক্টারের জন্য স্থান নেওয়া হবে।

## স্টোরেজের পার্থক্য

- **CHAR**:

  - সবসময় নির্দিষ্ট দৈর্ঘ্যের জন্য স্টোরেজ বরাদ্দ করে। উদাহরণস্বরূপ, `CHAR(10)` সবসময় ১০টি ক্যারেক্টারের জন্য স্থান ব্যবহার করবে, এমনকি যদি ডেটা ছোট হয়।
  - এটি ডিস্কে বেশি স্থান নিতে পারে যদি ডেটা সাধারণত নির্দিষ্ট দৈর্ঘ্যের চেয়ে ছোট হয়।
  - উদাহরণ: "Hello" স্টোর করলে `CHAR(10)` এর জন্য স্থান হবে: `Hello     ` (৫টি ক্যারেক্টার + ৫টি স্পেস)।

- **VARCHAR**:
  - শুধুমাত্র প্রকৃত ডেটার জন্য স্থান ব্যবহার করে, তাই এটি স্টোরেজের দিক থেকে বেশি দক্ষ।
  - উদাহরণ: "Hello" স্টোর করলে `VARCHAR(10)` শুধুমাত্র ৫টি ক্যারেক্টারের জন্য স্থান নেবে। তবে, `VARCHAR`-এর জন্য সামান্য ওভারহেড (overhead) থাকতে পারে কারণ এটি ডেটার দৈর্ঘ্য ট্র্যাক করে।

## পারফরম্যান্স

- **CHAR**:
  - যেহেতু `CHAR` নির্দিষ্ট দৈর্ঘ্যের, তাই ডাটাবেসে ডেটা প্রসেসিং এবং তুলনা করা দ্রুত হতে পারে। এটি ডাটাবেসের জন্য প্রতিটি রেকর্ডের সাইজ পূর্বাভাস করা সহজ করে।
  - যেসব ক্ষেত্রে ডেটার দৈর্ঘ্য সবসময় একই থাকে (যেমন, পোস্টাল কোড, ISO কোড), সেখানে `CHAR` ব্যবহার করা ভালো।
- **VARCHAR**:
  - `VARCHAR`-এর ক্ষেত্রে ডেটার দৈর্ঘ্য পরিবর্তনশীল হওয়ায় ডাটাবেসকে দৈর্ঘ্য ট্র্যাক করতে হয়, যা সামান্য পারফরম্যান্স ওভারহেড সৃষ্টি করতে পারে। তবে আধুনিক ডাটাবেসে এই পার্থক্য নগণ্য।
  - যেসব ক্ষেত্রে ডেটার দৈর্ঘ্য পরিবর্তনশীল (যেমন, নাম, ঠিকানা), সেখানে `VARCHAR` বেশি উপযোগী।

## ব্যবহারের ক্ষেত্র

- **CHAR**:
  - যখন ডেটার দৈর্ঘ্য সবসময় একই থাকে। উদাহরণস্বরূপ, যদি আপনি ২ অক্ষরের কান্ট্রি কোড (যেমন, "US", "BD") স্টোর করেন, তবে `CHAR(2)` উপযুক্ত।
  - উদাহরণ: একটি টেবিলে স্টেট কোড স্টোর করার জন্য `CHAR(2)` ব্যবহার করা যেতে পারে।
- **VARCHAR**:
  - যখন ডেটার দৈর্ঘ্য পরিবর্তনশীল হয়। উদাহরণস্বরূপ, মানুষের নাম, ঠিকানা, বা নোটের মতো ডেটা স্টোর করার জন্য `VARCHAR` বেশি উপযোগী।
  - এই অ্যাসাইনমেন্টে `rangers` টেবিলে `name` এবং `region` কলামে `VARCHAR(100)` ব্যবহৃত হয়েছে, কারণ রেঞ্জারের নাম (যেমন, "Alice Green") এবং রিজিয়ন (যেমন, "Northern Hills") বিভিন্ন দৈর্ঘ্যের হতে পারে।

`CHAR` এবং `VARCHAR` উভয়ই PostgreSQL-এ টেক্সট ডেটা স্টোর করার জন্য উপযোগী, তবে তাদের ব্যবহার নির্ভর করে ডেটার প্রকৃতি এবং অ্যাপ্লিকেশনের প্রয়োজনীয়তার উপর। এই পার্থক্য বোঝা ডাটাবেস ডিজাইনের সময় সঠিক ডাটা টাইপ নির্বাচনের জন্য অত্যন্ত গুরুত্বপূর্ণ, যা ডাটাবেসের পারফরম্যান্স এবং স্টোরেজ দক্ষতাকে প্রভাবিত করে।

# ৪. SELECT স্টেটমেন্টে WHERE ক্লজের উদ্দেশ্য কী?

PostgreSQL-এ `WHERE` ক্লজটি `SELECT` স্টেটমেন্টের সাথে ব্যবহৃত হয় ডাটাবেস থেকে নির্দিষ্ট শর্ত পূরণকারী রেকর্ড ফিল্টার করার জন্য।

### উদ্দেশ্য:

- **ডেটা ফিল্টারিং**: `WHERE` ক্লজ নির্দিষ্ট শর্তের ভিত্তিতে রেকর্ড নির্বাচন করে। উদাহরণস্বরূপ, শুধুমাত্র নির্দিষ্ট লোকেশনের সাইটিং বা নির্দিষ্ট রেঞ্জারের রেকর্ড বের করা।
- **শর্তভিত্তিক নির্বাচন**: এটি যৌক্তিক অপারেটর (`=`, `>`, `<`, `LIKE`, `IN`, ইত্যাদি) ব্যবহার করে ডেটা ফিল্টার করে।
- **কুয়েরি অপ্টিমাইজেশন**: অপ্রয়োজনীয় রেকর্ড বাদ দিয়ে দ্রুত ফলাফল প্রদান করে।

### উদাহরণ (এই অ্যাসাইনমেন্ট থেকে):

প্রবলেম ৩-এ আমরা `WHERE` ক্লজ ব্যবহার করেছি লোকেশনে "Pass" শব্দটি আছে এমন সাইটিং খুঁজতে:

```sql
SELECT *
FROM sightings
WHERE location LIKE '%Pass%';
```

**আউটপুট**:
| sighting_id | species_id | ranger_id | location | sighting_time | notes |
| ------------|------------|-----------|---------------|---------------------|--------|
| 4 | 1 | 2 | Snowfall Pass | 2024-05-18 18:30:00 | (NULL) |

এখানে `WHERE location LIKE '%Pass%'` নিশ্চিত করে যে শুধুমাত্র "Pass" শব্দটি লোকেশনে থাকা রেকর্ডগুলো আউটপুট আসবে।

### সুবিধা:

- নির্দিষ্ট ডেটা দ্রুত বের করা যায়।
- জটিল শর্ত (যেমন, `AND`, `OR`, `NOT`) ব্যবহার করে নির্ভুল ফিল্টারিং সম্ভব।
- ডাটাবেসের পারফরম্যান্স উন্নত করে।

সংক্ষেপে, `WHERE` ক্লজ `SELECT` স্টেটমেন্টকে আরও নির্দিষ্ট এবং কার্যকর করে তোলে, যা এই অ্যাসাইনমেন্টের মতো রিয়েল-ওয়ার্ল্ড ডাটা ফিল্টারিংয়ের জন্য অত্যন্ত গুরুত্বপূর্ণ।

# ৫. UPDATE স্টেটমেন্ট ব্যবহার করে ডেটা কীভাবে পরিবর্তন করা যায়?

PostgreSQL-এ `UPDATE` স্টেটমেন্ট ব্যবহার করা হয় ডাটাবেসের টেবিলে বিদ্যমান রেকর্ডের ডেটা পরিবর্তন বা আপডেট করার জন্য। এটি নির্দিষ্ট কলামের মান পরিবর্তন করে এবং `WHERE` ক্লজের মাধ্যমে কোন রেকর্ডগুলো আপডেট করা হবে তা নির্দিষ্ট করা যায়।

### উদ্দেশ্য:

- **ডেটা মডিফিকেশন**: টেবিলের এক বা একাধিক কলামের মান পরিবর্তন করা।
- **নির্দিষ্ট রেকর্ড টার্গেট**: `WHERE` ক্লজ ব্যবহার করে শুধুমাত্র নির্দিষ্ট শর্ত পূরণকারী রেকর্ড আপডেট করা।
- **বাল্ক আপডেট**: একাধিক রেকর্ড একসাথে পরিবর্তন করা।

### সিনট্যাক্স:

```sql
UPDATE table_name
SET column_name = new_value
WHERE condition;
```

### উদাহরণ (এই অ্যাসাইনমেন্ট থেকে):

প্রবলেম ৭-এ আমরা `species` টেবিলে ১৮০০ সালের আগে আবিষ্কৃত প্রজাতির `conservation_status` পরিবর্তন করে 'Historic' করেছি:

```sql
UPDATE species
SET conservation_status = 'Historic'
WHERE discovery_date < '1800-01-01';
```

**আউটপুট**:

- AffectedRows: 3 (যেহেতু তিনটি প্রজাতির `discovery_date` ১৮০০-এর আগের)।

এখানে:

- `UPDATE species`: `species` টেবিলে পরিবর্তন করা হবে।
- `SET conservation_status = 'Historic'`: `conservation_status` কলামের মান 'Historic' করা হবে।
- `WHERE discovery_date < '1800-01-01'`: শুধুমাত্র ১৮০০-এর আগে আবিষ্কৃত প্রজাতিগুলো আপডেট হবে।

### আরেকটি উদাহরণ:

আমরা রেঞ্জার "Alice Green"-এর রিজিয়ন পরিবর্তন করে "Western Forest" করতে চাই:

```sql
UPDATE rangers
SET region = 'Western Forest'
WHERE name = 'Alice Green';
```

- **WHERE ক্লজের গুরুত্ব**: `WHERE` না থাকলে পুরো টেবিলের সব রেকর্ড আপডেট হবে, যা অনাকাঙ্ক্ষিত ফলাফল ঘটাতে পারে।

- **একাধিক কলাম আপডেট**: একাধিক কলাম একসাথে আপডেট করা যায়, যেমন: `SET column1 = value1, column2 = value2`।
- **ডেটা ইন্টেগ্রিটি**: ফরেন কী কনস্ট্রেইন্ট থাকলে, আপডেট করা মান অবশ্যই valid হতে হবে।

### সুবিধা:

- নির্দিষ্ট ডেটা সহজে পরিবর্তন করা যায়।
- শর্তভিত্তিক আপডেটের মাধ্যমে নির্ভুলতা নিশ্চিত হয়।

সংক্ষেপে, `UPDATE` স্টেটমেন্ট ডাটাবেসে ডেটা মডিফাই করার জন্য একটি শক্তিশালী টুল, যা `WHERE` ক্লজের সাথে ব্যবহার করে নির্দিষ্ট এবং কার্যকর পরিবর্তন নিশ্চিত করে।
