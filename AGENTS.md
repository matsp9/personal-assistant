# Instrukcja dla każdego agenta

1. Zacznij od `PROJECT.md`, `docs/context/current-state.md` i `docs/workflow.md`, następnie przeczytaj bieżący task i potrzebny kod. Nie wymagaj historii rozmowy.
2. Najpierw zrozum stan poprzednika. Nie powtarzaj zakończonej pracy. Zapisuj postęp i konkretny następny krok przed przekazaniem projektu.
3. Buduj proste narzędzie jednej osoby na NAS. Dodatkowe usługi, frameworki, synchronizacja offline i automaty wymagają uzasadnienia. Nie dodawaj funkcji poza uzgodnionym zakresem.
4. Zapisuj decyzje z datą, powodem i statusem. Akceptację użytkownika wolno zapisać wyłącznie po jego rzeczywistej decyzji; podaj kontekst. Nie twórz fikcyjnych zgód.
5. Pracuj na danych syntetycznych. Nie czytaj danych produkcyjnych, prywatnych nagrań, sekretów ani rzeczywistych notatek. Nie kopiuj ich do repo, Issues, PR-ów, logów czy rozmów. `.gitignore` nie ogranicza dostępu do plików.
6. Oddziel narzędzia programistyczne od AI w aplikacji. Produkcyjne przetwarzanie prywatnych danych przez AI wymaga osobnej decyzji o dostawcy, retencji i kosztach.
7. Jedna spójna zmiana na branchu, z kryteriami i adekwatną weryfikacją. Nie deklaruj testów, których nie uruchomiono. W raporcie podaj komendy, wyniki i ograniczenia.
8. Nie rób force push, nie nadpisuj pracy użytkownika i nie wykonuj destrukcyjnych operacji na danych. Merge, wydanie i wdrożenie wymagają upoważnienia użytkownika; przygotuj wcześniej gotowy wynik do oceny.
9. Zmiany procesu można proponować i przygotowywać jako jawny diff. Nie instaluj ani nie zmieniaj uprawnień po cichu. Nie zakładaj, że konfiguracja Claude działa w Codexie.
10. Domyślnie pracuje jeden agent. Osobny reviewer, jeśli zostanie zlecony, dostaje task, diff i wyniki testów, a nie potrzebę odtwarzania całej rozmowy. Samokontrola nie jest niezależnym przeglądem.

Obecnie brak kodu: nie istnieją jeszcze komendy uruchomienia, lint ani testów aplikacji. Uzupełnij je po wyborze stosu i sprawdzeniu, nie zgaduj.
