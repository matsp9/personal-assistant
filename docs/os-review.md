# Ocena AI Development OS dla Personal Assistant

Data: 2026-10-14. Źródło: `C:/Users/mateu/Documents/Codex/ai-development-os-v0.5`.
Ocena dotyczy dostarczonej kopii, nie deklarowanego numeru w nazwie folderu.

## Wniosek

Zachować ideę „repo jako pamięć”, krótkie przyrosty, testy adekwatne do ryzyka i ochronę danych. Przyjąć uproszczony proces opisany w `personal-assistant/docs/workflow.md`. Pełny OS ma zbyt duży koszt dla aplikacji jednej osoby i wymaga adaptacji do Codexa. Nie kopiować go automatycznie ani nie uruchamiać skryptów konfigurujących GitHub w obecnym stanie.

## Ustalenia

| Obszar | Dowód w źródle | Ocena i zalecenie |
| --- | --- | --- |
| Wersjonowanie | README i OS: 0.3.0; polityka: 0.4.0; praktyki: 0.5.0 | Nie ma jednego wiarygodnego numeru procesu. Nowa adaptacja dostaje własną wersję 0.1.0 i zapis pochodzenia. |
| Przenośność | INNE-MODELE zaleca główne instrukcje w AGENTS; AGENTS odsyła do CLAUDE | Odwrócić zależność: AGENTS to instrukcja główna, CLAUDE tylko odsyłacz. Nie zakładać automatycznego czytania AGENTS przez każde narzędzie. |
| Dziedzina | Decimal i kwoty w AGENTS/CLAUDE; Django w OS; pracownicy i pieniądze w praktykach | Usunąć reguły poprzedniego produktu. Nie przesądzać technologii nowej aplikacji. |
| Rygor | Pełna ścieżka FEAT → ARCH → UI → TASK oraz siedem ról | Jeden prowadzący agent, krótki task i PR. Oddzielny przegląd dla zmian danych, dostępu i AI; dodatkowe role tylko gdy pomagają. |
| Sprzeczne procedury | OS: jeden PR na task i squash; praktyki: gałąź integracyjna, merge no-ff i jeden PR na paczkę | Wybrać jeden domyślny flow. Tu: jedna spójna zmiana → branch → PR → squash. |
| Zatwierdzenia | OS: człowiek ręcznie wpisuje accepted; praktyki: domyślna zgoda w części spraw | Użytkownik podejmuje decyzję w rozmowie; agent zapisuje jej treść, datę i kontekst. Żadnych fikcyjnych akceptacji ani obowiązku ręcznej edycji statusów. |
| CI i zabezpieczenia | INNE-MODELE przypisuje walidatorowi wykrywanie zmian zasad i akceptacji poza PO | `validate_os.py` sprawdza strukturę, odwołania i symulacje hooka. Nie audytuje diffu PR ani tożsamości autora akceptacji. Zielony wynik nie dowodzi ochrony działań Codexa. |
| GitHub | setup_github.py chroni main i wymaga tylko os-checks | Brak konfiguracji ochrony tagów i wydań; brak automatycznej gwarancji merge tylko przez człowieka. Dodać testy aplikacji do wymaganych checków po wyborze stosu. |
| Tożsamość | Agent używa tego samego logowania gh co użytkownik | GitHub nie odróżni człowieka od AI na podstawie autora commita. Reguły workflow są instrukcją, a nie granicą bezpieczeństwa. |
| Aktualizacje OS | update_os.py podmienia rdzeń, w tym AGENTS i CLAUDE; os_core_paths pomija OS-praktyki i INNE-MODELE | Automatyczna aktualizacja może nadpisać adaptację i pozostawić stare uzupełnienia. Tutaj aktualizacje tylko przez ocenę diffu i świadomy PR. |
| Dane | Zakaz danych produkcyjnych w narzędziach programistycznych | Zachować. Odróżnić go od runtime aplikacji, która może analizować prywatne dane za zgodą właściciela i z ustaloną polityką dostawcy AI. |
| Testy i taski | Limit około 300 linii, osobny czerwony commit, mutacje dla części funkcji | Rozmiar ma wynikać ze spójnego wyniku, nie liczby linii. Testy ryzykownych zachowań są potrzebne; ceremonie testowe nie są domyślne. |
| NAS | Praktyki wymagają spike, VPN, HTTPS i sprawdzonego backupu | Dobra baza. Dostęp na telefonie i nagrywanie trzeba sprawdzić na docelowym urządzeniu. Publiczne repo kodu nie oznacza publicznej aplikacji ani danych. |
| Backup | Praktyki zalecają usuwanie kopii z testów | Nie przenosić tego jako automatu. Retencja i usuwanie kopii wymagają jawnej polityki, szczególnie gdy mogły zawierać dane produkcyjne. |

## Co sprawdzono

- Przeczytano główne instrukcje, OS, praktyki, opis innych modeli, workflow startu i GitHuba, polityki, CI, szablon taska oraz skrypty walidacji, konfiguracji i aktualizacji. Przejrzano kod hooka; nie wykonano audytu bezpieczeństwa całego parsera.
- `python tooling/validate_os.py`: exit 0, PASS; 7 agentów, 10 komend, 10 szablonów, 86 przypadków hooka. To wynik testów symulowanych, nie test aktywnej ochrony w Codexie.
- Git, GitHub CLI, Python i Node dostępne w PATH. Docker nie został znaleziony w PATH; nie dowodzi to braku obsługi kontenerów na NAS-ie.
- `gh auth status`: exit 1; CLI zgłosiło nieważny token aktywnego konta `matsp9`. Wymaga ponownego logowania i weryfikacji.
- Nie wykonano setup_github ani update_os. Nie utworzono repo zdalnego, nie publikowano ani nie wdrażano aplikacji.

## Zalecany kierunek techniczny do dalszej oceny

Jedna aplikacja webowa dopasowana do telefonu, jedna baza i proste wdrożenie na NAS-ie. Kontener i SQLite są kandydatami, zależnymi od sprzętu i modelu dostępu. PWA można dodać, jeśli potrzebna będzie ikona i uruchamianie jak aplikacji. Nie zakładamy teraz synchronizacji offline, bazy wektorowej ani wielu usług.

Przepływ dyktowania ma oddzielać zapis wejścia, transkrypcję i klasyfikację. Błąd AI nie może zgubić wpisu. Użytkownik musi móc poprawić kategorię i datę. Zasady retencji audio, wysyłania danych do dostawcy i kosztów ustalimy przed integracją. Nie jest to jeszcze zatwierdzona specyfikacja funkcji.

## Źródła zewnętrzne

- [OpenAI: instrukcje AGENTS.md](https://learn.chatgpt.com/docs/agent-configuration/agents-md) — instrukcje repo dla Codexa.
- [OpenAI: workflow w repo, skills i CI](https://developers.openai.com/blog/skills-agents-sdk) — przenoszenie procedur do repozytorium.
- [GitHub: protected branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches) — ochrona publicznych repo na Free; prywatnych na odpowiednich planach płatnych.
- [MDN: getUserMedia](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/getUserMedia) — mikrofon w przeglądarce wymaga bezpiecznego kontekstu; na telefonie łączącym się z NAS-em planować HTTPS i zgodę na mikrofon.
