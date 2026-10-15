# TASK-0001 — fundament projektu

Status: in_progress. Ryzyko: niskie dla dokumentacji; konfiguracja dostępu wymaga sprawdzenia.
Branch: docs/TASK-0001-project-foundation. Commit: git log -1. PR: brak. Aktualizacja: 2026-10-15.

## Cel

Projekt ma jedno źródło instrukcji, jasny proces, repo dostępne zgodnie z wyborem właściciela i kontekst wystarczający dla nowego modelu.

## Kryteria zakończenia

- [x] Ocena źródłowych zasad z konkretnymi ustaleniami.
- [x] Propozycja uproszczonego workflow i instrukcji AGENTS.
- [x] Spis potwierdzonych potrzeb i nierozstrzygniętych decyzji.
- [x] Lista konfiguracji użytkownika i stanu narzędzi.
- [x] Zapis rzeczywistej decyzji właściciela o procesie: ADR-0001.
- [ ] Potwierdzone konto, nazwa, widoczność repo i licencja, jeśli publiczne.
- [ ] Poprawne logowanie gh, utworzone właściwe repo i zapisany URL.
- [x] Pakiet dokumentów zapisany w lokalnym repo; nowa sesja może wskazać następny krok bez historii rozmowy.

## Dziennik i weryfikacja

2026-10-14: źródłowy `python tooling/validate_os.py` zakończony exit 0, 86 przypadków hooka. `gh auth status`: exit 1, zgłoszony nieważny token. To nie są testy aplikacji. Sprawdzono 9 niepustych dokumentów Markdown i lokalne linki: 0 błędów; treść dokumentów przejrzana.

## Poza bieżącym taskiem

2026-10-15: zaakceptowane proces 0.1.0, publiczne repo personal-assistant i MIT. Przygotowano lokalne repo, instrukcje, licencję, gitignore i gitattributes; raport OS przeniesiono również do repo, by nie zależał od plików zewnętrznych. Ponowne gh auth status nadal zgłasza nieważny token. Docelowe konto i publikacja wymagają sprawdzenia po logowaniu. Nie uruchomiono CI na GitHubie.

Implementacja funkcji, wybór dostawcy AI, produkcyjne dane, wdrożenie i szczegółowa architektura. Kolejny krok po fundamencie: określenie pierwszego zakresu i sprawdzenie NAS-a.
