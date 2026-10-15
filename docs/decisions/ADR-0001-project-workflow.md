# ADR-0001 — prosty proces i publiczne repo

Status: accepted. Data: 2026-10-15.

Użytkownik zlecił ocenę AI Development OS i przygotowanie sposobu pracy dla prostej aplikacji osobistej. Po przedstawieniu uproszczonego standardu polecił: „Ok, zatem działajmy”. Przyjmujemy docs/workflow.md w wersji 0.1.0: jeden agent prowadzący, krótkie taski, branch i PR, testy proporcjonalne do ryzyka, pamięć w repo.

Użytkownik osobno wybrał publiczne repozytorium oraz potwierdził „personal-assistant + MIT”. Repo będzie nosić nazwę personal-assistant; kod i dokumentacja projektu mają licencję MIT. Nie zmienia to licencji cudzych zależności ani praw do materiałów źródłowych. Prywatne dane aplikacji nie są publikowane.

Nie importujemy hooków Claude Code i nie aktualizujemy procesu automatycznie ze źródłowego OS. Trwałe decyzje zapisujemy w repo, aby dowolny kolejny model mógł przejąć pracę.
