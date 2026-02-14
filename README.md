# 📚 Matematika - Blog za osnovnu školu

Interaktivni matematički blog sa lekcijama za 5., 6., 7. i 8. razred osnovne škole.

## 🎯 Funkcionalnosti

- ✅ Detaljne lekcije sa objašnjenjima
- 🎮 Interaktivne vežbe u browseru
- 📊 Vizuelizacije matematičkih koncepata
- 🧮 Podrška za matematičke formule (KaTeX)
- 📱 Responsive dizajn (radi na svim uređajima)
- ⚡ Brzo učitavanje (Next.js + static export)

## 📖 Sadržaj

### 5. razred
- Prirodni brojevi
- Sabiranje i oduzimanje
- Množenje i deljenje

### 6. razred
- Razlomci
- Decimalni brojevi (dolazi uskoro)
- Proporcija i razmera (dolazi uskoro)

### 7. razred
- Negativni brojevi
- Algebarski izrazi (dolazi uskoro)
- Jednačine (dolazi uskoro)

### 8. razred
- Pitagorina teorema
- Kvadratni koreni (dolazi uskoro)
- Kvadratne jednačine (dolazi uskoro)

## 🚀 Instalacija i pokretanje

### 1. Kloniraj projekat
```bash
git clone <tvoj-repo>
cd math-blog
```

### 2. Instaliraj zavisnosti
```bash
npm install
```

### 3. Pokreni development server
```bash
npm run dev
```

Otvori browser na [http://localhost:3000](http://localhost:3000)

## 📤 Deploy na Vercel

### Metod 1: GitHub (preporučeno)

1. Kreiraj GitHub repozitorijum i pushuj kod
2. Idi na [vercel.com](https://vercel.com)
3. Klikni "New Project"
4. Importuj svoj GitHub repo
5. Vercel će automatski detektovati Next.js i deployovati!

### Metod 2: Vercel CLI

```bash
# Instaliraj Vercel CLI
npm i -g vercel

# Deployuj
vercel

# Za production
vercel --prod
```

### Metod 3: Manual build

```bash
# Build projekta
npm run build

# Out folder će sadržati statičke fajlove
# Upload sve iz /out foldera na bilo koji hosting
```

## 📝 Dodavanje novih lekcija

### 1. Kreiraj novu stranicu

Kreiraj fajl u odgovarajućem folderu:
```
app/razredi/[razred]/[nova-lekcija]/page.tsx
```

### 2. Koristi template

```typescript
'use client'

import InteractiveExercise from '@/components/InteractiveExercise'

export default function NovaLekcija() {
  const questions = [
    {
      question: 'Tvoje pitanje?',
      correctAnswer: 'Tačan odgovor',
      options: ['Opcija 1', 'Opcija 2', 'Opcija 3', 'Opcija 4'],
      type: 'multiple-choice' as const,
    },
    // ... više pitanja
  ]

  return (
    <div className="max-w-4xl mx-auto">
      <h1 className="text-4xl font-bold mb-6">Naslov lekcije</h1>
      
      <div className="lesson-content">
        {/* Tvoj sadržaj */}
      </div>

      <InteractiveExercise 
        questions={questions}
        title="Proveri svoje znanje"
      />
    </div>
  )
}
```

### 3. Dodaj u listu lekcija

Ažuriraj `app/razredi/[razred]/page.tsx` da uključi novu lekciju.

## 🎨 Prilagođavanje

### Boje
Izmeni boje u `tailwind.config.js`:
```javascript
theme: {
  extend: {
    colors: {
      primary: '#3b82f6',  // Plava
      secondary: '#8b5cf6', // Ljubičasta
    },
  },
}
```

### Stilovi
Globalni stilovi su u `app/globals.css`

## 🛠️ Tehnologije

- **Next.js 14** - React framework
- **TypeScript** - Type safety
- **Tailwind CSS** - Styling
- **KaTeX** - Matematičke formule
- **Vercel** - Hosting

## 📧 Kontakt

Za pitanja i sugestije, kontaktirajte...

## 📄 Licenca

MIT License - koristi slobodno!

---

Napravljeno sa ❤️ za učenike osnovnih škola
