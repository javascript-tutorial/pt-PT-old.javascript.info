# Witaj świecie!

Kurs, który czytasz jest o jądrze JavaScriptu, które jest niezależne od platformy. Później, nauczysz się o Node.JS i innych platformach używających go.

Potrzebujemy działającego środowiska do uruchamiania naszych skryptów i od kiedy ta książka jest online, przeglądarka jest dobrym wyborem. Zminimalizujemy ilość komend typowych dla przeglądarek, żebyś nie spędzał czasu na ich naukę jeśli planujesz skoncentrować się na innym środowisku (takim jak Node.JS). Skupimy się na JavaScripcie w przeglądarce w [następnej części](/ui) tego kursu.

Najpierw zobaczmy jak dołączyć skrypt do strony internetowej. Dla środowisk serwerowych (takich jak Node.JS), możesz uruchamiać skrypt komendą np. `"node my.js"`.

## Znacznik "script"

Programy w JavaScripcie mogą być dodane w jakiejkolwiek części dokumentu HTML za pomocą tagu `<script>`.

Dla przykładu:

```html run height=100
<!DOCTYPE HTML>
<html>

<body>

  <p>Przed skryptem...</p>

*!*
  <script>
    alert( 'Witaj świecie!' );
  </script>
*/!*

  <p>...Po skrypcie.</p>

</body>

</html>
```

```
Możesz uruchomić przykład klikając przycisk "Play" w prawym górnym rogu powyższej sekcji.
```

Znacznik `<script>` zawiera kod JavaScript, który jest automatycznie uruchamiany,  kiedy przeglądarka przetwarza znacznik.

## Nowoczesne tagowanie

Znacznik `<script>` ma kilka atrybutów, które są rzadko używane w dzisiejszych dniach, ale ciągle mogą być znalezione w starym kodzie:

Atrybut `type`: <code>&lt;script <u>type</u>=...&gt;</code>: 
Stary standard HTML, HTML4 wymagał, aby znacznik script miał atrybut `type`. Zwykle było to `type="text/javascript"`. Nie jest to dłużej wymagane. Również, nowoczesny standard, HTML5, kompletnie zmienił znaczenie tego atrybutu. Teraz, może być używany dla modułów JavaScriptu. Jest to zaawansowany temat; powiemy o modułach w innej części kursu.

Atrybut `language`: <code>&lt;script <u>language</u>=...&gt;</code>:

Ten atrybut został stworzony do określenia języka skryptu. Aktualnie nie ma on sensu, ponieważ JavaScript jest domyślnym językiem. Nie ma potrzeby jego używania.

Komentarze przed i po skryptach:

W naprawdę starodawnych książkach i poradnikach możesz znaleźć komentarze wewnątrz tagów `<script>`, na przykład:

```html no-beautify
<script type="text/javascript"><!--
    ...
//--></script>
```

Ten trik nie jest używany w nowoczesnym JavaScripcie. Te komentarze chowały kod JavaScript przed starymi przeglądarkami, które nie wiedziały jak przetworzyć znacznik `<script>`. Przeglądarki wydane w ostatnich 15 latach nie mają tego błędu, więc za pomocą tego typu komentarza możesz rozpoznać naprawdę stary kod.

## Zewnętrzne skrypty

Jeśli mamy dużo kodu JavaScript, możemy umieścić go w oddzielnym pliku.

Pliki ze skryptami są dołączone do HTML za pomocą atrybutu `src`:

```html
<script src="/sciezka/do/skryptu.js"></script>
```

W tym przypadku, `/sciezka/do/skryptu.js` jest absolutną ścieżką do skryptu (ścieżką z folderu głównego strony do pliku).

Możesz też podać względną ścieżkę z aktualnego pliku. Dla przykładu, `src="script.js"` będzie znaczyło, że plik  `"script.js"` jest w aktualnym folderze.

Możemy podać pełny adres URL. Na przykład:

```html
<script
src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/3.2.0/lodash.js"></script>
```

Aby załączyć kilka skryptów użyj wielu znaczników:

```html
<script src="/js/script1.js"></script>
<script src="/js/script2.js"></script>
…
```

```smart
Z zasady, tylko najprostsze skrypty są umieszczane w HTML. Bardziej skomplikowane znajdują się w oddzielnych plikach.

Korzyść z używania oddzielnego pliku jest taka, że przeglądarka pobierze go i przechowa go w pamięci [cache](https://en.wikipedia.org/wiki/Web_cache).

Inne strony, które odwołują się do tego samego skryptu, wezmą go z tej pamięci zamiast go pobierać, więc plik jest pobrany tylko raz.

To ogranicza ruch sieciowy i sprawia, że strony są szybsze.
```

````warn header="Jeśli atrybut ` `src` jest ustawiony, zawartość znacznika script jest ignorowana"



To nie zadziała:

```html
<script *!*src*/!*="file.js">
  alert(1); // zawartość jest ignorowana z powodu ustawionego atrybutu src
</script>
```

Musimy wybrać, czy chcemy użyć zewnętrznego skryptu czy zwykłego znacznika `<script>` z kodem.

Przykład powyżej musi być rozdzielony na dwa skrypty, aby zadziałał.

```html
<script src="file.js"></script>
<script>
  alert(1);
</script>
```

```

## Podsumowanie

- Możemy użyć tagu `<script>`, aby dodać kod JavaScript do strony.
- Atrybuty `type` i `language` nie są potrzebne.
- Skrypt w zewnętrznym pliku może być dodany za pomocą `<script src="ścieżka/do/skryptu.js"></script>`.

Jest wiele więcej do nauczenia się w temacie skryptów przeglądarki i ich interakcji ze stroną internetową. Pamiętajmy o tym, że ta część kursu jest poświęcona językowi JavaScript, dlatego nie powinniśmy się rozpraszać jego typowo przeglądarkowymi implementacjami. Będziemy używać przeglądarki jako sposobu na uruchomienie kodu JavaScript, który jest bardzo wygodny do czytania online, ale tylko jeden z wielu sposobów.
```

