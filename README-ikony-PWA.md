# MIGO.planLekcji — pakiet PWA (manifest + ikony)

## Co jest w paczce
- `migo-plan-lekcji.html` — sama aplikacja (bez zmian w działaniu, tylko dodany link do manifestu w `<head>`)
- `manifest.json` — plik PWA opisujący nazwę, kolory i ikony aplikacji
- `icons/` — 4 pliki ikon. **Na razie wygenerowane automatycznie z Twojego loga MIGO.apps** (żeby manifest od razu działał), ale możesz je swobodnie podmienić na własne:
  - `icon-192.png` (192×192) — zwykła ikona
  - `icon-512.png` (512×512) — zwykła ikona, większa (użyje np. splash screen)
  - `icon-192-maskable.png` / `icon-512-maskable.png` — wersje „maskable”: system Android może je przyciąć do koła/zaokrąglonego kwadratu, dlatego ważne fragmenty grafiki powinny mieścić się w środkowych ~60% obrazka

## Jak podmienić na własne ikony
1. Przygotuj kwadratowe grafiki PNG w dokładnie takich wymiarach jak wyżej.
2. Dla wersji maskable zostaw margines (bezpieczna strefa) — ok. 20% wolnego miejsca dookoła głównego motywu.
3. Podmień pliki w folderze `icons/`, zachowując **te same nazwy**. Nic więcej nie trzeba zmieniać — `manifest.json` już się do nich odwołuje.

## Jak to wdrożyć, żeby dało się „zainstalować” na telefonie
Te pliki muszą leżeć razem na serwerze (ten sam folder), obsługiwanym przez **https** — samo otwarcie pliku HTML z dysku (`file://`) nie wystarczy, żeby telefon zaproponował instalację. Najprostsze opcje:
- GitHub Pages / Netlify / Vercel (darmowe hostingi statycznych stron)
- dowolny hosting, na który wrzucisz te pliki

Po wejściu na taki adres w Chrome na Androidzie telefon sam zaproponuje „Dodaj do ekranu głównego” / zainstalowanie aplikacji.

## Krok w stronę Google Play
Samo PWA da się „zainstalować” jako ikonę, ale to jeszcze nie to samo, co aplikacja w Google Play. Do sklepu potrzebne będzie dodatkowo:
- opakowanie PWA jako **TWA (Trusted Web Activity)** przez Android Studio / Bubblewrap,
- konto dewelopera Google Play (jednorazowa opłata),
- polityka prywatności (link),
- ikony/grafiki na stronę w sklepie (osobne wymagania wymiarowe).

To już osobny, większy krok — daj znać, kiedy będziesz gotowy, to go rozpiszę podobnie jak poprzednie.
