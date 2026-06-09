# La Chocolatera – Shopify Theme

## Projekt-Übersicht

- **Shop-Name:** La Chocolatera
- **Zweck:** Online-Shop für Kakao-Produkte
- **Store:** lachocolatera-test.myshopify.com
- **Theme-Basis:** Shopify Skeleton Theme v0.1.0
- **Repo:** git@github.com:playfulwizzard/mein-shopify-store.git

## Produkte & Kategorien

| Kategorie | Produkte |
|---|---|
| Schokolade | Tafeln, Pralinen, Trinkschokolade |
| Kakao Nibs | Roh, geröstet |
| Kakao Pulver | Naturell, stark entölt |
| Kakaobohnen | Ganz, gemahlen |
| Kakaobutter | Roh, desodoriert |
| Geschenksets | Diverse Zusammenstellungen |

## Seitenstruktur

| Seite | Template | Inhalt |
|---|---|---|
| Startseite | `templates/index.json` | Hero, Featured Products, USPs, Blog-Teaser |
| Shop (Alle Produkte) | `templates/collection.json` | Produktlisting, Filter |
| Produkt | `templates/product.json` | Standard-Produktseite |
| Über Uns | `templates/page.json` | Story, Philosophie, Team |
| Blog | `templates/blog.json` | Rezepte, Kakaowissen, News |
| Blog-Artikel | `templates/article.json` | Einzelner Blogpost |
| Landing Pages | `templates/page.*.json` | Highlight-Produkte (z.B. `page.kakao-nibs.json`) |
| Warenkorb | `templates/cart.json` | Standard |
| Suche | `templates/search.json` | Standard |
| 404 | `templates/404.json` | Standard |

## Branch-Workflow

```
main         → Live / Produktion
staging      → Testing vor Live-Push
feature/*    → Neue Features (z.B. feature/hero-section)
hotfix/*     → Schnelle Bugfixes (z.B. hotfix/mobile-menu)
```

**Workflow:** `feature/*` → PR nach `staging` → testen → PR nach `main`

## Dev-Workflow

```bash
cd mein-shopify-store
git checkout feature/mein-feature
shopify theme dev --store=lachocolatera-test.myshopify.com
```

Theme-Vorschau: `https://lachocolatera-test.myshopify.com/?preview_theme_id=198718816586`
Theme-Editor: `https://lachocolatera-test.myshopify.com/admin/themes/198718816586/editor`

## Theme-Struktur

```
assets/      → CSS, SVGs, statische Dateien
blocks/      → Wiederverwendbare, nestbare UI-Blöcke
config/      → Globale Theme-Einstellungen (settings_schema.json)
layout/      → Master-Layout (theme.liquid)
locales/     → Übersetzungen (en.default.json)
sections/    → Modulare Seitenabschnitte
snippets/    → Wiederverwendbare Liquid-Fragmente
templates/   → Seitenstruktur-Definitionen (JSON)
```

## Wichtige Dateien

- `layout/theme.liquid` — Master-Layout, Header/Footer-Einbindung
- `config/settings_schema.json` — Globale Farben, Fonts, Layout
- `sections/header.liquid` — Navigation, Warenkorb-Icon
- `sections/footer.liquid` — Footer-Links, Zahlungsicons
- `snippets/css-variables.liquid` — CSS Custom Properties
- `snippets/image.liquid` — Bildrendering mit optionalem Link
- `snippets/meta-tags.liquid` — SEO & Social Meta Tags

## Coding-Konventionen

- Neue Sections immer mit `{% schema %}` für Merchant-Anpassbarkeit
- CSS-Variablen aus `snippets/css-variables.liquid` verwenden (kein Hardcoding von Farben/Fonts)
- Bilder immer über `snippets/image.liquid` einbinden
- Texte über Locale-Dateien (`locales/en.default.json`) verwalten
- Sections nicht in `header-group` oder `footer-group` registrieren, wenn sie nur auf bestimmten Seiten erscheinen
- Für Landing Pages: eigene Templates unter `templates/page.*.json` anlegen

## CSS Custom Properties (Referenz)

```css
--font-primary--family
--page-width          /* 90rem oder 110rem */
--page-margin         /* Standard: 20px */
--color-background    /* Standard: #FFFFFF */
--color-foreground    /* Standard: #333333 */
--style-border-radius-inputs
```
