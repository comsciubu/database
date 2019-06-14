# Dev Note

1. ติดตั้ง node

2. ติดตั้ง gitbook

```sh
npm i -g gitbook-cli
```

3. เริ่มเขียนเอกสาร ด้วย markdown

   แยก folder แต่ละ folder มี README.md กับ SUMMARY.md

4. ติดตั้ง plugin ที่ระบุไว้ใน `book.json`

```sh
gitbook install
```

5. ทดสอบผลลัพธ์

```sh
gitbook serve . -o docs
```

6. เปิดเว็บไปที่ `http://localhost:4000/` เพื่อดูผลลัพธ์

7. บันทึกการเปลี่ยนแปลง 

> จำเป็นต้องใช้ความรู้เรื่อง git  

คำสั่งคร่าวๆ เบื้องต้น

```sh
cp -r _book/* docs/
git add .
git commit -m "ข้อความบอก update อะไรบ้างในหนึ่งบรรทัด"
```

8. รอประมาณ 3 นาทีแล้วดูการเปลี่ยนแปลงที่ 

https://comsciubu.github.io/database

