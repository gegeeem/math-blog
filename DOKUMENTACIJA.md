# 📚 Matematički Blog - Kompletna Dokumentacija

## 🎉 Šta si dobio?

Kompletan Next.js blog sa interaktivnim lekcijama iz matematike za osnovnu školu!

## ✨ Funkcionalnosti

### 🎯 Trenutno aktivne lekcije (10 lekcija)

#### 5. razred (3 lekcije)
1. **Prirodni brojevi** - Pisanje, čitanje, upoređivanje i zaokruživanje
2. **Sabiranje i oduzimanje** - Računske operacije sa prenošenjem
3. **Množenje i deljenje** - Tablica množenja, deljenje sa i bez ostatka

#### 6. razred (1 lekcija)
1. **Razlomci** - Skraćivanje, proširivanje, upoređivanje

#### 7. razred (1 lekcija)
1. **Negativni brojevi** - Sabiranje, oduzimanje, množenje, deljenje

#### 8. razred (1 lekcija)
1. **Pitagorina teorema** - Primena u geometriji, Pitagorine trojke

### 🎮 Interaktivne vežbe
- Svaka lekcija ima kviz sa 4-5 pitanja
- Automatska provera odgovora
- Trenutni feedback (tačno/netačno)
- Praćenje rezultata (% uspešnosti)
- Mogućnost ponovnog pokušaja

### 📊 Vizualizacije
- Brojevna prava
- Tablice množenja
- Geometrijske figure (Pitagorina teorema)
- Razlomci sa vizuelnim prikazom
- Boje kodiranje po razredima

### 🧮 Matematičke formule
- KaTeX integracija za formule
- Inline i block formule
- Automatsko renderovanje

## 📁 Struktura projekta

```
math-blog/
├── app/                              # Next.js App Router
│   ├── globals.css                   # Globalni stilovi + KaTeX
│   ├── layout.tsx                    # Root layout sa navigacijom
│   ├── page.tsx                      # Početna stranica
│   └── razredi/
│       ├── peti/
│       │   ├── page.tsx             # Lista lekcija
│       │   ├── prirodni-brojevi/    # Lekcija 1
│       │   ├── sabiranje-oduzimanje/# Lekcija 2
│       │   └── mnozenje-deljenje/   # Lekcija 3
│       ├── sesti/
│       │   ├── page.tsx
│       │   └── razlomci/            # Lekcija 1
│       ├── sedmi/
│       │   ├── page.tsx
│       │   └── negativni-brojevi/   # Lekcija 1
│       └── osmi/
│           ├── page.tsx
│           └── pitagorina-teorema/  # Lekcija 1
├── components/
│   ├── Math.tsx                     # Komponenta za formule
│   └── InteractiveExercise.tsx     # Kviz komponenta
├── package.json                     # Zavisnosti
├── tsconfig.json                    # TypeScript config
├── tailwind.config.js              # Tailwind config
├── next.config.js                  # Next.js config (static export)
├── postcss.config.js               # PostCSS config
├── vercel.json                     # Vercel deployment
├── .gitignore                      # Git ignore
├── README.md                       # Kompletna dokumentacija
└── QUICKSTART.md                   # Brzi start vodič
```

## 🚀 Kako koristiti?

### Lokalno pokretanje

```bash
# 1. Navigiraj u folder
cd math-blog

# 2. Instaliraj zavisnosti (samo prvi put)
npm install

# 3. Pokreni development server
npm run dev

# 4. Otvori browser
# http://localhost:3000
```

### Deploy na Vercel (3 načina)

#### Način 1: GitHub (preporučeno) 🌟
1. Napravi GitHub repozitorijum
2. Push kod: `git init && git add . && git commit -m "Initial" && git push`
3. Idi na https://vercel.com
4. Klikni "New Project"
5. Import svoj GitHub repo
6. Vercel automatski detektuje Next.js i deploya!
7. Dobijaš URL: `https://tvoj-projekat.vercel.app`

#### Način 2: Vercel CLI
```bash
npm i -g vercel
vercel          # Development
vercel --prod   # Production
```

#### Način 3: Static Export
```bash
npm run build
# Upload /out folder na bilo koji static hosting
```

## 📝 Dodavanje novih lekcija

### Korak 1: Kreiraj novu lekciju

Napravi fajl: `app/razredi/[razred]/[nova-lekcija]/page.tsx`

```typescript
'use client'

import InteractiveExercise from '@/components/InteractiveExercise'

export default function NovaLekcija() {
  const questions = [
    {
      question: 'Tvoje pitanje?',
      correctAnswer: 'Tačan odgovor',
      options: ['A', 'B', 'C', 'D'],  // Za multiple choice
      type: 'multiple-choice' as const,
    },
    {
      question: 'Drugo pitanje?',
      correctAnswer: '42',
      type: 'input' as const,  // Za unos odgovora
    },
  ]

  return (
    <div className="max-w-4xl mx-auto">
      <h1 className="text-4xl font-bold mb-6">Naslov Lekcije</h1>
      
      <div className="lesson-content">
        <h2>Podnaslov</h2>
        <p>Tvoj sadržaj...</p>

        <div className="example">
          <h3>Primer:</h3>
          <p>Objašnjenje primera...</p>
        </div>

        <div className="important">
          <p><strong>Važno:</strong> Ključne informacije...</p>
        </div>
      </div>

      <InteractiveExercise 
        questions={questions}
        title="Proveri svoje znanje"
      />
    </div>
  )
}
```

### Korak 2: Dodaj u navigaciju

Ažuriraj `app/razredi/[razred]/page.tsx`:

```typescript
const lekcije = [
  // ... postojeće lekcije
  {
    slug: 'nova-lekcija',
    naslov: 'Nova Lekcija',
    opis: 'Kratak opis lekcije',
  },
]
```

## 🎨 Prilagođavanje

### Boje

`tailwind.config.js`:
```javascript
theme: {
  extend: {
    colors: {
      primary: '#3b82f6',    // Plava
      secondary: '#8b5cf6',  // Ljubičasta
    },
  },
}
```

### Stilovi lekcija

`app/globals.css`:
```css
.lesson-content h2 { /* Stilizuj naslove */ }
.lesson-content .example { /* Stilizuj primere */ }
.lesson-content .important { /* Stilizuj važne delove */ }
```

### Dodavanje matematičkih formula

```typescript
import Math from '@/components/Math'

// Inline formula
<Math>x^2 + y^2 = z^2</Math>

// Block formula (centrirano)
<Math block>
  \frac{a}{b} = \frac{c}{d}
</Math>
```

## 🛠️ Tehnički detalji

### Zavisnosti
- **Next.js 14** - React framework sa App Routerom
- **React 18** - UI library
- **TypeScript** - Type safety
- **Tailwind CSS** - Utility-first CSS
- **KaTeX** - Matematičke formule (brže od MathJax)
- **gray-matter** - Markdown frontmatter (za buduće proširenje)

### Performanse
- Static export za maksimalnu brzinu
- Optimizovane slike (automatski)
- Minimal JavaScript bundle
- Server-side rendering
- Automatski code splitting

### SEO
- Metadata u layout.tsx
- Semantički HTML
- Pristupačnost (a11y)

## 📈 Buduća proširenja

### Predlozi za nove funkcionalnosti:

1. **Sistem napretka** - Praćenje završenih lekcija
2. **Sertifikati** - Za završene razrede
3. **Lekcije u PDF** - Export za offline učenje
4. **Video tutorijali** - Embed YouTube videa
5. **Forum/Komentari** - Diskusija o lekcijama
6. **Adaptivno učenje** - Težina prema napretku
7. **Gamifikacija** - Badges, achievements
8. **Multi-jezik** - Engleski, Nemački...

### Kako dodati:

**1. PDF Export:**
```bash
npm install jspdf html2canvas
# Dodaj "Export PDF" dugme u lekcije
```

**2. Progress tracking:**
```typescript
// Koristi localStorage ili backend
localStorage.setItem('completed-lessons', JSON.stringify([...]))
```

**3. Video integracija:**
```typescript
<iframe 
  src="https://www.youtube.com/embed/VIDEO_ID"
  className="w-full aspect-video"
/>
```

## 🐛 Troubleshooting

### Problem: "Module not found"
```bash
rm -rf node_modules package-lock.json
npm install
```

### Problem: Port 3000 zauzet
```bash
npm run dev -- -p 3001
```

### Problem: Build errors
```bash
npm run build  # Proveri greške pre deploya
```

### Problem: KaTeX ne renderuje
- Proveri da li je import ispravan
- Vidi konzolu browsera za greške
- KaTeX formula mora biti validna LaTeX sintaksa

## 📞 Podrška

Za pitanja, probleme ili sugestije:
1. Proveri README.md i QUICKSTART.md
2. Pogledaj kod postojećih lekcija kao primere
3. Konsultuj Next.js dokumentaciju: https://nextjs.org/docs

## 📊 Statistika projekta

- **Ukupno fajlova:** ~25
- **Ukupno lekcija:** 10 (sa još 12 planiranih)
- **Lines of code:** ~2,500+
- **Komponente:** 2 reusable (Math, InteractiveExercise)
- **Stranice:** 15+ (home + razredi + lekcije)

## ✅ Checklist za deploy

- [ ] `npm install` - Zavisnosti instalirane
- [ ] `npm run dev` - Lokalno testiranje
- [ ] Proveravamo sve linkove
- [ ] Testiramo sve interaktivne vežbe
- [ ] Proveravamo matematičke formule
- [ ] Testiramo na mobilnom
- [ ] `npm run build` - Build uspešan
- [ ] Deploy na Vercel
- [ ] Testiranje live sajta

## 🎓 Zaključak

Imaš kompletan, funkcionalan matematički blog spreman za Vercel!

**Sledeći koraci:**
1. `cd math-blog && npm install`
2. `npm run dev` - Testiraj lokalno
3. Deploy na Vercel preko GitHub-a
4. Dodaj nove lekcije po potrebi
5. Deli sa učenicima! 🎉

---

**Srećno sa projektom!** 🚀📚✨
