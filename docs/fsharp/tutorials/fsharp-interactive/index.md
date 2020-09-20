---
title: Informacje o F# Interactive (dotnet)
description: 'Dowiedz się, jak F# Interactive (dotnet FSI) służy do interaktywnego uruchamiania kodu F # za pomocą konsoli programu lub wykonywania skryptów języka F #.'
ms.date: 08/20/2020
f1_keywords:
- VS.ToolsOptionsPages.F#_Tools.F#_Interactive
ms.openlocfilehash: ae8d68140ddec8e18ee23e9a43b548907e1ab5c4
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720325"
---
# <a name="interactive-programming-with-f"></a>Programowanie interaktywne przy użyciu języka F\#

F# Interactive (dotnet FSI) służy do interaktywnego uruchamiania kodu F # za pomocą konsoli programu lub do wykonywania skryptów języka F #. Inaczej mówiąc, program F # Interactive wykonuje REPL (odczyt, oszacowanie i drukowanie) dla języka F #.

Aby uruchomić F# Interactive z konsoli programu, uruchom polecenie `dotnet fsi` . Znajdziesz się `dotnet fsi` w dowolnym zestawie SDK platformy .NET.

Aby uzyskać informacje o dostępnych opcjach wiersza polecenia, zobacz [opcje F# Interactive](../../language-reference/fsharp-interactive-options.md).

Aby uruchomić F# Interactive za pomocą programu Visual Studio, można kliknąć odpowiedni przycisk paska narzędzi z etykietą **F# Interactive**lub użyć klawiszy **Ctrl + Alt + F**. Spowoduje to otwarcie okna interaktywnego, okna narzędzia z uruchomioną sesją F# Interactive. Możesz również wybrać kod, który ma być uruchamiany w oknie interaktywnym i nacisnąć kombinację klawiszy **ALT + ENTER**. F# Interactive uruchamia się w oknie narzędzia z etykietą **F# Interactive**. W przypadku korzystania z tej kombinacji klawiszy upewnij się, że okno edytora ma fokus.

Niezależnie od tego, czy używasz konsoli programu, czy programu Visual Studio, zostanie wyświetlony wiersz polecenia, a interpreter czeka na dane wejściowe. Możesz wprowadzić kod tak samo jak w pliku kodu. Aby skompilować i wykonać kod, wprowadź dwa średnika (**;;**), aby zakończyć wiersz lub kilka wierszy danych wejściowych.

F# Interactive próbuje skompilować kod i, jeśli to się powiedzie, wykonuje kod i drukuje sygnaturę typów i wartości, które zostały skompilowane. Jeśli wystąpią błędy, interpreter wyświetla komunikaty o błędach.

Kod wprowadzony w tej samej sesji ma dostęp do dowolnych wcześniej wprowadzonych konstrukcji, dzięki czemu można kompilować programy. Obszerny bufor w oknie narzędzi umożliwia skopiowanie kodu do pliku w razie potrzeby.

W przypadku uruchamiania w programie Visual Studio F# Interactive uruchamiane niezależnie od projektu, więc na przykład nie można używać konstrukcji zdefiniowanych w projekcie w F# Interactive, chyba że skopiujesz kod funkcji do okna interaktywnego.

Jeśli masz otwarty projekt, który odwołuje się do niektórych bibliotek, możesz odwoływać się do nich w F# Interactive przez **Eksplorator rozwiązań**. Aby odwołać się do biblioteki w F# Interactive, rozwiń węzeł **odwołania** , otwórz menu skrótów dla biblioteki i wybierz polecenie **Wyślij do F# Interactive**.

Można kontrolować F# Interactive argumenty wiersza polecenia (Opcje), dostosowując ustawienia. W menu **Narzędzia** wybierz pozycję **Opcje...**, a następnie rozwiń węzeł **Narzędzia języka F #**. Te dwie ustawienia, które można zmienić, to opcje F# Interactive i ustawienie **F# Interactive 64-bitowe** , które jest istotne tylko w przypadku uruchamiania F# Interactive na komputerze 64-bitowym. To ustawienie określa, czy chcesz uruchomić dedykowaną 64-bitową wersję fsi.exe lub fsianycpu.exe, która korzysta z architektury komputera, aby określić, czy uruchomić program jako proces 32-bitowy czy 64-bitowy.

## <a name="scripting-with-f"></a>Wykonywanie skryptów przy użyciu języka F\#

Skrypty używają rozszerzenia pliku **. FSX** lub **. FSSCRIPT**. Zamiast kompilowania kodu źródłowego, a następnie uruchamiania skompilowanego zestawu, można po prostu uruchomić polecenie **dotnet FSI** i określić nazwę pliku skryptu kodu źródłowego języka f #, a program F # Interactive odczytuje kod i wykonuje go w czasie rzeczywistym.

## <a name="differences-between-the-interactive-scripting-and-compiled-environments"></a>Różnice między środowiskami interaktywnymi, skryptowymi i skompilowanymi

Podczas kompilowania kodu w F# Interactive, niezależnie od tego, czy uruchamiasz **interaktywnie** , czy uruchamiasz skrypt, jest zdefiniowany symbol Interactive. Podczas kompilowania kodu w kompilatorze jest zdefiniowany symbol **skompilowany** . W tym przypadku, jeśli kod musi być inny w skompilowanych i interaktywnych trybach, można użyć dyrektyw preprocesora dla kompilacji warunkowej, aby określić, która z nich ma być używana.

Niektóre dyrektywy są dostępne podczas wykonywania skryptów w F# Interactive, które nie są dostępne podczas wykonywania kompilatora. Poniższa tabela zawiera podsumowanie dyrektyw, które są dostępne podczas korzystania z F# Interactive.

|Dyrektywę|Opis|
|---------|-----------|
|**#help**|Wyświetla informacje dotyczące dostępnych dyrektyw.|
|**#I**|Określa ścieżkę wyszukiwania zestawu w cudzysłowie.|
|**#load**|Odczytuje plik źródłowy, kompiluje go i uruchamia.|
|**#quit**|Kończy sesję F# Interactive.|
|**#r**|Odwołuje się do zestawu.|
|**#time ["on" &#124; "off"]**|Niezależnie od tego **#time** włącza, czy mają być wyświetlane informacje o wydajności. Gdy jest włączona, F# Interactive miary czasu rzeczywistego, czasu procesora oraz informacje o wyrzucaniu elementów bezużytecznych dla każdej sekcji kodu, który jest interpretowany i wykonywany.|

Gdy określisz pliki lub ścieżki w F# Interactive, oczekiwano literału ciągu. W związku z tym pliki i ścieżki muszą być ujęte w znaki cudzysłowu, a normalne znaki ucieczki mają zastosowanie. Ponadto można użyć znaku @, aby spowodować, że F# Interactive interpretuje ciąg, który zawiera ścieżkę jako ciąg Verbatim. Powoduje to, że F# Interactive ignoruje wszystkie znaki ucieczki.

Jedną z różnic między skompilowanym i interaktywnym trybem jest sposób dostępu do argumentów wiersza polecenia. W trybie skompilowanym Użyj **System. Environment. GetCommandLineArgs**. W skryptach Użyj **FSI. CommandLineArgs —**.

Poniższy kod ilustruje sposób tworzenia funkcji, która odczytuje argumenty wiersza polecenia w skrypcie, a także pokazuje, jak odwoływać się do innego zestawu ze skryptu. Pierwszy plik kodu, **. FS**, jest kodem, do którego odwołuje się zestaw. Skompiluj ten plik przy użyciu wiersza polecenia: **Urząd nadzoru systemu.** , a następnie wykonaj drugi plik jako skrypt z wierszem polecenia: **FSI--exec plik1. FSX** test

```fsharp
// MyAssembly.fs
module MyAssembly
let myFunction x y = x + 2 * y
```

```fsharp
// file1.fsx
#r "MyAssembly.dll"

printfn "Command line arguments: "

for arg in fsi.CommandLineArgs do
    printfn "%s" arg

printfn "%A" (MyAssembly.myFunction 10 40)
```

Wynik jest następujący:

```console
Command line arguments:
file1.fsx
test
90
```

## <a name="package-management-in-f-interactive"></a>Zarządzanie pakietami w F# Interactive

[!NOTE] Zarządzanie pakietami jest dostępne jako funkcja w wersji zapoznawczej w wersjach `dotnet fsi` dostarczonych w `3.1.300` i nowszych wersjach zestawu .NET SDK, a także wszystkich `5.*` wersjach zestawu .NET SDK. Aby włączyć ją w tej wersji zapoznawczej, uruchom polecenie `dotnet fsi` z `--langversion:preview` argumentem.

`#r`Składnia do odwoływania się do biblioteki DLL w F# Interactive może być również używana do odwoływania się do pakietu NuGet za pomocą następującej składni:

```fsharp
#r "nuget: <package name>
```

Na przykład, aby odwołać się do `FSharp.Data` pakietu, należy użyć następującego `#r` odwołania:

```fsharp
#r "nuget: FSharp.Data"
```

Po wykonaniu tego wiersza Najnowsza wersja `FSharp.Data` pakietu zostanie pobrana do pamięci podręcznej NuGet i przywoływana w bieżącej sesji F# Interactive.

Oprócz nazwy pakietu do określonych wersji pakietu można odwoływać się za pomocą krótkiej składni:

```fsharp
#r "nuget: FSharp.Data, 3.3.2"
```

lub bardziej jawny sposób:

```fsharp
#r "nuget: FSharp.Data, Version=3.3.2"
```

## <a name="related-articles"></a>Pokrewne artykuły:

|Tytuł|Opis|
|-----|-----------|
|[Opcje interakcyjne F#](../../language-reference/fsharp-interactive-options.md)|Opisuje składnię i opcje wiersza polecenia dla F# Interactive, fsi.exe.|
