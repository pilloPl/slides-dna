---

# 5. Jak to wpływa na rolę developera i architekta

---

## Przykład: granice językowe modułów

---

## Granice: Kiedyś

Dobry architekt (albo bardzo doświadczony senior):

- pilnował **języka modułów**
- widział, że:
  - „status”, „workflow”, „rule”, „policy” //TODO zmienic przyklad
  - zaczynają znaczyć coś innego w innym module
- czuł, że:
  - język jednego kontekstu **przecieka** do drugiego  
  - mimo że:
    - testy przechodzą (nawet te architektoniczne)  
    - architektura „technicznie” się zgadza  

➡️ To był **skill i doświadczenie**

---

## Co było trudne
- nie dało się tego łatwo:
  - przetestować
  - opisać w typach
  - złapać statyczną analizą

Jeśli architekt **nie zauważył w porę**:
- system powoli tracił spójność
- moduły zaczynały „gadać cudzym językiem”
- koszt zmian rósł, choć kod wyglądał OK

---

## Co się realnie zmienia

### Teraz architekt:

- nadal **odpowiada za granice**
- nadal **rozumie język modułów**
- ale **nie musi być jedynym sensorem** i próg wejścia jest mniejszy

Może mieć:  
➡️ **agenta wpiętego w SDLC jako sanity check**
TODO jkubrynski - odniesinie do Twojej czesci tego jak wpinac w SDLC 

---

## Ten sam przykład — teraz

Zmiana w PR:
- technicznie poprawna
- testy przechodzą
- architektura się „nie wali”

Agent w code review:
> „Ten PR wprowadza pojęcia z modułu A  
> do modułu B.  
> Nazwy i odpowiedzialności zaczynają się mieszać.”

➡️ **Alarm, nie decyzja**

---

## Kluczowa różnica

### Kiedyś
- tylko najlepsi architekci
- tylko z doświadczenia
- tylko „w głowie”

### Teraz
- ta sama odpowiedzialność
- ale:
  - **wcześniejszy sygnał**
  - **niższy punkt wejścia i tańszy feedback**
  - **mniej cichych erozji architektury**
---

TODO: screen ze skillem agenta

## Technologia buduje przewagę konkurencyjną

Ale nie sama technologia.

➡️ **Przewagę buduje ktoś, kto potrafi ją zastosować w systemie i procesie**

Biznes:
- nie wymyśli MCP  
- nie wymyśli agentów  
- nie wymyśli pluginów  
- nie zna ograniczeń LLM  

➡️ **To nie jest ich rola**

---

## Nowa odpowiedzialność po stronie technicznej

Jeśli AI:
- zmienia sposób wytwarzania  
- zmienia tempo dostarczania  
- zmienia architekturę  

➡️ to **developer i architekt** muszą:
- zaproponować rozwiązania  
- ocenić ryzyko  
- ustawić procesy  

---

## Przykład: „jak trudny to problem naprawdę jest?”

---

## Kiedyś

Dobry architekt / senior:

- miał **w głowie zestaw pytań**
- po kilku zdaniach wiedział:
  - czy to jest problem prosty czy złożony
  - czy to jest domena, proces czy tylko glue code
  - czy potrzebujemy:
    - jednego seniora
    - zespołu
    - długiego projektu
    - czy wystarczą testy jednostkowe

Te pytania:
- nie były zapisane
- nie były formalne
- były efektem doświadczenia

➡️ **Klasa problemu była rozpoznawana intuicyjnie**

---

## Co te pytania dawały?

Na ich podstawie architekt:
- dobierał **klasę zawodników**
- dobierał **strategię testowania**
- wybierał **building blocki**
- wiedział:
  - gdzie będzie ból
  - gdzie ryzyko
  - gdzie „nie wolno improwizować”

Ale:
➡️ ta wiedza była **w głowie kilku osób**

---

## Problem

Jeśli:
- dobrego architekta nie było
- albo był przeciążony
- albo wszedł za późno

To:
- złożony problem wyglądał jak prosty
- decyzje zapadały „za nisko”
- testy nie łapały prawdziwego ryzyka

➡️ **Architektura psuła się legalnie**

---

## Co się realnie zmienia

### Teraz

- nadal ma te pytania
- nadal odpowiada za decyzję
- **ale może je sprotokolizować**

Czyli:
➡️ zamienić intuicję w **jawny zestaw pytań**

---

## Teraz

Zmiana / feature / ticket trafia do systemu.

Zanim padnie decyzja „jak to robimy”,
agent zadaje **meta-pytania**:

- czy to zmienia stan domeny?
- czy to chroni niezmienniki?
- czy to proces z krokami?
- czy jest równoległość?
- czy dane mogą się zmienić w trakcie?

➡️ **Jeszcze bez implementacji**

---

## Co robi agent

Agent:
- nie projektuje architektury
- nie wybiera wzorców „na twardo”
- **pomaga nazwać klasę problemu**

Np.:
> „To wygląda na logikę procesową.  
> Czy proces jest krótki czy długi?”

Albo:
> „To wygląda na ochronę niezmienników.  
> Czy wielu użytkowników może robić to równolegle?”

➡️ **Wymusza doprecyzowanie**

---

TODO: screen agenta
TODO: czy moge powiedziec, ze my damy te skille za darmo?

## Co robi architekt

Architekt:
- widzi odpowiedzi
- rozumie konsekwencje
- decyduje:
  - jaka architektura
  - jakie testy
  - jaki poziom ostrożności
  - kto powinien to robić

➡️ AI **nie podejmuje decyzji**
➡️ AI **nie pozwala jej podjąć w ciemno**

---

## Kluczowa różnica

### Kiedyś
- pytania były w głowie
- działało tylko z najlepszymi
- łatwo było je pominąć

### Teraz
- te same pytania
- ale:
  - jawne
  - powtarzalne
  - zadawane zawsze
  - nawet gdy architekt jest zajęty

➡️ **Mniej przypadkowych decyzji**

---

## Co to NIE jest

To nie jest:
- automatyczna architektura
- generator wzorców
- „AI decyduje za nas”


---

## I tu pojawia się SDLC

Te pytania:
- nie muszą czekać na review
- nie muszą być zadane „w głowie”

Mogą być:
➡️ **wpięte w proces wytwórczy**

---

## Przykład w praktyce

Agent w SDLC:
- czyta **User Story z Jiry**
- zagląda do:
  - opisów akceptacyjnych
  - diagramów z Confluence
  - kontekstu domenowego
TODO jkubrybski - czy o wpieciu w jire mowisz?

---

## Przykład: Search

---

## Kiedyś: 

Cel:
➡️ **żeby towary były łatwiej znajdowane**

Ale rozwiązania były „klasyczne”:

- SEO / content  
- feedy do marketplace’ów i porównywarek  
- własna wyszukiwarka + facety  
- integracje B2B / partner API  
- kampanie 

Architekt zwykle dostawał to jako:
> „Potrzebujemy lepszej widoczności produktów”


---

## Teraz: MCP

Ten sam cel:
➡️ **produkty mają być znajdowane**

Tylko nowy kanał to:
- agent po stronie klienta (B2C)
- agent po stronie supportu i sales (B2E)
- asystent zakupowy w aplikacji
- automatyczne rekomendacje i Q&A na katalogu

I biznes wciąż nie powie:
> „Zbudujmy MCP do produktów”

Bo nie musi wiedzieć, że MCP istnieje.

---

## Teraz: to architekt może wyjść z propozycją

➡️ Architekt / senior dev mówi:

> „Wystawmy katalog produktów jako MCP.
> Dzięki temu asystent/agent będzie mógł:
> - wyszukiwać produkty (po cechach, dostępności, cenie)
> - dopytywać o brakujące kryteria
> - przygotować shortlistę i argumentację
> - zasilić support/sales w real-time”

Agent dostaje możliwość:
- `searchProducts(query, filters)`
- `getProduct(productId)`
- `getAvailability(productId, location)`
- `getPrice(productId, customerSegment)`

Efekt:
- użytkownik pisze „szukam butów do biegania na zimę do 600 zł”
- agent robi doprecyzowanie + filtrację
- agent pokazuje 3–5 opcji wraz z uzasadnieniem

➡️ **Nowy kanał „odkrywania produktów”** bez przebudowy całego frontu.

---

## Nie jest to za darmo

### 1) Wersjonowanie

### 2) Granice danych (scope)
- co agent może zobaczyć (a czego nie)
  - czy agent widzi inventory per magazyn / sklep (i na jakich zasadach)

### 3) Bezpieczeństwo dostępu
- authN/authZ (kto i z jakiej roli może pytać)
- rate limits / throttling
- audyt?

### 4) Koszty i ograniczenia LLM

---

# Kolejny przykład: reguły, których nie da się wymusić ręcznie

---

## Przykład: „strażnik” między tabelami

---

Mamy moduł:
- 4 tabele
- jedna z nich pełni rolę **strażnika spójności**
- przy **każdej** zmianie w pozostałych:
  - ta jedna **musi być zablokowana / zaktualizowana razem**

Biznesowo:
- to **jedna operacja**
- technicznie:
  - kilka miejsc
  - kilka ścieżek dostępu

---

## Kiedyś

Architekt/Senior Dev:
- zaprojektował enkapsulację
- ukrył bezpośredni dostęp
- zabezpieczył „normalne” ścieżki

I dodatkowo:
- napisał ADR
- wytłumaczył zespołowi
- przypominał na review
- liczył na zdrowy rozsądek

➡️ **Reguła istniała głównie w głowach**

---

## Dlaczego to nie zawsze działało

Bo w końcu ktoś mówi:
> „To ja tylko na chwilę”  
> „To szybki fix”  
> „Architekt jest na urlopie”

Technicznie:
- da się obejść
- testy mogą nie złapać

➡️ **System pozwalał na złamanie reguły**

---

## Co było frustrujące

- ADR przeczytany raz
- edukacja działa do pierwszej presji
- review nie zawsze złapie kontekst
- regresja wychodzi po czasie

---

## Teraz

Nie próbujemy już:
- wymuszać wszystkiego edukacją
- liczyć na pamięć zespołu
- pilnować każdej zmiany

➡️ **Reguła trafia do systemu jako guardian**

---

## Guardian w SDLC

Guardian / skill:
- zna regułę:
  > „Zmiana w którejkolwiek z tych tabel  
  > wymaga synchronizacji z tabelą-strażnikiem”

Działa:
- przy PR
- przy refaktorze
- przy zmianach generowanych przez AI

➡️ **Sugeruje, nie blokuje**

---

## Ten sam scenariusz — teraz

Ktoś zmienia jedną z tabel:
- testy przechodzą
- kod się kompiluje
- „technicznie OK”

Guardian w review:
> „Ta zmiana dotyka tabeli X.  
> Czy uwzględniono aktualizację tabeli-straż

---

## Code review w świecie AI

AI:
- pisze więcej kodu  
- szybciej  
- czasem bez zrozumienia kontekstu  

➡️ **Code review nie może być już tylko stylem i testami**

---

## Nowy cel code review

Chronić:
- architekturę  
- granice kontekstów  
- pluginowość  
- odpowiedzialności modułów  

Pytania w review:
- czy ten kod łamie granice?
- czy agent nie „wciągnął” za dużo?
- czy to da się wyciąć jako plugin?

---

## AI w SDLC — ktoś musi to wdrożyć

AI nie „wchodzi samo” w SDLC.

Ktoś musi:
- zaprojektować onboarding agenta  
- określić gdzie AI może commitować  
- ustawić role: sugestia vs decyzja  
- określić odpowiedzialność człowieka  

➡️ To jest **design procesu**

---

## Onboarding agenta ≠ prompt

To:
- dostęp do repo  
- zakres odpowiedzialności  
- kontekst domenowy  
- zasady eskalacji  

Architekt / senior:
> „Ten agent:
> - jest w tym miejcu SDLC
> - może refaktoryzować pluginy
> - nie może zmieniać core
> - wymaga review człowieka”

---

## Dlaczego ta rola (architekta, inżyniera produktowego) ewoluuje w FDE

---

## Kto to jest FDE (Forward-Deployed Engineer)

FDE to nie jest:
- „architekt od diagramów”
- „spec od promptów”
- „AI developer”

FDE to osoba, która:
- **rozumie kontekst biznesowy**
- **rozumie architekturę systemu**
- **rozumie ograniczenia AI**

I potrafi:
➡️ przełożyć *cel biznesowy* na *konkretną decyzję architektoniczną*

- FDE:
  - widzi **nowe kanały (np. agenty, MCP)** wcześniej niż biznes
  - potrafi je **bezpiecznie osadzić w architekturze**
  - zna koszty, ryzyka i granice

➡️ **Dzięki AI zarządza kontekstem szybciej i bliżej biznesu niż kiedyś**

---

## Dlaczego to realna przewaga

FDE:
- nie sprzedaje hype’u
- nie obiecuje „AI wszystko zrobi”
- **dowodzi decyzje architektoniczne**

Bo wie:
- co wolno wystawić
- czego nie wolno
- jak wersjonować
- jak zabezpieczyć
- kiedy powiedzieć „nie”

➡️ Taki człowiek:
- skraca time-to-value
- zmniejsza ryzyko
- i realnie buduje przewagę konkurencyjną


