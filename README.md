# Lab 06 : JavaScript/TypeScript #3

### ป้อนข้อมูลนักศึกษา

รหัส นศ.:

ชื่อ-สกุล :

ให้ นศ.เขียนโปรแกรมโดยใช้ Node.js + TypeScript ตามคำสั่งของโจทย์ในข้อต่าง ๆ ตามรายละเอียดด้านล่างนี้

[คลิกเพื่อดูรายละเอียด](https://o365cmu-my.sharepoint.com/:b:/g/personal/dome_potikanond_cmu_ac_th/EUzDKZepCp9Gsj5rsqYFRLYBaG_BsNIheMRtFGcZMp96ug?e=iXKn9C)

---

### คำอธิบายเกี่ยวกับการใช้งาน TypeScript

หากในโปรเจคโฟลเดอร์ยังไม่มี `package.json` ให้ initialize project ด้วยการ**รันคำสั่งต่อไปนี้ภายในโปรเจคโฟลเดอร์**

```bash
$ npm init -y
```

ถ้าหากได้มีการติดตั้ง `pnpm` ไว้แล้วก็สามารถใช้คำสั่งต่อไปนี้แทนได้

```bash
$ pnpm init
```

หากโปรเจคมี `package.json` แล้วให้ติดตั้ง package ต่าง ๆ ที่เป็น `dependencies` ของโปรเจคด้วยคำสั่ง

```bash
$ npm i
```

หรือ

```bash
$ pnpm i
```

Package ที่ต่าง ๆ ที่ติดตั้งอาจมีการออกเวอร์ชันใหม่ ๆ ที่ได้รับการแก้ไขข้อบกพร่อง เพิ่มความสามารถ และอุดช่องโหว่ด้านความปลอดภัย โดยเราสามารถอัพเดต package เหล่านี้ให้เป็นเวอร์ชันล่าสุดด้วยคำสั่ง

```bash
$ npm update
```

หรือ

```bash
$ pnpm update
```

สำหรับ lab นี้เราได้มีการติดตั้ง package ต่อไปนี้เรียบร้อยแล้วดังนั้น นศ. ไม่ต้องติดตั้งเองอีก

- `axios` : เพื่อใช้ในการสร้าง HTTP request สำหรับการดึงข้อมูล
- `TypeScript` : เพื่อให้สามารถเขียนโค้ด TypeScript ในโปรเจคนี้
- `@types/node` : เพื่อเพิ่มข้อมูล Type definition ให้ node.js
- `tsx` เพื่อให้สามารถรันโค้ด TypeScript ได้โดยไม่ต้อง compile
- `nodemon` เพื่อให้สามารถรันโค้ด JavaScript ได้เมื่อไฟล์มีการเปลี่ยนแปลง (optional)

ติดตั้ง package อื่นๆ ที่จำเป็นแบบ development dependencies ด้วย PNPM

```bash
$ pnpm install -D typescript  @types/node  tsx
```

ติดตั้ง `Axios` package ที่จำเป็นแบบ dependencies ด้วย PNPM

```bash
$ pnpm install axios
```

**หมายเหตุ:** ใน lab นี้ ได้มีการสร้างไฟล์ `tsconfig.json` ไว้ให้ นศ. แล้ว

เมื่อต้องการรันไฟล์ TypeScript โดยไม่จำเป็นต้อง Compile สามารถใช้คำสั่งต่อไปนี้

```bash
$ npx tsx <filename.ts>
```

---

### ทดสอบการทำงานกับ Testcase ที่ใช้ในระบบ Classroom autograder

**หมายเหตุ:** ใน lab นี้ ได้มีการปรับให้สามารถตรวจสอบการทำงานจากไฟล์ `TypeScript` ได้เลย (ไม่ต้อง compile ให้ได้ไฟล์ `JavaScript`) โดยใช้คำสั่งต่อไปนี้ในการตรวจสอบความถูกต้อง

```bash
$ npm run test q1     // เพื่อตรวจข้อ q1
$ npm run test        // เพื่อตรวจทุกข้อ
```
