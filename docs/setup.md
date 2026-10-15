# Konfiguracja przed implementacją

## Co już sprawdzono

Git 2.55.0, GitHub CLI, Python i Node są dostępne. Docker nie został znaleziony w PATH na tym komputerze. `gh auth status` 2026-10-14 zgłosił nieważny token konta matsp9. Użytkownik 2026-10-15 wybrał publiczne repo i podał NAS Synology DS218+, DSM 7.1.1 oraz iPhone 17 Pro Max.

Specyfikacja DS218+ podaje Intel Celeron J3355 i fabryczne 2 GB RAM; faktyczna pamięć urządzenia nie została sprawdzona. W DSM 7.1 pakiet kontenerów nazywa się Docker; nazwa Container Manager dotyczy DSM 7.2 i nowszych. Użytkownik potwierdził 2026-10-15, że używa już Dockera na NAS-ie i łączy się przez OpenVPN. Wersja pakietu pozostaje do sprawdzenia przed wdrożeniem. Przed produkcją sprawdzimy aktualizacje DSM i pakietów; nie przeprowadzamy aktualizacji systemu w ramach ustalania procesu.

Źródła: [specyfikacja DS218+](https://global.download.synology.com/download/Document/Hardware/ProductSpec/DiskStation/18-year/DS218%2B/enu/Product_Spec_DS218%2B_enu.pdf), [nazwy pakietów według DSM](https://kb.synology.com/en-global/DSM/tutorial/How_do_I_back_up_Docker_containers).

## Kroki użytkownika

1. W terminalu zaloguj ponownie GitHub CLI: `gh auth login -h github.com`. Wybierz przeglądarkę i docelowe konto. Następnie `gh auth status`. Nie przesyłaj tokenu do rozmowy. To logowanie do konta jest działaniem użytkownika; agent nie potrzebuje poznawać sekretu.
2. Nazwa personal-assistant, publiczna widoczność i MIT są zatwierdzone. Po logowaniu sprawdzimy docelowe konto i dostępność nazwy.
3. Lokalne repo jest już przygotowane w katalogu tego dokumentacyjnego projektu; zdalne czeka na logowanie. Można otworzyć jego folder jako lokalny projekt w Codexie. Startowe polecenie: „Przeczytaj AGENTS.md i docs/context/current-state.md, sprawdź stan repo i kontynuuj bieżący task”.
4. Przy przygotowaniu wdrożenia sprawdź ilość RAM w Centrum informacji oraz wersję Dockera. Instalacja Dockera i dostęp przez OpenVPN są już potwierdzone. Nie udostępniaj haseł ani administracyjnego dostępu na tym etapie.

## Co przygotuje agent po tych ustaleniach

- Repo aplikacji i pierwszą gałąź, dokumentację z tego pakietu, `.gitignore` dobrany do stosu oraz komendy lokalnego startu.
- CI i ochronę `main`: PR, właściwe testy, zakaz force push i usuwania gałęzi głównej. Na koncie osobistym publiczne repo obsługuje protected branches w GitHub Free; prywatne wymaga odpowiedniego planu, np. Pro. Potwierdzimy dostępność przed zmianą ustawień.
- Krótki test zgodności NAS-a przed pisaniem wdrożenia. Kierunek: istniejący OpenVPN i HTTPS aplikacji; konfigurację certyfikatu i dostęp z iPhone'a sprawdzimy przed uruchomieniem mikrofonu.
- Instrukcję backupu, odtwarzania i aktualizacji przed użyciem prywatnych danych.

Nie trzeba na tym etapie instalować Claude Code, MCP ani siedmiu agentów. Do pracy na lokalnym repo i PR-ach może wystarczyć Git oraz zalogowane `gh`; plugin GitHub jest opcjonalny. Podłączenie repo dla sesji chmurowych innych narzędzi ustalimy, gdy wybierzesz takie narzędzie.

Klucz do wybranego AI będzie potrzebny dopiero przy integracji, jeśli wybierzemy zewnętrzne API. Na razie nie kupujemy usług ani nie zapisujemy kluczy. Przed tym etapem ustalamy budżet i politykę danych.

## Źródła

- [Instrukcje repo w Codexie](https://learn.chatgpt.com/docs/agent-configuration/agents-md).
- [Dostępność protected branches na planach GitHub](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches).
- [Mikrofon w bezpiecznym kontekście przeglądarki](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getUserMedia).
