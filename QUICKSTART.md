# 🚀 Quick Start Guide

## Brzo pokretanje (3 koraka)

### 1️⃣ Instaliraj zavisnosti
```bash
cd math-blog
npm install
```

### 2️⃣ Pokreni lokalno
```bash
npm run dev
```
Otvori: http://localhost:3000

### 3️⃣ Deploy na Vercel
```bash
# GitHub metod (najlakši):
# 1. Napravi GitHub repo
# 2. Push kod
# 3. Na vercel.com klikni "Import Project"
# 4. Izaberi svoj repo - gotovo!

# ILI koristi CLI:
npm i -g vercel
vercel
```

## 📁 Struktura projekta

```
math-blog/
├── app/
│   ├── razredi/
│   │   ├── peti/          # 5. razred lekcije
│   │   ├── sesti/         # 6. razred lekcije
│   │   ├── sedmi/         # 7. razred lekcije
│   │   └── osmi/          # 8. razred lekcije
│   ├── layout.tsx         # Glavni layout
│   ├── page.tsx           # Početna stranica
│   └── globals.css        # Globalni stilovi
├── components/
│   ├── Math.tsx           # Matematičke formule
│   └── InteractiveExercise.tsx  # Interaktivne vežbe
└── package.json
```

## 📝 Dodavanje nove lekcije

1. Kreiraj: `app/razredi/[razred]/[lekcija]/page.tsx`
2. Kopiraj template iz postojeće lekcije
3. Dodaj u listu: `app/razredi/[razred]/page.tsx`

## 🎨 Prilagođavanje boja

Izmeni `tailwind.config.js`:
```javascript
colors: {
  primary: '#tvoja-boja',    // Glavna boja
  secondary: '#tvoja-boja',  // Sekundarna boja
}
```

## ❓ Problemi?

### "Module not found" greška
```bash
rm -rf node_modules package-lock.json
npm install
```

### Port 3000 je zauzet
```bash
npm run dev -- -p 3001  # Koristi port 3001
```

### Build greške
```bash
npm run build  # Proveri da li ima grešaka
```

## 📚 Trenutne lekcije

✅ 5. razred: Prirodni brojevi, Sabiranje i oduzimanje, Množenje i deljenje
✅ 6. razred: Razlomci
✅ 7. razred: Negativni brojevi
✅ 8. razred: Pitagorina teorema

🔜 Uskoro: Još 8+ lekcija

---

Za detaljna uputstva, pogledaj README.md
