# Karta projektu

Status: wstępny zakres; proces zaakceptowany. Aktualizacja: 2026-10-15.

## Potwierdzone potrzeby użytkownika

- Osobisty asystent: zadania, listy rzeczy do zrobienia, notatki i centrum wiedzy.
- Dostęp z telefonu; dyktowanie i automatyczne rozpoznawanie rodzaju wpisu.
- Własny NAS jako miejsce uruchomienia prostej aplikacji webowej.
- Umiarkowana złożoność, użytek osobisty.
- Dokumentacja pozwalająca innemu modelowi przejąć pracę w dowolnym momencie.
- Publiczne repozytorium kodu na GitHubie — decyzja użytkownika z 2026-10-15.
- NAS: Synology DS218+, DSM 7.1.1; telefon: iPhone 17 Pro Max — informacje użytkownika z 2026-10-15.
- Docker jest zainstalowany i używany na NAS-ie; dostęp zdalny przez OpenVPN — potwierdzenie użytkownika z 2026-10-15.

## Granice obecnego etapu

Ustalamy proces pracy. Szczegółowe funkcje, stos, dostawca AI i sposób wdrożenia pozostają do omówienia. Nie zakładamy aplikacji natywnej, systemu dla wielu użytkowników ani rozbudowanej infrastruktury.

## Robocze kierunki

Jedna aplikacja webowa, interfejs na telefon, prosta baza, backup i eksport. Kod publiczny; prywatny dostęp do aplikacji jest rekomendacją do uzgodnienia. Docelowa aplikacja będzie używała prawdziwych danych i potrzebuje ochrony od pierwszego wdrożenia, mimo jednego użytkownika.

## Otwarte decyzje

1. Faktyczna ilość RAM, dostępne zasoby i wersja pakietu Docker na NAS-ie.
2. Przeglądarka na iPhonie; konfiguracja HTTPS dla aplikacji dostępnej przez OpenVPN.
3. Potwierdzenie działania logowania GitHub CLI i konta docelowego. Nazwa personal-assistant i licencja MIT zatwierdzone.
4. Zgoda lub brak zgody na wysyłanie audio/tekstu do zewnętrznego AI oraz budżet.
5. Pierwszy mały zakres użytecznej wersji.

Proces projektu: lokalna adaptacja AI Development OS, zaakceptowana wersja 0.1.0. Obowiązuje dokument `docs/workflow.md`; szablon źródłowy nie jest importowany jako aktywna konfiguracja. Decyzja: ADR-0001.
