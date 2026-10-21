# BUG-02: Номын он-ыг хязгаарлах шалгалт байхгүй байна

Орчин:  Уншлагын жагсаалт v2.0, curl, Windows 11, 2026-10-21
Урьдчилсан нөхцөл: node app.js-ийг шинээр асаасан (анхны 3 ном)

## Дахин гаргах алхам
1. API ашиглан он-ыг 1000-аас бага (ж: 500) утгаар нэмэх:
   `curl -i -X POST http://localhost:3000/api/books -H "Content-Type: application/json" -d '{"title": "Old Book", "author": "Ancient", "year": 500}'`
2. API ашиглан он-ыг 2100-аас их (ж: 3000) утгаар нэмэх:
   `curl -i -X POST http://localhost:3000/api/books -H "Content-Type: application/json" -d '{"title": "Future Book", "author": "Time Traveler", "year": 3000}'`

Хүлээгдээж байсан: Он нь 1000-2100 хооронд байх ёстой тул алдаа зааж нэмэхгүй байх.
Бодит үр дүн: Хоёр тохиолдолд HTTP 201 Created буцааж, ном нэмэгдэв.

Ноцтой байдал: Major - Буруу өгөгдөл системд хадгалагдаж байна.
Хавсралт: evidence/bug-02-curl.txt
Олдсон аялал: Boundary Value Analysis
