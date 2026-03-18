<img width="1024" height="620" alt="Screenshot 2026-03-18 210438" src="https://github.com/user-attachments/assets/a9d06b74-30b1-402f-8aab-5c8bd60ebd25" />
# 🌿 Plant Shop – UI Prototype

Responsiver Frontend-Prototype eines modernen Plant Shops, gebaut mit purem HTML5 und CSS3. Kein Framework, kein JavaScript – alle Interaktionen und Animationen entstehen ausschließlich durch modernes CSS.

---

## 📁 Projektstruktur

```
/
├── index.html
├── css/
│   ├── stylesheet.css
│   └── fauna.css          ← Self-hosted Webfont (Fauna One)
├── img/
└── webfonts/
    ├── FaunaOne-Regular.woff
    └── FaunaOne-Regular.woff2
```

---

## 🧩 Seitenaufbau

**Navigation** – Sticky Glassmorphism-Nav mit `backdrop-filter: blur()`, animiertem Underline-Hover per `::after` Pseudo-Element und Hamburger-Menü für Mobile.

**Header / Hero** – Mehrschichtiges Hintergrundbild aus drei überlagerten Ebenen (`background-image` Stacking), fluid skalierender Überschrift per `clamp()` und animiertem CTA-Button.

**Learn More** – Zweispaltiges Flex-Layout mit Bild-Hover-Zoom. Smooth Hover-Transition auf Button zu Grün.

**Yellow Pics** – Asymmetrisches CSS Grid mit großem Hauptbild und drei kleineren Bildern. Alle Bilder mit Hover-Zoom und Box-Shadow Effekt.

**Grid Gallery** – Dreispaltiges CSS Grid mit Hintergrundpflanze und Hover-Zoom-Effekt auf allen Bildern.

**Testimonials** – Horizontales **CSS Scroll Snap Karussell** ohne JavaScript. Immer zwei Karten sichtbar, einrastiges Scrollen, gestylte grüne Scrollbar.

**Footer** – Minimalistischer Credits-Footer.

---

## ✨ CSS-Highlights

### CSS Custom Properties
Alle Farben, Abstände, Transitions und Border-Radien zentral in `:root` definiert – wartbarer, konsistenter Code ohne Hex-Codes zu wiederholen.

```css
:root {
    --color-yellow: #F2B138;
    --color-green: #349623;
    --space-xl: 6rem;
    --transition-base: 0.3s ease;
}
```

### Glassmorphism Navigation
Sticky Nav mit Frosted-Glass-Effekt – rein per CSS, kein JavaScript.

```css
nav {
    background-color: rgba(242, 177, 56, 0.75);
    backdrop-filter: blur(12px);
    position: sticky;
    top: 0;
}
```

### Fluid Typography mit `clamp()`
Schriftgrößen skalieren stufenlos zwischen Viewport-Größen – keine sprunghaften Media Query Breakpoints nötig.

```css
h1 { font-size: clamp(2rem, 6vw, 4rem); }
h2 { font-size: clamp(1.5rem, 4vw, 2.5rem); }
```

### CSS Scroll Snap Karussell
Vollständiges horizontales Karussell ohne eine einzige Zeile JavaScript.

```css
.testimonials > div {
    display: flex;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
}
.testimonials article {
    scroll-snap-align: start;
    flex: 0 0 calc(50% - 1rem);
}
```

### Moderner `:has()` Selektor
Parent-Selektor für kontextbasiertes Styling – einer der neuesten CSS-Selektoren überhaupt.

```css
.testimonials article:has(img) {
    border-left: 4px solid var(--color-green);
}
```

### Scroll-Animationen
Elemente faden beim Laden sanft ein – per `@keyframes` und gestaffelten `animation-delay` Klassen, ohne JavaScript.

```css
@keyframes fadeInUp {
    from { opacity: 0; transform: translateY(30px); }
    to   { opacity: 1; transform: translateY(0); }
}
```

### Dark Mode
Automatische Farbanpassung per `@media (prefers-color-scheme: dark)` – folgt der Systemeinstellung des Nutzers.

### `prefers-reduced-motion`
Alle Animationen werden für Nutzer deaktiviert, die das in ihren Systemeinstellungen bevorzugen – Accessibility by default.

---

## 📱 Responsive Breakpoints

| Breakpoint | Zielgerät | Änderungen |
|---|---|---|
| `≤ 1024px` | Tablet | Abstände reduziert, flexiblere Breiten |
| `≤ 768px` | Mobil | Hamburger-Menü, Flex-Layouts untereinander, Grid vereinfacht, Testimonials einspaltiger |
| `≤ 480px` | Kleines Mobil | Alles einspaltiger, Testimonials gestapelt |

---

## 🛠️ Technologien

- **HTML5** – semantisches Markup
- **CSS3** – Custom Properties, `clamp()`, CSS Grid, Flexbox, Scroll Snap, `backdrop-filter`, `:has()`, `@keyframes`, `prefers-color-scheme`, `prefers-reduced-motion`
- **Self-hosted Webfont** – Fauna One via `@font-face` mit `font-display: swap`
- **Kein Framework**, kein JavaScript

---

## 📸 Bildquellen

Alle Fotos stammen von [Unsplash](https://unsplash.com) und sind unter der [Unsplash License](https://unsplash.com/license) frei verwendbar.

---

## 📌 Hinweise

Dieser Prototype ist ein reines UI/UX-Demo ohne Backend-Anbindung.
