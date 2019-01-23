# Struktura kodu

Pierwszą rzeczą, której się nauczymy to budowanie bloków kodu.

## Wyrażenie

Wyrażenia są konstrukcjami składniowymi i komendami, które wywołują akcję.

Zobaczyliśmy już wyrażenie `alert('Hello, world!')`, które pokazuje wiadomość "Hello world!".

W kodzie możemy mieć tyle wyrażeń ile chcemy. Wyrażenia mogą być oddzielone za pomocą średnika.

Na przykład, tutaj rozdzieliliśmy "Witaj świecie" na dwa alerty"

```js run no-beautify
alert('Witaj'); alert('świecie');
```

Zwykle,  aby sprawić, żeby kod był bardziej czytelny, wyrażenia są w oddzielnych liniach.

```js run no-beautify
alert('Witaj');
alert('świecie');
```

## Średniki [#semicolon]

Średniki mogą być pominięte, kiedy występuje znak nowej linii.

To również zadziała:

```js run no-beautify
alert('Witaj')
alert('świecie')
```

W tym przypadku, JavaScript interpretuje znak nowej linii jako "niejawny" średnik. Jest to nazywane [automatycznym wstawianiem średnika](https://tc39.github.io/ecma262/#sec-automatic-semicolon-insertion).

**Jednak są sytuacje w jakich JavaScript "zawodzi" z dodawaniem średnika, kiedy jest on naprawdę potrzebny.**

Błędy, które występują w takich sytuacjach są całkiem trudne do znalezienia i naprawy.

```smart header="Przykład błędu"
Jeśli jesteś ciekawy zobaczyć konkretny przykład takiego błędu, sprawdź ten kod:

​```js run
[1, 2].forEach(alert)
​```

Nie ma potrzeby w tej chwili myśleć o znaczeniu nawiasów `[]` i `forEach`. Poznamy je później. Teraz po prostu zapamiętaj wynik kodu: pokazuje `1`, a potem `2`.

Teraz, dodajmy `alert` przed obecnym kodem i *nie* zakańczajmy go średnikiem:

​```js run no-beautify
alert("Tu wystąpi błąd")

[1, 2].forEach(alert)
​```

Teraz, jeśli uruchomimy kod, tylko pierwszy alert jest pokazany, a następnie mamy błąd!

Wszystko powraca do porządku, jeśli dodamy średni po 'alert':
​```js run
alert("Teraz wszystko działa");

[1, 2].forEach(alert)
​```

Teraz dostajemy wiadomość "Teraz wszytko działa", a następnie `1` i `2`.

Błąd występuje w przypadkach nie używania średników, ponieważ JavaScript nie dodaje średnika przed nawiasami kwadratowymi `[...]`.

Dlatego, że średnik nie jest wstawiany automatycznie, kod w pierwszym przykładzie jest traktowany jako pojedyncze wyrażenie. Oto jak widzi to silnik:

​```js run no-beautify
alert("Tutaj wystąpi błąd")[1, 2].forEach(alert)
​```

Jednak, powinno być dwoma oddzielnymi wyrażeniami, a nie jednym. Takie połączenie jest w tym przypadku niepoprawne, stąd błąd.
```

Rekomendujemy stawianie średników pomiędzy wyrażeniami, nawet jeśli są one oddzielone znakami nowej linii. Ta zasada jest szeroko przyjętą przez społeczność. Zauważmy jeszcze raz -- jest możliwość opuszczenia średników przez większość czasu. Ale bezpieczniej, szczególnie dla początkującego -- jest ich używać.

## Komentarze

Wraz z upływem czasu, programy stają się coraz bardziej skomplikowane. Koniecznym staje się dodawanie *komentarzy*, które opisują co kod robi i dlaczego.

Komentarze mogą być wstawione w dowolne miejsce skryptu. Nie wpływają one na jego działanie, ponieważ silnik po prostu je ignoruje.

**Jednoliniowe komentarze zaczynają się dwoma ukośnikami `//`.**

Reszta linii jest komentarzem. Może on obejmować pełną linię lub być poprzedzony wyrażeniem.

Tak jak tutaj:

```js run
// Ten komentarz zajmuje całą linię
alert('Hello');

alert('Hello'); // Ten komentarz jest poprzedzony wyrażeniem
```

**Wieloliniowe komentarze rozpoczynają się ukośnikiem i gwiazdką <code>/&#42;</code>, a zakańczane gwiazdką i ukośnikiem <code>&#42;/</code>.**

Tak jak tutaj:

```js run
/* Przykład z wykorzystaniem dwóch wiadomości.
To jest wieloliniowy komentarz.
*/
alert('Witaj');
alert('świecie');
```

Zawartość komentarza jest ignorowana, więc jeśli umieścimy kod w środku `/* ... */` , to się nie uruchomi.

Czasami wygodnie jest tymczasowo wyłączyć część kodu:

```js run
/* Komentowanie kodu
alert('Hello');
*/
alert('World');
```

```warn header="Nested comments are not supported!"
Nie może być `/* ... */` w środku innego `/* ... */`.

Taki kod przerwie działanie z powodu błędu:

​```js run no-beautify
/*
  /* zagnieżdżony komentarz?!? */
*/
alert( 'świecie' );
​```
```

Proszę, nie wahaj się komentować swojego kodu.

Komentarze podnoszą ogólną ilość kodu, ale to nie jest żaden problem. Jest wiele narzędzi, które minifikują kod przed wysłaniem na serwer produkcyjny. Usuwają one komentarze, więc nie pojawiają się w działających skryptach. W związku z tym, komentarze nie mają ani trochę negatywnego wpływu na produkcję.



Później w kursie będzie rozdział <info:coding-style>, który również wyjaśnia jak pisać lepsze komentarze.