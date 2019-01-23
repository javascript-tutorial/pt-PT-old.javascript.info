# Konsola deweloperska

Kod jest podatny na błędy. Bardzo prawdopodobnie będziesz je robić... Oh, o czym ja mówię? Będziesz *absolutnie na pewno* robić błędy, przynajmniej jeśli jesteś człowiekiem, a nie [robotem](https://en.wikipedia.org/wiki/Bender_(Futurama)).

W przeglądarce, użytkownicy domyślnie nie widzą błędów. Więc, jeśli coś pójdzie źle w skrypcie, nie zobaczymy co jest zepsute i nie możemy tego naprawić.

Aby umożliwić przeglądanie errorów i zdobywanie wielu przydatnych informacji o skryptach, w przeglądarki wbudowano "narzędzia programistyczne" (ang. dev tools).

Większość programistów składnia się, aby użyć Chrome'a lub Firefox'a do programowania, ponieważ te przeglądarki mają najlepsze narzędzia dla programistów. Inne przeglądarki również dostarczają narzędzia programistyczne, czasami ze specjalnymi funkcjami, ale zwykle ciągle gonią Chrome i Firefox'a. Dlatego, wielu programistów ma "ulubioną" przeglądarkę i zmienia ją jeśli problem jest specyficzny dla określonej przeglądarki.

Narzędzia dla programistów są potężne; mają wiele funkcji. Zacznijmy, ucząc się jak je otworzyć, patrzeć na błędy i uruchamiać komendy JavaScriptu.

## Google Chrome

Otwórz stronę [bug.html](bug.html).

Jest tam error w kodzie JavaScriptu. Jest ukryty przed zwykłymi odwiedzającymi, więc otwórzmy narzędzia programistyczne aby go zobaczyć.

Naciśnij `key:F12` lub, jeśli używasz Mac'a - `key:Cmd+Opt+J`.

Narzędzia programistyczne otworzą się domyślnie w zakładce Console.

Wyglądają mniej więcej tak:

![chrome](chrome.png)

Dokładny wygląd narzędzi zależy od twojej wersji Chrome. Zmienia się od czasu do czasu, ale powinien być podobny.

- Możemy tutaj zobaczyć wiadomość o błędzie koloru czerwonego. W tym przypadku skrypt zawiera nieznaną komendę "lalala".
- Po prawej jest klikalny link do źródła `bug.html:12` z linią, gdzie wystąpił błąd.

Poniżej wiadomości błędu znajduje się niebieski symbol `>`. Oznacza "linię komend", gdzie możemy wpisywać komendy JavaScriptu. Wciśnij `key:Enter`, żeby je uruchomić (użyj`key:Shift+Enter` aby wpisać wieloliniowe komendy).

Teraz możemy zobaczyć błędy i to wystarczy na start. Wrócimy do narzędzi programistycznych później i nauczymy się bardziej zaawansowanego debugowania w rozdziale <info:debugging-chrome>.

## Firefox, Edge i inne

Większość innych przeglądarek używa `key:F12` jako skrótu do otwierania narzędzi programistycznych.

Wygląd i ich odczucia są całkiem podobne. Kiedy raz nauczysz się jak używać jednego z tych narzędzi (możesz zacząć z Chromem), możesz łatwo przesiąść się na inne.

## Safari

Safari (przeglądarka na MacOS, nie wspierana przez Windowsa/Linuxa) jest trochę specjalna w tym wypadku. Najpierw musimy włączyć "menu programistyczne".

Otwórz Preferencje i przejdź do panelu "Zaawansowane". Jest tam opcja do zaznaczenia na dole:

![safari](safari.png)

Od teraz `key:Cmd+Opt+C` może włączyć konsolę. Również, zauważ, że pojawiło się nowe menu nazwane "Develop". Ma ono wiele komend i opcji.

## Podsumowanie

- Narzędzia programistyczne pozwalają nam zobaczyć błędy, wykonywać komendy, analizować zmienne i wiele więcej.
- Mogą one być otwarte wciskając `key:F12` dla większości przeglądarek na Windowsie. W Chromie na Macu trzeba użyć kombinacji `key:Cmd+Opt+J`, a w Safari `key:Cmd+Opt+C` (muszą być uprzednio włączone).

Teraz mamy gotowe środowisko. W następnej sekcji przejdziemy do JavaScriptu.

