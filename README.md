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

## Zapis do PDF

1. Kliknij przycisk **Drukuj / Zapisz jako PDF**
2. W oknie druku wybierz drukarkę **PDF**
3. Ustaw marginesy na **Brak**
4. Odznacz opcję **Drukuj nagłówki i stopki** (Safari) — inaczej treść nie zmieści sie na jednej stronie
5. Kliknij Drukuj

## Kolor paska bocznego

Zmień kolor podając wartość hex (`#3C3C3C`) lub klikając na picker. Kolor zapisuje sie automatycznie.

## Import i eksport danych

- **Eksport JSON** zapisuje wszystkie dane formularza do pliku `cv_dane.json`. Zdjecie nie jest eksportowane (zostaje tylko w localStorage).
- **Import JSON** wczytuje wczesniej wyeksportowany plik i przywraca wszystkie pola.

## Zdjecie

Format kwadratowy. Plik JPG lub PNG. Zdjecie przechowywane jest w localStorage przeglądarki — nie jest eksportowane do JSON z uwagi na rozmiar.

## Dane lokalne

Wszystkie dane zapisywane są automatycznie w `localStorage` pod kluczem `cv2_data`. Dane nie opuszczają przeglądarki.

Czyszczenie danych: otwórz narzędzia deweloperskie przeglądarki, przejdź do Application > Local Storage i usuń klucz `cv2_data`.

## Architektura

Cały projekt to jeden plik HTML zawierający CSS, HTML i JavaScript. Brak zewnętrznych zależności — ikony jako inline SVG, brak CDN, brak frameworków.

```
cv-builder.html
├── <style>       CSS variables, style edytora, style CV, @media print
├── #editor       panel boczny (360px) — formularz z sekcjami
├── #preview-panel  podgląd CV na żywo
└── <script>      stan aplikacji, renderowanie, persistence (localStorage)
```

## FullPrint
<img width="1913" height="1017" alt="image" src="https://github.com/user-attachments/assets/364d34f5-8f38-4b37-84cf-94dcaf63404d" />


## Przykładowe dane
{
  "name": "Anna Kowalska",
  "title": "Product Manager",
  "email": "anna.kowalska@gmail.com",
  "phone": "+48 512 345 678",
  "birth": "15.03.1993",
  "address": "ul. Marszalkowska 12, Warszawa",
  "link": "linkedin.com/in/anna-kowalska",
  "color": "#2C4A7C",
  "about": "Product Manager z 6-letnim doswiadczeniem w rozwijaniu produktow cyfrowych w srodowisku agile. Specjalizuje sie w laczeniu perspektywy uzytkownika z celami biznesowymi. Doswiadczona w pracy z zespolami rozproszonymi i zarzadzaniu roadmapa produktu od fazy odkrycia po wdrozenie.",
  "skills": [
    { "name": "Zarzadzanie roadmapa produktu" },
    { "name": "Metodyki Agile / Scrum" },
    { "name": "Analiza danych i metryki (GA4, Mixpanel)" },
    { "name": "Warsztatry UX i user research" },
    { "name": "SQL — poziom podstawowy" },
    { "name": "Figma" }
  ],
  "langs": [
    { "name": "Polski",   "level": "Ojczysty" },
    { "name": "Angielski", "level": "C1" },
    { "name": "Niemiecki", "level": "B1" }
  ],
  "exps": [
    {
      "role": "Senior Product Manager",
      "company": "Allegro / Warszawa",
      "dates": "03.2021 – obecnie",
      "desc": "Prowadzenie produktu platnosci — 4 mln aktywnych uzytkownikow miesiecznie\nZwiekszylem konwersje na etapie kasy o 18% przez optymalizacje UX\nKoordynacja zespolu 3 deweloperow, 1 designera i analityka\nWprowadzenie kwartalnego cyklu OKR dla pionu produktowego"
    },
    {
      "role": "Product Manager",
      "company": "Ailleron / Krakow",
      "dates": "06.2018 – 02.2021",
      "desc": "Zarzadzanie aplikacja mobilna do bankowosci — 500 tys. uzytkownikow\nWdrozenie funkcji BLIK w czasie 4 miesiecy od koncepcji do produkcji\nCiagla wspolpraca z compliance i prawnikami w zakresie PSD2\nNPS produktu wzrost z 34 do 61 w ciagu 18 miesiecy"
    },
    {
      "role": "Junior Product Owner",
      "company": "Netguru / Poznan",
      "dates": "09.2016 – 05.2018",
      "desc": "Wsparcie PM przy definiowaniu backlogu dla klientow z sektora fintech\nProwadzenie sesji refinementu i planowania sprintu\nDokumentacja wymagan i historyjek uzytkownikow"
    }
  ],
  "edus": [
    {
      "school": "Szkola Glowna Handlowa w Warszawie",
      "field": "Magister Zarzadzania",
      "spec": "Zarzadzanie projektami i innowacje",
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
      "name": "SQL dla analitykow danych",
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
      "name": "Najlepszy projekt wewnetrzny — optymalizacja kasy",
      "org": "Allegro",
      "date": "2022"
    }
  ],
  "interests": "Gorska turystyka piesza, fotografia uliczna, podcasts o psychologii decyzji.",
  "consent": "Wyrażam zgodę na przetwarzanie moich danych osobowych w celu prowadzenia rekrutacji na aplikowane przeze mnie stanowisko."
}
