---

# 5. Jak to wpływa na rolę developera i architekta

---

## Przykład: granice językowe modułów

---

## Kiedyś

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

## Teraz

AI:
- bardzo szybko zaczyna grzebać w kodzie
- bardzo szybko generuje rozwiązania
- **nie rozpoznaje klasy złożoności problemu**

➡️ AI idealnie:
- implementuje złe uproszczenia
- przyspiesza złe decyzje

Jeśli nie ma guardrails:
➡️ system jedzie w ścianę szybciej niż kiedyś

---

## Co się realnie zmienia

### Teraz architekt:

- nadal ma te pytania
- nadal odpowiada za decyzję
- **ale może je sprotokolizować**

Czyli:
➡️ zamienić intuicję w **jawny zestaw pytań**

---

## Ten sam przykład — teraz

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

TODO: skirin skilla

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

## Pluginowość = realna przewaga

AI dramatycznie:
- zwiększa liczbę zmian  
- zwiększa liczbę autorów kodu  
- zwiększa chaos kontekstowy  

➡️ **Pluginowa architektura staje się krytyczna**

---

## Dlaczego pluginowość jest ważniejsza niż wcześniej?

Bo:
- agent nie ogarnia monolitu  
- LLM działa lepiej w małym kontekście  
- mniejszy kontekst = lepsze decyzje  

➡️ Plugin:
- ma jasne API  
- ma ograniczony scope  
- da się testować osobno  

---

## Rola architekta: bronić pluginowości

Nie tylko w kodzie.

Ale w:
- review  
- standardach  
- decyzjach „na szybko”  

Architekt musi umieć powiedzieć:
> „Nie, nie wrzucamy tego do core — to powinien być plugin”

Bo:
- AI przyspiesza złe decyzje tak samo jak dobre

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

➡️ To jest **design procesu**, nie toola.

---

## Onboarding agenta ≠ prompt

To:
- dostęp do repo  
- zakres odpowiedzialności  
- kontekst domenowy  
- zasady eskalacji  

Architekt / senior decyduje:
> „Ten agent:
> - może refaktoryzować pluginy
> - nie może zmieniać core
> - wymaga review człowieka”

---

## FDE: 

tODO
---

## Co się realnie zmienia w roli developera?

Mniej:
- pisania boilerplate  
- ręcznego klepania  

Więcej:
- decyzji architektonicznych  
- pracy na granicach systemu  
- rozumienia całości  

---

## Co się realnie zmienia w roli architekta?

Architekt:
- nie tylko „rysuje diagramy”  
- ale **aktywnie ustawia system pod AI**

Decyduje:
- gdzie AI ma wejść  
- gdzie nie  
- jak chronić system przed chaosem  

---

## Podsumowanie

AI nie zabiera roli developera ani architekta.

AI:
- **podnosi poprzeczkę**

Wygrywają ci, którzy:
- rozumieją architekturę  
- rozumieją SDLC  
- rozumieją ograniczenia AI  
- potrafią zaproponować konkretne rozwiązania

➡️ **To jest miejsce, gdzie buduje się przewagę konkurencyjną**


---

## AI wchodzi w obszary, których wcześniej nie dotykało

Klasycznie:
- kod pisał człowiek  
- decyzje były explicite  
- odpowiedzialność była jasna  

AI:
- generuje zmiany masowo  
- eksploruje system  
- łączy dane, których nikt ręcznie nie łączył  

➡️ **To zmienia model ryzyka**

---

## Problem #6: agent widzi za dużo

Agent:
- ma dostęp do repo  
- ma dostęp do dokumentacji  
- ma dostęp do danych  

Często:
- więcej niż pojedynczy developer  
- więcej niż miałby człowiek na start  

➡️ **Zaczynamy łamać zasadę least privilege**

---

## To nie jest tylko security — to governance

Bo pytania są inne:
- kto zdecydował, że agent ma ten dostęp?
- czy agent może łączyć te dane?
- czy agent „rozumie”, czego nie wolno mu wypuścić?

➡️ **Brakuje decyzji, nie narzędzi**

---

## Klasyczne security nie wystarcza

IAM, role, ACL:
- działają na poziomie systemów  
- nie działają na poziomie *intencji*  

AI:
- nie wykrada danych  
- ale może je **zsyntetyzować**  

➡️ To nowy wektor ryzyka

---

## Problem #7: agent robi „dobrą” rzecz w zły sposób

Przykład:
- agent poprawia bug  
- potrzebuje danych produkcyjnych  
- wyciąga je do promptu  

Technicznie:
- wszystko działa  

Security:
- wyciek kontekstowy  

➡️ **Nikt tego nie zaplanował**

---

## Rozwiązanie: governance na poziomie agentów

Nie:
- „AI policy w Confluence”  

Tylko:
- **architektura agentów**

Decyzje:
- jakie agenty istnieją  
- jaki mają scope  
- z jakich źródeł mogą korzystać  

---

## Agent ≠ człowiek

Człowiek:
- ma intuicję  
- ma strach  
- ma kontekst organizacyjny  

Agent:
- wykona zadanie  
- jeśli nie ma zakazu — pójdzie dalej  

➡️ Governance musi być **jawne i techniczne**

---

## Problem #8: brak audytu decyzji AI

Po incydencie:
- nie wiemy, który agent  
- nie wiemy, na jakich danych  
- nie wiemy, dlaczego  

Logi:
- nie wystarczą  

➡️ **Brakuje audytu decyzyjnego**

---

## Rozwiązanie: decyzje AI jako artefakty

Każda istotna akcja agenta:
- jest zapisana  
- ma kontekst  
- ma uzasadnienie  

Np.:
- „dlaczego zmieniłem ten kod”
- „jakie źródła wykorzystałem”
- „jakie reguły governance obowiązywały”

➡️ To jest **nowy rodzaj audytu**

---

## Rola architekta w security & governance

Architekt:
- projektuje granice agentów  
- definiuje „strefy zakazane”  
- decyduje, gdzie AI nie wchodzi  

Nie deleguje tego:
- na security  
- na compliance  

Bo:
➡️ **to jest część architektury systemu**

---

## Rola developera

Developer:
- wie, gdzie AI pomaga  
- wie, gdzie AI jest ryzykiem  

Jego zadanie:
- zgłosić niebezpieczne miejsca  
- opisać nieformalne zasady  
- przekazać wiedzę agentom  

➡️ Governance wyrasta z praktyki, nie z dokumentów

---

## Problem #9: Shadow AI wraca tylnymi drzwiami

Jeśli:
- oficjalne AI jest zbyt ograniczone  
- governance jest oderwane od realiów  

Zespół:
- użyje własnych narzędzi  
- obejdzie proces  
- wróci chaos  

➡️ Governance, które blokuje — przegrywa

---

## Dobre governance działa „w tle”

Nie przeszkadza:
- w codziennej pracy  
- w review  
- w eksploracji  

Ale:
- reaguje, gdy zbliżasz się do granicy  
- zatrzymuje, gdy trzeba  

➡️ Jak dobre guardrails, nie mur

---

## Podsumowanie: security i governance w świecie AI

To nie jest:
- checkbox  
- polityka  
- PDF  

To jest:
- **świadome projektowanie ról agentów**
- **jawne granice dostępu**
- **audyt decyzji, nie tylko akcji**
- **architekt w pętli decyzyjnej**

---

## Ostateczna przewaga

Organizacje, które:
- włączą AI bez governance → przyspieszą chaos  
- włączą governance bez zrozumienia AI → zablokują zespoły  

Wygrywają te, które:
➡️ **zaprojektują AI jak część systemu**

To jest trudne.  
Dlatego jest przewagą.


---

## Spec-driven zamiast „AI pisze kod”

AI:
- potrafi zmieniać kod
- nie rozumie transakcji
- nie rozumie konsekwencji biznesowych

➡️ Dlatego potrzebujemy **spec-driven podejścia**

---

## Co to znaczy „spec-driven”?

Spec:
- nie opisuje jak coś działa
- opisuje **kiedy zmiana jest poprawna, a kiedy nie**

To nie jest dokumentacja.
To są **reguły systemu**.


---

## Problem z AI

AI widzi:
- pliki
- funkcje
- testy

Nie widzi:
- że te zmiany muszą wydarzyć się razem
- że stan pośredni jest nieakceptowalny
- że rollback jest drogi

➡️ AI idealnie łamie agregaty

---

## Przykład (intuicyjny)

Zmiana:
- statusu zamówienia
- płatności
- rezerwacji stocku

Technicznie:
- trzy różne miejsca

Biznesowo:
- **jedna transakcja**

➡️ To jest agregat

---

## Spec agregatu (minimalna)

Nie piszemy elaboratów.

Spec mówi:
- co MUSI zmienić się razem
- czego NIE WOLNO zmienić osobno
- jaki stan jest biznesowo niepoprawny

To wystarczy.

---


## Po co ta spec?

Bo:
- testy tego nie wyrażą
- typy tego nie złapią
- AI tego nie zgadnie

Spec:
➡️ przenosi wiedzę architektoniczną do systemu

---

## Spec → agent

Agent w code review:
- nie sprawdza „czy działa”
- sprawdza „czy nie rozcięto agregatu”

> „Ta zmiana dotyka tylko części transakcji”

➡️ Guardrail, nie automat

---

## Co tu robi architekt?

Architekt:
- identyfikuje agregaty
- zapisuje ich reguły
- decyduje gdzie AI może działać
- gdzie musi się zatrzymać

To nie jest governance.
To jest **architektura systemu**.

---


➡️ Biznes rozumie koszt i ryzyko.

---

## Podsumowanie

Spec-driven:
- nie spowalnia
- skraca feedback loop
- pozwala używać AI bez chaosu


Kto to rozumie:
➡️ realnie buduje przewagę konkurencyjną
