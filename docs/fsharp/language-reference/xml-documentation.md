---
title: Dokumentacja XML
description: 'Dowiedz się więcej o pomocy technicznej w języku F # w celu wygenerowania dokumentacji z komentarzy.'
ms.date: 09/15/2020
ms.openlocfilehash: a5bec20f27c23caee951cda2dc5d17808f69d384
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679406"
---
# <a name="document-your-code-with-xml-comments"></a>Dokumentowanie kodu za pomocą komentarzy XML

Można utworzyć dokumentację z komentarzy do kodu potrójnym ukośnikiem (//) w języku F #. Komentarze XML mogą poprzedzać deklaracje w plikach kodu (. FS) lub sygnatur (. FSI).

Komentarze dokumentacji XML są specjalnym rodzajem komentarza, który został dodany powyżej definicji dowolnego typu lub elementu członkowskiego zdefiniowanego przez użytkownika.
Są one specyficzne, ponieważ mogą być przetwarzane przez kompilator w celu wygenerowania pliku dokumentacji XML w czasie kompilacji.
Plik XML wygenerowany przez kompilator może być dystrybuowany wraz z zestawem .NET, dzięki czemu środowisk IDE mogą używać etykietek narzędzi do wyświetlania szybkich informacji o typach lub elementach członkowskich. Ponadto plik XML można uruchomić za pomocą narzędzi, takich jak [fsdocs](http://fsprojects.github.io/FSharp.Formatting/) , aby wygenerować witryny sieci Web dokumentacji interfejsu API.

Komentarze dokumentacji XML, podobnie jak wszystkie inne komentarze, są ignorowane przez kompilator, chyba że opcje opisane poniżej są włączone, aby sprawdzać poprawność i kompletność komentarzy w czasie kompilacji.

Plik XML można wygenerować w czasie kompilacji, wykonując jedną z następujących czynności:

- Można dodać `GenerateDocumentationFile` element do `<PropertyGroup>` sekcji `.fsproj` pliku projektu, który generuje plik XML w katalogu projektu o tej samej nazwie pliku głównego co zestaw. Na przykład:

   ```xml
   <GenerateDocumentationFile>true</GenerateDocumentationFile>
   ```

- Jeśli tworzysz aplikację przy użyciu programu Visual Studio, kliknij prawym przyciskiem myszy projekt i wybierz polecenie **Właściwości**. W oknie dialogowym właściwości wybierz kartę **kompilacja** i sprawdź **plik dokumentacji XML**. Możesz również zmienić lokalizację, w której kompilator zapisuje plik.

Istnieją dwa sposoby zapisywania komentarzy do dokumentacji XML: z tagami XML i bez nich. Oba używają komentarzy z potrójnym ukośnikiem.

## <a name="comments-without-xml-tags"></a>Komentarze bez tagów XML

Jeśli `///` komentarz nie zaczyna się od `<` Then, cały tekst komentarza jest traktowany jako dokumentacja podsumowania dla konstrukcji kodu, która jest bezpośrednio następująca. Użyj tej metody, jeśli chcesz napisać tylko krótkie podsumowanie dla każdej konstrukcji.

Komentarz jest zakodowany w formacie XML podczas przygotowywania dokumentacji, dlatego znaki takie jak `<` `>` i `&` nie muszą być zmienione. Jeśli nie określisz jawnie tagu podsumowującego, nie należy określać innych tagów, takich jak **param** lub **zwracających** Tagi.

Poniższy przykład pokazuje alternatywną metodę bez tagów XML. W tym przykładzie cały tekst w komentarzu jest traktowany jako podsumowanie.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7102.fs)]

## <a name="comments-with-xml-tags"></a>Komentarze ze znacznikami XML

Jeśli treść komentarza zaczyna się od `<` (normalnie `<summary>` ), jest traktowana jako treść komentarza w formacie XML przy użyciu tagów XML. Ta sekunda pozwala określić oddzielne notatki dla krótkiego podsumowania, dodatkowe uwagi, dokumentację dla każdego parametru i parametru typu oraz zgłoszone wyjątki oraz opis wartości zwracanej.

Poniżej znajduje się typowy komentarz dokumentacji XML w pliku sygnatury:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7101.fs)]

## <a name="recommended-tags"></a>Zalecane Tagi

Jeśli używasz tagów XML, w poniższej tabeli opisano Tagi zewnętrzne rozpoznawane w komentarzach do kodu XML w języku F #.

| Składnia tagów                                  | Opis |
|---------------------------------------------|-----------|
| `<summary>`**_Opis_**`</summary>`           | Określa, że *tekst* jest krótkim opisem elementu programu. Opis jest zwykle jednym lub dwoma zdaniami.|
| `<remarks>`**_Opis_**`</remarks>`           | Określa, że *tekst* zawiera dodatkowe informacje o elemencie program.|
| `<param name="`**_Nazwa_** `">` ** _Opis_**`</param>` | Określa nazwę i opis parametru funkcji lub metody.|
| `<typeparam name="`**_Nazwa_** `">` ** _Opis_**`</typeparam>` | Określa nazwę i opis parametru typu.|
| `<returns>`**_Opis_**`</returns>`           | Określa, że *tekst* opisuje wartość zwracaną przez funkcję lub metodę.|
| `<exception cref="`**_Typ_** `">` ** _Opis_**`</exception>` |Określa typ wyjątku, który może być wygenerowany i okoliczności, w których jest generowany.|
| `<seealso cref="`**_odwoła_**`"/>`      | Określa również link do dokumentacji dla innego typu. *Odwołanie* jest nazwą wyświetlaną w pliku dokumentacji XML. Zobacz także linki zwykle wyświetlane w dolnej części strony dokumentacji.|

W poniższej tabeli opisano Tagi do użycia wewnątrz sekcji opisu:

| Składnia tagów                                | Opis |
|-------------------------------------------|-------------|
| `<para>`**_Opis_**`</para>`               | Określa akapit tekstu. Służy do rozdzielania tekstu wewnątrz znacznika **uwagi** .|
| `<code>`**_Opis_**`</code>`               | Określa, że *tekst* jest wieloma wierszami kodu. Ten tag może być używany przez generatory dokumentacji do wyświetlania tekstu w czcionce, która jest odpowiednia dla kodu.|
| `<paramref name="`**_Nazwij_**`"/>`         | Określa odwołanie do parametru w tym samym komentarzu do dokumentacji.|
| `<typeparamref name="`**_Nazwij_**`"/>`     | Określa odwołanie do parametru typu w tym samym komentarzu do dokumentacji.|
| `<c>`**_Opis_**`</c>`                     | Określa, że *tekst* jest kodem wbudowanym. Ten tag może być używany przez generatory dokumentacji do wyświetlania tekstu w czcionce, która jest odpowiednia dla kodu.|
| `<see cref="`**_Dokumentacja_** `">` ** _tekst_**`</see>` | Określa link wbudowany do innego elementu programu. *Odwołanie* jest nazwą wyświetlaną w pliku dokumentacji XML. *Tekst* jest tekstem wyświetlanym w łączu.|

### <a name="user-defined-tags"></a>Tagi zdefiniowane przez użytkownika

Poprzednie Tagi reprezentują te, które są rozpoznawane przez kompilator F # i typowe narzędzia edytora F #. Jednak użytkownik może definiować własne znaczniki.
Narzędzia takie jak fsdocs zapewniają obsługę dodatkowych tagów, takich jak [\<namespacedoc>](https://github.com/fsharp/fslang-design/blob/master/tooling/FST-1031-xmldoc-extensions.md) .
Niestandardowe i wewnętrzne narzędzia do generowania dokumentacji mogą również być używane ze znacznikami standardowymi i można obsługiwać wiele formatów wyjściowych z formatu HTML do pliku PDF.

## <a name="compile-time-checking"></a>Sprawdzanie czasu kompilacji

Gdy `--warnon:3390` jest włączona, kompilator weryfikuje składnię XML i parametry, do których odwołują się w `<param>` i `<paramref>` Tagi.

## <a name="documenting-f-constructs"></a>Dokumentowanie konstrukcji języka F #

Konstrukcje języka F #, takie jak moduły, elementy członkowskie, przypadki Unii i pola rekordów, są udokumentowane `///` bezpośrednio przed ich deklaracją.
W razie potrzeby niejawne konstruktory klas są udokumentowane przez złożenie `///` komentarza przed listą argumentów. Na przykład:

```fsharp
/// This is the type
type SomeType
      /// This is the implicit constructor
      (a: int, b: int) =

    /// This is the member
    member _.Sum() = a + b
```

## <a name="limitations"></a>Ograniczenia

Niektóre funkcje dokumentacji XML w języku C# i innych językach .NET nie są obsługiwane w języku C#.

- W języku F # odwołania krzyżowe muszą używać pełnej sygnatury XML odpowiadającego symbolu, na przykład `cref="T:System.Console"` .
  Proste odsyłacze w stylu C#, takie jak `cref="Console"` nie są rozbudowane do pełnych podpisów XML i te elementy nie są sprawdzane przez kompilator F #. Niektóre narzędzia dokumentacji mogą zezwalać na użycie tych odsyłaczy przez kolejne przetwarzanie, ale należy używać pełnych podpisów.
  
- Tagi `<include>` `<inheritdoc>` nie są obsługiwane przez kompilator F #. Nie podano żadnego błędu, jeśli są one używane, ale są po prostu kopiowane do wygenerowanego pliku dokumentacji bez wpływu na wytworzoną dokumentację.

- Odwołania krzyżowe nie są sprawdzane przez kompilator F #, nawet gdy `-warnon:3390` jest używany.

- Nazwy używane w tagach `<typeparam>` i `<typeparamref>` nie są sprawdzane przez kompilator F #, nawet gdy `--warnon:3390` jest używany.

- Jeśli brakuje dokumentacji, nie są wyświetlane żadne ostrzeżenia `--warnon:3390` .

## <a name="recommendations"></a>Zalecenia

Dokumentowanie kodu jest zalecane z wielu powodów. Poniżej przedstawiono niektóre najlepsze rozwiązania, ogólne scenariusze przypadków użycia i informacje, które należy znać w przypadku używania tagów dokumentacji XML w kodzie języka F #.

- Włącz opcję `--warnon:3390` w kodzie, aby upewnić się, że dokumentacja XML jest prawidłowym kodem XML.

- Rozważ dodanie plików sygnatury w celu oddzielenia komentarzy do dokumentacji XML od implementacji.

- Ze względu na spójność wszystkich publicznie widocznych typów i ich członków należy udokumentować. Jeśli to konieczne, zrób wszystko.

- W przypadku systemu operacyjnego minimum moduły, typy i ich elementy członkowskie powinny mieć zwykły `///` komentarz lub `<summary>` tag. Spowoduje to wyświetlenie okna etykietki narzędzia autouzupełniania w narzędziach do edycji w języku F #.

- Tekst dokumentacji należy napisać przy użyciu kompletnych zdań kończących się pełnym zatrzymywaniem.

## <a name="see-also"></a>Zobacz też

- [Komentarze dokumentacji XML języka C# &#40;C&#35; Przewodnik programowania&#41;](../../csharp/programming-guide/xmldoc/index.md).
- [Dokumentacja języka F #](index.md)
- [Opcje kompilatora](compiler-options.md)
