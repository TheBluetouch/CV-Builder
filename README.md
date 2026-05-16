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
