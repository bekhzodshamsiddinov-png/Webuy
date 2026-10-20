# Webuy — 3D ko'chmas mulk sayti

Qurilish loyihasi uchun interaktiv 3D sayt namunasi. Xaridor sichqoncha g'ildiragi bilan:

1. bulutlar ustidan majmuaga tushadi;
2. binoni ko'radi, qavat ustiga olib borsa bo'sh xonadonlar soni chiqadi, qavatni tanlaydi;
3. bosh eshikdan lobbi va reception'ga kiradi;
4. liftda tanlangan qavatga chiqadi;
5. xonadonni tomsiz holda tepadan ko'radi;
6. xona nuqtasini bosib, xona ichida 360° aylanib ko'radi (sichqoncha bilan tortish, g'ildirak bilan yaqinlashtirish, telefonda barmoq bilan).

Pastda xonadon rejalari, narxlar va ko'rishga yozilish formasi bor.

**Jonli sayt:** https://bekhzodshamsiddinov-png.github.io/Webuy/

Sayt GitHub Pages orqali `gh-pages` branch'idan chiqadi. O'zgarishlar `main`ga push qilingandan keyin `gh-pages`ga ham push qilinadi: `git push origin main main:gh-pages`.

> Hozirgi bino, lobbi va kvartira kod bilan chizilgan namunaviy model. "Sadaf Residence" nomi, narxlar va maydonlar shartli. Real loyihada ular buyurtmachining 3D modeli va ma'lumotlari bilan almashtiriladi.

## Tuzilishi

| Fayl | Vazifasi |
|---|---|
| `index.html` | Butun sayt: dizayn, 3D sahna, kamera yo'li, 360° rejim, forma |
| `vendor/three/` | three.js r160 (MIT), tashqi CDN'ga bog'liq bo'lmasligi uchun repo ichida |

Build kerak emas: oddiy statik sayt. Lokal ishga tushirish uchun:

```bash
python3 -m http.server 8000
# keyin http://localhost:8000
```

(`index.html` faylini to'g'ridan-to'g'ri ikki marta bosib ochish ishlamaydi: brauzer ES-modullarni `file://` dan yuklamaydi.)

## Keyingi bosqich: real modelni ulash

- **Bino modeli:** GLB (Draco bilan siqilgan) eng yaxshi format. FBX, OBJ, 3ds Max, SketchUp, Revit, Blender fayllaridan eksport qilinadi va `GLTFLoader` orqali yuklanadi.
- **Interyer:** kvartira modeli yoki 360° panorama renderlar (Corona / V-Ray / Lumion / Twinmotion, 8K equirectangular JPG). Panorama bilan xonalar fotodek real ko'rinadi.
- **Ma'lumotlar:** xonadonlar ro'yxati (qavat, raqam, maydon, narx, holat). Hozir `index.html` ichidagi `floors` va `rooms` massivlarida turibdi.
- **Forma:** hozir namuna. Arizalarni Telegram botga yoki CRM'ga yuborish qo'shiladi.
