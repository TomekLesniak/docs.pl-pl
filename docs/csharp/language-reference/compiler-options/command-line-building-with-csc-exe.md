---
description: Kompilacja w wierszu polecenia z csc.exe
title: Kompilacja w wierszu polecenia z csc.exe
ms.date: 04/19/2017
helpviewer_keywords:
- builds [C#]
- command line [C#]
ms.assetid: 66e70056-dd20-453c-a9b3-507e0478b015
ms.openlocfilehash: 9ffd164602862fce7f5e4f0982d3eda7cb403e60
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "89125933"
---
# <a name="command-line-build-with-cscexe"></a>Kompilacja w wierszu polecenia z csc.exe

Kompilator języka C# można wywołać, wpisując nazwę pliku wykonywalnego (*csc.exe*) w wierszu polecenia.

W przypadku korzystania z okna **wiersz polecenia dla deweloperów dla programu Visual Studio** wszystkie wymagane zmienne środowiskowe są ustawiane dla Ciebie. Aby uzyskać informacje na temat sposobu uzyskiwania dostępu do tego narzędzia, zobacz temat [wiersz polecenia dla deweloperów for Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md) .

Jeśli używasz standardowego okna wiersza polecenia, musisz dostosować ścieżkę przed wywołaniem *csc.exe* z dowolnego podkatalogu na komputerze. Należy również uruchomić *VsDevCmd.bat* , aby ustawić odpowiednie zmienne środowiskowe do obsługi kompilacji w wierszu polecenia. Aby uzyskać więcej informacji na temat *VsDevCmd.bat*, w tym instrukcje dotyczące sposobu znajdowania i uruchamiania, zobacz [jak ustawić zmienne środowiskowe dla wiersza polecenia programu Visual Studio](./how-to-set-environment-variables-for-the-visual-studio-command-line.md).

Jeśli pracujesz na komputerze, na którym jest tylko zestaw Windows Software Development Kit (SDK), możesz użyć kompilatora C# w **wierszu polecenia zestawu SDK**, który można otworzyć z poziomu opcji menu **Microsoft .NET Framework SDK** .

Można również użyć programu MSBuild do programistycznego kompilowania programów w języku C#. Aby uzyskać więcej informacji, zobacz [MSBuild](/visualstudio/msbuild/msbuild).

Plik wykonywalny *csc.exe* zwykle znajduje się w folderze Microsoft. NET\Framework \\ *\<Version>* w katalogu *systemu Windows* . Jego lokalizacja może się różnić w zależności od dokładnej konfiguracji określonego komputera. Jeśli na komputerze zainstalowano więcej niż jedną wersję .NET Framework, znajdziesz wiele wersji tego pliku. Aby uzyskać więcej informacji na temat takich instalacji, zobacz [How to: Określanie, które wersje .NET Framework są zainstalowane](../../../framework/migration-guide/how-to-determine-which-versions-are-installed.md).

> [!TIP]
> Podczas kompilowania projektu przy użyciu programu Visual Studio IDE, można wyświetlić polecenie **CSC** i skojarzone z nim opcje kompilatora w oknie **danych wyjściowych** . Aby wyświetlić te informacje, postępuj zgodnie z instrukcjami w temacie [How to: View, Save i Configure log Build Files](/visualstudio/ide/how-to-view-save-and-configure-build-log-files#to-change-the-amount-of-information-included-in-the-build-log) , aby zmienić poziom szczegółowości danych dziennika na **normalny** lub **szczegółowy**. Po odbudowaniu projektu Przeszukaj okno **dane wyjściowe** dla **CSC** , aby znaleźć wywołanie kompilatora języka C#.

 **W tym temacie**

- [Reguły dla składni wiersza polecenia](#rules-for-command-line-syntax-for-the-c-compiler)

- [Przykładowe wiersze poleceń](#sample-command-lines-for-the-c-compiler)

- [Różnice między kompilatorem C# i wyjściem kompilatora języka C++](#differences-between-c-compiler-and-c-compiler-output)

## <a name="rules-for-command-line-syntax-for-the-c-compiler"></a>Reguły dla składni wiersza polecenia dla kompilatora C#

Kompilator języka C# używa następujących reguł, gdy interpretuje argumenty podane w wierszu polecenia systemu operacyjnego:

- Argumenty są rozdzielane znakami odstępu, który jest spacją lub tabulatorem.

- Znak karetki (^) nie jest rozpoznawany jako znak ucieczki lub ogranicznik. Ten znak jest obsługiwany przez analizator wiersza polecenia w systemie operacyjnym przed przekazaniem go do `argv` tablicy w programie.

- Ciąg ujęty w znaki podwójnego cudzysłowu ("String") jest interpretowany jako pojedynczy argument, niezależnie od białego miejsca zawartego w. Ciąg w cudzysłowie może być osadzony w argumencie.

- Podwójny cudzysłów poprzedzony ukośnikiem odwrotnym ( \\ ") jest interpretowany jako literał podwójnego znaku cudzysłowu (").

- Ukośniki odwrotne są interpretowane dosłownie, chyba że od razu poprzedzają podwójny cudzysłów.

- Jeśli parzysta liczba kresek ułamkowych jest poprzedzona znakiem podwójnego cudzysłowu, jeden ukośnik odwrotny jest umieszczany w `argv` tablicy dla każdej pary ukośników odwrotnych, a podwójny cudzysłów jest interpretowany jako ogranicznik ciągu.

- Jeśli po parzystej liczbie ukośników odwrotnych następuje znak podwójnego cudzysłowu, jeden ukośnik odwrotny jest umieszczany w `argv` tablicy dla każdej pary ukośników odwrotnych, a podwójny cudzysłów jest "ucieczkd" przez resztę ukośnika odwrotnego. Powoduje to dodanie literału podwójnego cudzysłowu (") do elementu `argv` .

## <a name="sample-command-lines-for-the-c-compiler"></a>Przykładowe wiersze poleceń dla kompilatora C#

- Kompiluje *File.exe* tworzenia *File.cs* :

  ```console
  csc File.cs
  ```

- Kompiluje *File.dll* tworzenia *File.cs* :

  ```console
  csc -target:library File.cs
  ```

- Kompiluje *File.cs* i tworzy *My.exe*:

  ```console
  csc -out:My.exe File.cs
  ```

- Kompiluje wszystkie pliki C# w bieżącym katalogu z włączonymi optymalizacjami i definiuje symbol debugowania. Dane wyjściowe są *File2.exe*:

  ```console
  csc -define:DEBUG -optimize -out:File2.exe *.cs
  ```

- Kompiluje wszystkie pliki w języku C# w bieżącym katalogu, które wygenerowały wersję Debug *File2.dll*. Brak logo i nie są wyświetlane żadne ostrzeżenia:

  ```console
  csc -target:library -out:File2.dll -warn:0 -nologo -debug *.cs
  ```

- Kompiluje wszystkie pliki C# w bieżącym katalogu na *coś. xyz* (Biblioteka DLL):

  ```console
  csc -target:library -out:Something.xyz *.cs
  ```

## <a name="differences-between-c-compiler-and-c-compiler-output"></a>Różnice między kompilatorem C# i wyjściem kompilatora języka C++

Nie ma plików obiektów (*. obj*) utworzonych w wyniku wywoływania kompilatora języka C#; pliki wyjściowe są tworzone bezpośrednio. W związku z tym kompilator języka C# nie potrzebuje konsolidatora.

## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Opcje kompilatora C# w porządku alfabetycznym](./listed-alphabetically.md)
- [Opcje kompilatora C# w rozbiciu na kategorie](./listed-by-category.md)
- [Main () i Command-Line argumenty](../../programming-guide/main-and-command-args/index.md)
- [Argumenty wiersza poleceń](../../programming-guide/main-and-command-args/command-line-arguments.md)
- [Wyświetlanie argumentów wiersza polecenia](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
- [Main() — Zwracane wartości](../../programming-guide/main-and-command-args/main-return-values.md)
