# NIIGEM 800 — GitHub Pages Web App

Энэ хувилбар нь одоо байгаа NIIGEM 800 сургалтын системийг хадгалж, PWA (суулгаж ашиглах боломжтой веб апп) болгосон багц юм.

## GitHub Pages дээр нийтлэх

1. GitHub дээр repository үүсгэнэ (эсвэл одоо байгаа repository-доо орно).
2. Энэ хавтас доторх **бүх файл, хавтсыг** repository-ийн үндсэн түвшинд байршуулна.
3. `index.html` нь repository-ийн үндсэн түвшинд байх ёстой. `assets/`, `manifest.json`, `sw.js` мөн түүнтэй нэг түвшинд байна.
4. Repository → **Settings → Pages** руу орно.
5. **Deploy from a branch** сонгоно.
6. `main` branch, `/(root)` сонгоод Save дарна.
7. GitHub Pages URL үүссэний дараа утас болон компьютерээс HTTPS холбоосоор нээнэ.

## PWA боломжууд

- Android/дэмждэг браузерт суулгах боломжтой.
- iPhone/iPad дээр Safari → Share → Add to Home Screen ашиглана.
- Үндсэн HTML, дүрс, manifest нь эхний удаа амжилттай ачаалсны дараа Cache-д орно.
- Дараагийн удаа интернэтгүй үед үндсэн интерфэйс нээгдэнэ.
- Шинэ хувилбарын `sw.js` cache version-ийг өөрчилж нийтэлбэл хуучин cache устаж шинэ хувилбар татагдана.

## Анхаарах зүйл

- Сургалтын явц, алдаа, ахицын ихэнх өгөгдөл одоогоор `localStorage`-д хадгалагддаг. Тиймээс өөр төхөөрөмж/браузерт автоматаар синк хийхгүй, browser data арилгавал алдагдаж болно. Бүртгэлтэй олон хэрэглэгчийн систем болгохын тулд authentication + database sync тусад нь хэрэгтэй.
- `tests.json` нь нэмэлт сорилын файл; ашиглах бол repository-ийн үндсэн түвшинд байрлуулна.
- Supabase ашигладаг сорилын дүн илгээх тохиргоог өөрчлөх шаардлагагүйгээр хадгалсан. Гэхдээ Supabase-ийн RLS policy нь зөвхөн зөвшөөрсөн үйлдлийг нээлттэй байлгаж байгаа эсэхийг Dashboard дээр шалгаарай.
- GitHub Pages нь статик hosting. Нэвтрэлт, төлбөр, багшийн удирдлагын самбар зэрэг backend шаарддаг боломжийг дан GitHub Pages шийдэхгүй.

## Файлын бүтэц

```text
repository-root/
├── index.html
├── manifest.json
├── sw.js
├── README.md
└── assets/
    ├── icon-192.png
    ├── icon-512.png
    ├── apple-touch-icon.png
    └── niigem800-logo.jpg
```
