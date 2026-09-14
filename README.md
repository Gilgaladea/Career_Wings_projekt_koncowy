# Dziennik dobrostanu

Aplikacja Flask: codzienna ankieta dobrostanu i tygodniowe podsumowanie
generowane przez Claude (Anthropic).

## Funkcje

- Ocena 5 obszarów (dieta, aktywność fizyczna, sen, zarządzanie stresem, satysfakcja)
- Refleksje i opcjonalny plik tekstowy (`.txt`), zapisywany w JSON
- Nawigacja po dniach (dziś i 14 dni wstecz)
- Możliwość jednorazowego wypełniania ankiety na każdy dzień przez jednego użytkownika
- Możliwość wypełnienia ankiety przed logowaniem (szkic, dokończenie po zalogowaniu)
- Podsumowanie tygodnia na podstawie 2–7 ankiet z ostatnich 7 dni (plik HTML do pobrania)
- Konta z hasłami hashowanymi (bcrypt)
- Rate limiting, ochrona przed prompt injection i nagłówki bezpieczeństwa (Talisman)

Rejestracja informuje, że treść ankiet i przesłanych plików jest przetwarzana
przez model AI Claude (Anthropic). Model: `claude-haiku-4-5-20251001`.

## Wymagania

- Python 3.10 lub nowszy
- Konto na console.anthropic.com z kluczem API
## Instalacja lokalna

1. Sklonuj repozytorium:

```bash
git clone https://github.com/Gilgaladea/Career_Wings_projekt_koncowy.git
cd Career_Wings_projekt_koncowy
```

2. Stwórz i aktywuj wirtualne środowisko:

```bash
python -m venv venv
```

Linux / macOS:

```bash
source venv/bin/activate
```

Windows (PowerShell):

```powershell
venv\Scripts\Activate.ps1
```

3. Zainstaluj zależności:

```bash
pip install -r requirements.txt
```

4. Stwórz plik `.env` w głównym folderze i uzupełnij:

```
ANTHROPIC_API_KEY=twoj-klucz-tutaj
SECRET_KEY=dowolny-dlugi-losowy-tekst
```

5. Uruchom aplikację:

```bash
python app.py
```

6. Otwórz w przeglądarce: http://127.0.0.1:8080

## Zmienne środowiskowe

| Nazwa | Opis | Wymagane |
|---|---|---|
| ANTHROPIC_API_KEY | Klucz API do Claude | Tak |
| SECRET_KEY | Sekret do podpisywania sesji Flaska | Tak |

## Struktura projektu

```
app.py              główny plik aplikacji (trasy, logika)
templates/          szablony HTML (Jinja2)
static/             CSS; foldery danych powstają w runtime
requirements.txt    lista zależności Pythona
```

Dane użytkowników (`users.json`), szkice ankiet, zapisane ankiety i wygenerowane
raporty HTML nie są w repozytorium (patrz `.gitignore`).

## Autor
Gilgaladea, projekt stworzony w ramach kursu.