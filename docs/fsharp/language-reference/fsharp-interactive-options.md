---
title: Opcje interaktywne
description: Dowiedz się więcej na temat opcji wiersza polecenia obsługiwanych przez F# Interactive, fsi.exe.
ms.date: 08/15/2020
ms.openlocfilehash: da2251c1d2e57090ed926e501cebf3c53ac58052
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558611"
---
# <a name="f-interactive-options"></a>Opcje F# Interactive

W tym artykule opisano opcje wiersza polecenia obsługiwane przez F# Interactive, `fsi.exe` . F# Interactive akceptuje wiele z tych samych opcji wiersza polecenia co kompilator języka F #, ale również akceptuje pewne dodatkowe opcje.

## <a name="use-f-interactive-for-scripting"></a>Używanie F# Interactive do obsługi skryptów

F# Interactive, `dotnet fsi` , może być uruchamiany interaktywnie lub można uruchomić z wiersza polecenia, aby uruchomić skrypt. Składnia wiersza polecenia jest

```dotnetcli
dotnet fsi [options] [ script-file [arguments] ]
```

Rozszerzenie pliku dla plików skryptów języka F # to `.fsx` .

## <a name="table-of-f-interactive-options"></a>Tabela opcji F# Interactive

Poniższa tabela zawiera podsumowanie opcji obsługiwanych przez F# Interactive. Można ustawić te opcje w wierszu polecenia lub w środowisku IDE programu Visual Studio. Aby ustawić te opcje w środowisku IDE programu Visual Studio, otwórz menu **Narzędzia** , wybierz polecenie **Opcje**, rozwiń węzeł **Narzędzia F #** , a następnie wybierz **F# Interactive**.

Gdy listy pojawiają się w F# Interactive argumenty opcji, elementy listy są oddzielone średnikami ( `;` ).

|Opcja|Opis|
|------|-----------|
|**--**|Służy do Poinstruuj F# Interactive, aby traktować pozostałe argumenty jako argumenty wiersza polecenia do programu lub skryptu języka F #, do którego można uzyskać dostęp w kodzie przy użyciu listy **FSI. CommandLineArgs —**.|
|**--zaewidencjonowano**[ **+**&#124;**-** ]|Taka sama jak opcja kompilatora **fsc.exe** . Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).|
|**--CodePage: &lt; int&gt;**|Taka sama jak opcja kompilatora **fsc.exe** . Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).|
|**--consolecolors**[ **+**&#124;**-** ]|Wyświetla ostrzeżenia i komunikaty o błędach w kolorze.|
|**--crossoptimize**[ **+**&#124;**-** ]|Włączać lub wyłączać optymalizacje między modułami.|
|**--Debug**[ **+**&#124;**-** ]<br /><br />**--Debug:**[**full**&#124;**pdbonly**&#124;**Portable**&#124;**Embedded**]<br /><br />**-g**[ **+**&#124;**-** ]<br /><br />**-g:**[**pełna**&#124;**pdbonly**&#124;**przenośny**&#124;**Embedded**]|Taka sama jak opcja kompilatora **fsc.exe** . Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).|
|**--define: &lt; ciąg&gt;**|Taka sama jak opcja kompilatora **fsc.exe** . Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).|
|**--deterministyczny**[ **+**&#124;**-** ]|Tworzy deterministyczny zestaw (w tym identyfikator GUID i sygnaturę czasową wersji modułu).|
|**--exec**|Nakazuje programowi F # Interactive Kończenie po załadowaniu plików lub uruchomieniu pliku skryptu podanym w wierszu polecenia.|
|**--fullpaths —**|Taka sama jak opcja kompilatora **fsc.exe** . Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).|
|**--GUI**[ **+**&#124;**-** ]|Włącza lub wyłącza pętlę zdarzeń Windows Forms. Wartość domyślna jest włączona.|
|**--Pomoc**<br /><br />**-?**|Służy do wyświetlania składni wiersza polecenia i krótkiego opisu każdej opcji.|
|**--lib: &lt; Lista folderów&gt;**<br /><br />**-I: &lt; Lista folderów&gt;**|Taka sama jak opcja kompilatora **fsc.exe** . Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).|
|**--Load: &lt; filename&gt;**|Kompiluje dany kod źródłowy przy uruchamianiu i ładuje skompilowane konstrukcje F # do sesji.|
|**--mlcompatibility**|Taka sama jak opcja kompilatora **fsc.exe** . Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).|
|**--noframework**|Taka sama jak opcja kompilatora **fsc.exe** . Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md)|
|**--nologo**|Taka sama jak opcja kompilatora **fsc.exe** . Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).|
|**--nowarn: &lt; Ostrzeżenie-lista&gt;**|Taka sama jak opcja kompilatora **fsc.exe** . Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).|
|**--Optymalizuj**[ **+**&#124;**-** ]|Taka sama jak opcja kompilatora **fsc.exe** . Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).|
|**--preferreduilang: &lt; lang&gt;**| Określa nazwę preferowanej kultury języka wyjściowego (na przykład es-ES, ja-JP). |
|**--quiet**|Pomiń dane wyjściowe F# Interactive strumienia **stdout** .|
|**--Cytaty-debugowanie**|Określa, że powinny być emitowane dodatkowe informacje o debugowaniu dla wyrażeń, które pochodzą z literałów cytatu w języku F # i odbitej definicji. Informacje debugowania są dodawane do atrybutów niestandardowych węzła drzewa wyrażenia języka F #. Zobacz [cytaty kodu](code-quotations.md) i [expr. CustomAttributes —](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).|
|**--ReadLine**[ **+**&#124;**-** ]|Włącza lub wyłącza uzupełnianie kart w trybie interaktywnym.|
|**--Reference: &lt; filename&gt;**<br /><br />**-r: &lt; filename&gt;**|Taka sama jak opcja kompilatora **fsc.exe** . Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).|
|**--tailcalls**[ **+**&#124;**-** ]|Włącza lub wyłącza użycie instrukcji "tail IL", która powoduje, że ramka stosu będzie ponownie używana na potrzeby funkcji cyklicznych. Ta opcja jest domyślnie włączona.|
|**--targetprofile: &lt; ciąg&gt;**|Określa Profil platformy docelowej tego zestawu. Prawidłowe wartości to `mscorlib` , `netcore` , lub `netstandard` . Wartość domyślna to `mscorlib`.|
|**--Użyj: &lt; filename&gt;**|Instruuje interpretera, aby używał danego pliku przy uruchamianiu jako początkowej danych wejściowych.|
|**--utf8output —**|Taka sama jak opcja kompilatora fsc.exe. Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).|
|**--WARN: &lt; ostrzeżenie-poziom&gt;**|Taka sama jak opcja kompilatora **fsc.exe** . Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).|
|**--warnaserror —**[ **+**&#124;**-** ]|Taka sama jak opcja kompilatora **fsc.exe** . Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).|
|**--warnaserror —**[ **+**&#124;**-** ]:** &lt; int-list &gt; **|Taka sama jak opcja kompilatora **fsc.exe** . Aby uzyskać więcej informacji, zobacz [Opcje kompilatora](compiler-options.md).|

## <a name="f-interactive-structured-printing"></a>F# Interactive drukowanie strukturalne

F# Interactive ( `dotnet fsi` ) używa rozszerzonej wersji [prostego formatowania tekstu](plaintext-formatting.md) do raportowania wartości.

1. `%A`Obsługiwane są wszystkie funkcje formatowania zwykłego tekstu, a niektóre można dodatkowo dostosować.

2. Drukowanie jest kolorowe, jeśli kolory są obsługiwane przez konsolę wyjściową.

3. Limit jest umieszczany w pokazanych długośćch ciągów, chyba że jawnie przeznaczysz ten ciąg.

4. Zestaw ustawień definiowanych przez użytkownika jest dostępny za pośrednictwem `fsi` obiektu.

Dostępne ustawienia umożliwiające dostosowanie drukowania zwykłego tekstu dla raportowanych wartości to:

```fsharp
open System.Globalization

fsi.FormatProvider <- CultureInfo("de-DE")  // control the default culture for primitives

fsi.PrintWidth <- 120        // Control the width used for structured printing

fsi.PrintDepth <- 10         // Control the maximum depth of nested printing

fsi.PrintLength <- 10        // Control the length of lists and arrays

fsi.PrintSize <- 100         // Control the maximum overall object count

fsi.ShowProperties <- false  // Control whether properties of .NET objects are shown by default

fsi.ShowIEnumerable <- false // Control whether sequence values are expanded by default

fsi.ShowDeclarationValues <- false // Control whether values are shown for declaration outputs
```

### <a name="customize-with-addprinter-and-addprinttransformer"></a>Dostosuj przy użyciu programu `AddPrinter` i `AddPrintTransformer`

Drukowanie w danych wyjściowych F# Interactive można dostosować za pomocą `fsi.AddPrinter` i `fsi.AddPrintTransformer` .
Pierwsza funkcja daje tekst, aby zastąpić drukowanie obiektu. Druga funkcja zwraca obiekt surogatu do wyświetlenia. Rozważmy na przykład następujący kod F #:

```fsharp
open System

fsi.AddPrinter<DateTime>(fun dt -> dt.ToString("s"))

type DateAndLabel =
    { Date: DateTime
      Label: string  }

let newYearsDay1999 =
    { Date = DateTime(1999, 1, 1)
      Label = "New Year" }
```

W przypadku uruchomienia przykładu w F# Interactive dane wyjściowe w oparciu o zestaw opcji formatowania. W takim przypadku ma wpływ na formatowanie daty i godziny:

```console
type DateAndLabel =
  { Date: DateTime
    Label: string }
val newYearsDay1999 : DateAndLabel = { Date = 1999-01-01T00:00:00
                                       Label = "New Year" }
```

`fsi.AddPrintTransformer` może służyć do nadawania obiektu zastępczego do drukowania:

```fsharp
type MyList(values: int list) =
    member _.Values = values

fsi.AddPrintTransformer(fun (x:MyList) -> box x.Values)

let x = MyList([1..10])
```

Te dane wyjściowe:

```console
val x : MyList = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

Jeśli funkcja Transformer przekazała `fsi.AddPrintTransformer` wartość Returns `null` , transformator wydruku jest ignorowany.
Można go użyć do filtrowania dowolnej wartości wejściowej, zaczynając od typu `obj` .  Na przykład:

```fsharp
fsi.AddPrintTransformer(fun (x:obj) ->
    match x with
    | :? string as s when s = "beep" -> box ["quack"; "quack"; "quack"]
    | _ -> null)

let y = "beep"
```

Te dane wyjściowe:

```console
val y : string = ["quack"; "quack"; "quack"]
```

## <a name="related-topics"></a>Powiązane tematy

|Tytuł|Opis|
|-----|-----------|
|[Opcje kompilatora](compiler-options.md)|Opisuje opcje wiersza polecenia dostępne dla kompilatora F #, **fsc.exe**.|
