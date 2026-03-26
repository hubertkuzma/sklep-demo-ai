# 🛒 Sklep Demo — E-commerce Analytics & AI Dashboard

> Projekt portfolio demonstrujący pełny stack analityki e-commerce z warstwą AI — od generowania danych, przez dashboardy BI, automatyzacje, aż po chatbota analitycznego.

![Status](https://img.shields.io/badge/status-aktywny-brightgreen)
![Stack](https://img.shields.io/badge/stack-no--code%20%2B%20AI-blueviolet)
![Licencja](https://img.shields.io/badge/licencja-MIT-blue)

---

## 🎯 O projekcie

Fikcyjny sklep e-commerce z **2000 SKU** zbudowany w celach edukacyjnych i portfolio. Projekt pokazuje jak zbudować kompletny ekosystem analityczny bez znajomości programowania — od surowych danych po inteligentnego asystenta AI.

**Demo aplikacji AI:** [hubertkuzma.github.io](https://hubertkuzma.github.io/sklep-demo-ai/)

---

## 🏗️ Architektura projektu

```
Google Sheets (dane źródłowe)
        │
        ├──► Looker Studio (dashboardy BI)
        │
        ├──► Make.com (automatyzacje)
        │         └──► Gmail (e-maile przypominające)
        │
        └──► Claude AI API (analityk AI / chatbot)
```

---

## 📦 Zawartość datasetu

| Arkusz | Rekordy | Opis |
|--------|---------|------|
| Produkty_SKU | 2 000 | SKU, ceny, marże, stany magazynowe, oceny |
| Klienci | 500 | Segmenty RFM, CLV, miasta, zgody marketingowe |
| Zamówienia | 2 000 | Statusy, metody płatności, rabaty |
| Pozycje_zamówień | ~7 100 | Szczegóły każdego produktu w zamówieniu |
| Porzucone_koszyki | 350 | Wartości, odzysk, e-maile |

---

## 📊 Dashboardy Looker Studio

**4 strony interaktywnego raportu:**

### 1️⃣ Sprzedaż ogólna
- Łączna sprzedaż: **6 506 622 PLN**
- Trend miesięczny sprzedaży
- Podział na metody płatności
- KPI: liczba zamówień, średnia wartość koszyka, łączne rabaty

### 2️⃣ Bestsellery
- Top 10 produktów według przychodu
- Ranking kategorii (Elektronika dominuje z **58.1%** sprzedaży)
- Udział kategorii w całkowitym przychodzie

### 3️⃣ Klienci & Segmenty
- Segmentacja: VIP 10% / Regularny 33.8% / Okazjonalny 37.4% / Nowy 18.8%
- Top 10 klientów wg CLV (max: **122 290 PLN**)
- Rozkład geograficzny klientów
- Średnie CLV: **13 013 PLN**

### 4️⃣ Porzucone koszyki
- **387 847 PLN** łączna utracona wartość
- Wskaźnik odzysku: **28.9%**
- Analiza kategorii z największymi stratami
- Skuteczność e-maili przypominających

---

## 🤖 Automatyzacja Make.com

**Scenariusz: Odzyskiwanie porzuconych koszyków**

```
Wyzwalacz: Nowy wiersz w Google Sheets (Porzucone_koszyki)
     ↓
Filtr: Email_wyslany = FALSE
     ↓
Gmail: Wysyłka spersonalizowanego e-maila z wartością koszyka
     ↓
Google Sheets: Aktualizacja Email_wyslany = TRUE
```

- ⏰ Uruchamia się automatycznie co 15 minut
- 📧 Personalizacja: imię, wartość koszyka, data porzucenia
- ✅ Zabezpieczenie przed duplikatami

---

## 🧠 AI Analityk (Claude API)

Interaktywna aplikacja webowa umożliwiająca rozmowę z danymi sklepu w języku naturalnym.

**Możliwości:**
- Analiza trendów sprzedażowych
- Profilowanie segmentów klientów
- Rekomendacje biznesowe oparte na danych
- Identyfikacja ryzyk i szans

**Przykładowe pytania:**
- *„Jakie działania zwiększyłyby sprzedaż w Q1?"*
- *„Opisz profil klienta VIP i jak do niego dotrzeć"*
- *„Gdzie tracimy najwięcej na porzuconych koszykach?"*

---

## 🛠️ Stack technologiczny

| Warstwa | Technologia | Plan |
|---------|-------------|------|
| Dane | Google Sheets | Darmowy |
| Generowanie danych | Python (pandas, openpyxl) | Darmowy |
| Dashboardy BI | Looker Studio | Darmowy |
| Automatyzacje | Make.com | Free tier |
| E-mail | Gmail | Darmowy |
| AI / Chatbot | Claude API (Haiku) | Pay-per-use |
| Hosting | GitHub Pages | Darmowy |

**Łączny koszt miesięczny: ~0 PLN** (poza minimalnym kosztem API)

---

## 🚀 Jak uruchomić lokalnie

### 1. Sklonuj repozytorium
```bash
git clone https://github.com/twoja-nazwa/sklep-demo-ai.git
cd sklep-demo-ai
```

### 2. Wgraj dataset do Google Sheets
- Otwórz `sklep_demo_dataset.xlsx`
- Importuj do Google Sheets: `Plik → Importuj`

### 3. Skonfiguruj Looker Studio
- Wejdź na [lookerstudio.google.com](https://lookerstudio.google.com)
- Podłącz Google Sheets jako źródło danych
- Odtwórz dashboardy wg dokumentacji powyżej

### 4. Uruchom aplikację AI
- Otwórz `index.html` przez dowolny serwer HTTP
- Wklej klucz API Anthropic
- Zacznij analizować dane

---

## 📈 Kluczowe insighty biznesowe

| Obszar | Finding | Rekomendacja |
|--------|---------|--------------|
| 📦 Kategorie | Elektronika = 58% sprzedaży | Rozszerzyć asortyment, negocjować lepsze marże |
| 🛒 Koszyki | 387k PLN strat rocznie | Ulepszyć e-maile, dodać SMS reminder |
| 👥 VIP | Tylko 10% klientów | Program lojalnościowy z early access |
| 📧 E-mail | 67% koszyków z mailem vs 33% bez | Wysyłać maile do 100% porzuceń |
| 🏙️ Geo | Warszawa poniżej potencjału | Lokalne kampanie Google/Meta Ads |

---

## 👨‍💻 Autor

Projekt stworzony w celach edukacyjnych jako demonstracja możliwości narzędzi no-code + AI w analityce e-commerce.

---

## 📄 Licencja

MIT — możesz swobodnie używać, modyfikować i dystrybuować.
