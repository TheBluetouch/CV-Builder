# CV Builder

Lokalny generator CV działający jako pojedynczy plik HTML. Nie wymaga serwera, instalacji ani połączenia z internetem. Otwierasz plik w przeglądarce, wypełniasz formularz i drukujesz do PDF.

## Uruchomienie

Otwórz `cv-builder.html` bezpośrednio w przeglądarce (Chrome lub Safari).

## Jak używać

Lewy panel to edytor — zmiany widoczne są na żywo po prawej stronie.

**Dostępne sekcje:**
- Dane osobowe (imię, email, telefon, adres, data urodzenia, link)
- O mnie
- Umiejętności
- Znajomość języków (z poziomem CEFR)
- Doświadczenie zawodowe
- Wykształcenie
- Kursy i certyfikaty
- Osiągnięcia
- Zainteresowania
- Klauzula RODO

## Język CV

Przyciski **PL / EN** w górnej części edytora przełączają język etykiet w CV — nagłówki sekcji, etykiety kontaktu i domyślna klauzula zgody. Edytor pozostaje po polsku. Wybrany język zapisuje się automatycznie i jest uwzględniany przy imporcie JSON.

## Zapis do PDF

1. Kliknij przycisk **Drukuj / Zapisz jako PDF**
2. W oknie druku wybierz drukarkę **PDF**
3. Ustaw marginesy na **Brak**
4. Odznacz opcję **Drukuj nagłówki i stopki** (Safari) — inaczej treść nie zmiesci sie na jednej stronie
5. Kliknij Drukuj

## Kolor paska bocznego

Zmień kolor podając wartość hex (`#3C3C3C`) lub klikając na picker. Kolor zapisuje sie automatycznie.

## Import i eksport danych

- **Eksport JSON** zapisuje wszystkie dane formularza do pliku `cv_dane.json`. Zdjecie nie jest eksportowane (zostaje tylko w localStorage).
- **Import JSON** wczytuje wczesniej wyeksportowany plik i przywraca wszystkie pola, w tym jezyk CV.

Klucz `lang` w pliku JSON (`"pl"` lub `"en"`) automatycznie przełącza język po imporcie.

## Przykładowe dane

- `cv_dane_pl.json` — przykładowe CV po polsku
```
{
  "lang": "pl",
  "name": "Anna Kowalska",
  "title": "Product Manager",
  "email": "anna.kowalska@gmail.com",
  "phone": "+48 512 345 678",
  "birth": "15.03.1993",
  "address": "ul. Marszałkowska 12, Warszawa",
  "link": "linkedin.com/in/anna-kowalska",
  "color": "#2C4A7C",
  "about": "Product Manager z 6-letnim doświadczeniem w rozwijaniu produktów cyfrowych w środowisku agile. Specjalizuję się w łączeniu perspektywy użytkownika z celami biznesowymi. Doświadczona w pracy z zespołami rozproszonymi i zarządzaniu roadmapą produktu od fazy odkrycia po wdrożenie.",
  "skills": [
    { "name": "Zarządzanie roadmapą produktu" },
    { "name": "Metodyki Agile / Scrum" },
    { "name": "Analiza danych i metryki (GA4, Mixpanel)" },
    { "name": "Warsztaty UX i user research" },
    { "name": "SQL — poziom podstawowy" },
    { "name": "Figma" }
  ],
  "langs": [
    { "name": "Polski",    "level": "Ojczysty" },
    { "name": "Angielski", "level": "C1" },
    { "name": "Niemiecki", "level": "B1" }
  ],
  "exps": [
    {
      "role": "Senior Product Manager",
      "company": "Allegro / Warszawa",
      "dates": "03.2021 – obecnie",
      "desc": "Prowadzenie produktu płatności — 4 mln aktywnych użytkowników miesięcznie\nZwiększyłam konwersję na etapie kasy o 18% przez optymalizację UX\nKoordynacja zespołu 3 deweloperów, 1 designera i analityka\nWprowadzenie kwartalnego cyklu OKR dla pionu produktowego"
    },
    {
      "role": "Product Manager",
      "company": "Ailleron / Kraków",
      "dates": "06.2018 – 02.2021",
      "desc": "Zarządzanie aplikacją mobilną do bankowości — 500 tys. użytkowników\nWdrożenie funkcji BLIK w czasie 4 miesięcy od koncepcji do produkcji\nWspółpraca z działem compliance i prawnikami w zakresie PSD2\nNPS produktu wzrósł z 34 do 61 w ciągu 18 miesięcy"
    },
    {
      "role": "Junior Product Owner",
      "company": "Netguru / Poznań",
      "dates": "09.2016 – 05.2018",
      "desc": "Wsparcie PM przy definiowaniu backlogu dla klientów z sektora fintech\nProwadzenie sesji refinementu i planowania sprintu\nDokumentacja wymagań i historyjek użytkowników"
    }
  ],
  "edus": [
    {
      "school": "Szkoła Główna Handlowa w Warszawie",
      "field": "Magister Zarządzania",
      "spec": "Zarządzanie projektami i innowacje",
      "dates": "2014 – 2016"
    },
    {
      "school": "Uniwersytet Ekonomiczny w Poznaniu",
      "field": "Licencjat Ekonomii",
      "spec": "",
      "dates": "2011 – 2014"
    }
  ],
  "courses": [
    {
      "name": "Professional Scrum Product Owner I (PSPO I)",
      "org": "Scrum.org",
      "date": "2020"
    },
    {
      "name": "Google Analytics 4 Certification",
      "org": "Google",
      "date": "2022"
    },
    {
      "name": "SQL dla analityków danych",
      "org": "DataCamp",
      "date": "2021"
    }
  ],
  "achievements": [
    {
      "name": "Product Manager roku w kategorii fintech",
      "org": "Mobile Trends Awards",
      "date": "2023"
    },
    {
      "name": "Najlepszy projekt wewnętrzny — optymalizacja kasy",
      "org": "Allegro",
      "date": "2022"
    }
  ],
  "interests": "Górska turystyka piesza, fotografia uliczna, podcasty o psychologii decyzji.",
  "consent": "Wyrażam zgodę na przetwarzanie moich danych osobowych w celu prowadzenia rekrutacji na aplikowane przeze mnie stanowisko."
}
```
- `cv_dane_en.json` — przykładowe CV po angielsku
```
{
  "lang": "en",
  "name": "Anna Kowalska",
  "title": "Product Manager",
  "email": "anna.kowalska@gmail.com",
  "phone": "+48 512 345 678",
  "birth": "15.03.1993",
  "address": "Marszalkowska 12, Warsaw, Poland",
  "link": "linkedin.com/in/anna-kowalska",
  "color": "#2C4A7C",
  "about": "Product Manager with 6 years of experience building digital products in agile environments. Specialising in bridging user needs with business goals. Proven track record of leading cross-functional teams and managing product roadmaps from discovery through to delivery.",
  "skills": [
    { "name": "Product roadmap management" },
    { "name": "Agile / Scrum methodologies" },
    { "name": "Data analysis and metrics (GA4, Mixpanel)" },
    { "name": "UX workshops and user research" },
    { "name": "SQL — foundational level" },
    { "name": "Figma" }
  ],
  "langs": [
    { "name": "Polish",   "level": "Ojczysty" },
    { "name": "English",  "level": "C1" },
    { "name": "German",   "level": "B1" }
  ],
  "exps": [
    {
      "role": "Senior Product Manager",
      "company": "Allegro / Warsaw",
      "dates": "Mar 2021 – present",
      "desc": "Leading the payments product serving 4M monthly active users\nImproved checkout conversion by 18% through UX optimisation\nManaging a cross-functional team of 3 engineers, 1 designer and 1 analyst\nIntroduced a quarterly OKR cycle across the product division"
    },
    {
      "role": "Product Manager",
      "company": "Ailleron / Krakow",
      "dates": "Jun 2018 – Feb 2021",
      "desc": "Owned a mobile banking app with 500k users\nDelivered BLIK payment feature in 4 months from concept to production\nCollaborated with legal and compliance teams on PSD2 requirements\nGrew product NPS from 34 to 61 over 18 months"
    },
    {
      "role": "Junior Product Owner",
      "company": "Netguru / Poznan",
      "dates": "Sep 2016 – May 2018",
      "desc": "Supported PM in backlog definition for fintech clients\nFacilitated sprint planning and refinement sessions\nAuthored user stories and requirements documentation"
    }
  ],
  "edus": [
    {
      "school": "Warsaw School of Economics (SGH)",
      "field": "Master of Management",
      "spec": "Project Management and Innovation",
      "dates": "2014 – 2016"
    },
    {
      "school": "Poznan University of Economics",
      "field": "Bachelor of Economics",
      "spec": "",
      "dates": "2011 – 2014"
    }
  ],
  "courses": [
    {
      "name": "Professional Scrum Product Owner I (PSPO I)",
      "org": "Scrum.org",
      "date": "2020"
    },
    {
      "name": "Google Analytics 4 Certification",
      "org": "Google",
      "date": "2022"
    },
    {
      "name": "SQL for Data Analysts",
      "org": "DataCamp",
      "date": "2021"
    }
  ],
  "achievements": [
    {
      "name": "Product Manager of the Year — fintech category",
      "org": "Mobile Trends Awards",
      "date": "2023"
    },
    {
      "name": "Best Internal Project — checkout optimisation",
      "org": "Allegro",
      "date": "2022"
    }
  ],
  "interests": "Mountain hiking, street photography, podcasts on decision psychology.",
  "consent": "I consent to the processing of my personal data for the purposes of recruitment for the position I am applying for."
}
```

## Zdjecie

Format kwadratowy. Plik JPG lub PNG. Zdjecie przechowywane jest w localStorage przeglądarki — nie jest eksportowane do JSON z uwagi na rozmiar.

## Dane lokalne

Wszystkie dane zapisywane są automatycznie w `localStorage` pod kluczem `cv2_data`. Dane nie opuszczają przeglądarki.

Czyszczenie danych: otwórz narzędzia deweloperskie przeglądarki, przejdź do Application > Local Storage i usuń klucz `cv2_data`.

## Architektura

Cały projekt to jeden plik HTML zawierający CSS, HTML i JavaScript. Brak zewnętrznych zależności — ikony jako inline SVG, brak CDN, brak frameworków.

```
cv-builder.html
├── <style>        CSS variables, style edytora, style CV, @media print
├── #editor        panel boczny (360px) — formularz z sekcjami i przełącznikiem PL/EN
├── #preview-panel podgląd CV na żywo
└── <script>       tłumaczenia, stan aplikacji, renderowanie, persistence (localStorage)
```

## FullPrint
<img width="1913" height="1017" alt="image" src="https://github.com/user-attachments/assets/364d34f5-8f38-4b37-84cf-94dcaf63404d" />
