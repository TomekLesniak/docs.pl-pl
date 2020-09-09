---
title: Ewolucja platformy .NET Core do platformy .NET 5
description: Dowiedz się więcej na temat platformy .NET 5 — platformy deweloperskiej obejmującej wiele platform i typu "open source", która jest kolejną ewolucją platformy .NET Core.
ms.date: 09/02/2020
ms.topic: overview
ms.author: dapine
author: IEvangelist
ms.openlocfilehash: 9318b1afbe22c97f056bd38732306c6a6b60ad00
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598119"
---
# <a name="the-evolution-of-net-core-to-net-5"></a>Ewolucja platformy .NET Core do platformy .NET 5

W tym artykule przedstawiono szczegółowe informacje zawarte w programie .NET 5, który jest następną wersją programu .NET Core 3,1. Numer wersji to 5,0, aby uniknąć nieporozumień przy użyciu .NET Framework 4. x. I "rdzeń" został porzucony z nazwy, ponieważ jest to główna implementacja platformy .NET do przodu. ASP.NET Core zachowuje nazwę "rdzeń", aby uniknąć pomyłki z ASP.NET MVC 5. Ponadto Entity Framework Core zachowuje nazwę "rdzeń", aby uniknąć pomyłki z Entity Framework 5 i 6. Platforma .NET 5 obsługuje więcej typów aplikacji i więcej platform niż .NET Core lub .NET Framework.

Pojawieniu platformy .NET Core rozwinęły ekosystem platformy .NET w atrakcyjny sposób. Zostało ono dojrzałe jako projekt Open Source w witrynie GitHub, świętujemy wkłady społecznościowe i humbly ulepszenie w miarę upływu czasu.

Platforma .NET Core ma kilka podstawowych cech:

> [!div class="checklist"]
>
> - Wiele platform
> - Open source
> - Instalacja równoczesna
> - Małe pliki projektu (zestaw SDK)
> - Elastyczne wdrażanie

Platforma .NET 5 rozszerza te charakterystyki, wprowadzając przyrostowe ulepszenia:

- Aplikacje pojedynczego pliku
- Funkcje wewnętrzne ARM64 i ARM64 systemu Windows
- Udoskonalenia wydajności w celu:
  - [Odzyskiwanie pamięci (GC)](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5/#gc)
  - [System.Text.Json](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5/#json)
  - [System.Text.RegularExpressions](https://devblogs.microsoft.com/dotnet/regex-performance-improvements-in-net-5)
  - [Asynchroniczne buforowanie ValueTask](https://devblogs.microsoft.com/dotnet/async-valuetask-pooling-in-net-5)
  - [Wiele więcej obszarów](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5)
- Optymalizacje rozmiaru kontenera
- [Przycinanie aplikacji](https://devblogs.microsoft.com/dotnet/app-trimming-in-net-5)
- [Udoskonalenia kompilatora języka C#](https://devblogs.microsoft.com/dotnet/automatically-find-latent-bugs-in-your-code-with-net-5)
- Narzędzia obsługujące debugowanie zrzutów
- Platforma to 80% adnotacji dla [typów referencyjnych dopuszczających wartości null](../csharp/nullable-references.md)

### <a name="what-net-5-is-not"></a>Co to jest platforma .NET 5

Platforma .NET 5 nie zastępuje .NET Framework. Nie istnieją plany dotyczące portów następujących technologii z .NET Framework do platformy .NET 5, ale istnieją obsługiwane alternatywy zawarte w programie .NET 5:

| Technologia                             | Zalecenie                                              |
|----------------------------------------|-------------------------------------------------------------|
| Formularze sieci Web                              | [ASP.NET Core Blazor](/aspnet/core/blazor)                  |
| Windows Communication Foundation (WCF) | [gRPC](/aspnet/core/grpc)                                   |
| Windows Workflow (WF)                  | [CoreWF "open source"](https://github.com/UiPath-Open/corewf) |

## <a name="net-standard"></a>.NET Standard

Nowe opracowywanie aplikacji może określać `net5.0` moniker platformy docelowej (TFM) dla wszystkich typów projektów, w tym biblioteki klas. Udostępnianie kodu między obciążeniami programu .NET 5 jest uproszczone w tym, że wszystko, co jest potrzebne, to `net5.0` TFM.

`net5.0`TFM łączy i zastępuje `netcoreapp` `netstandard` nazwy i. Ta TFM zazwyczaj obejmuje tylko technologie, które działają na wielu platformach, takich jak .NET Standard. Jeśli jednak planujesz udostępnianie kodu między obciążeniami .NET Framework, .NET Core i .NET 5, możesz to zrobić, określając `netstandard2.0` jako TFM. Aby uzyskać więcej informacji, zobacz [jak określić Platformy docelowe](../standard/frameworks.md#how-to-specify-a-target-framework).

## <a name="language-updates"></a>Aktualizacje języka

W przypadku platformy .NET 5 Języki programowania .NET są kontynuowane.

### <a name="c-updates"></a>Aktualizacje w języku C#

Deweloperzy piszący aplikacje .NET 5 będą mieli dostęp do najnowszej wersji i funkcji języka C#. Program .NET 5 jest sparowany z językiem C# 9, który oferuje wiele nowych funkcji w języku. Oto kilka świateł:

- Rekordy: niezmienne typy odwołań, które zachowują się jak typy wartości, i wprowadzają nowe `with` słowo kluczowe do języka.
- Dopasowywanie do wzorca relacyjnego: rozszerza możliwości dopasowania wzorców do operatorów relacyjnych dla obliczeń porównawczych i wyrażeń, w tym wzorców logicznych — nowe słowa kluczowe `and` , `or` i `not` .
- Instrukcje najwyższego poziomu: jako metody przyspieszania wdrażania i uczenia się języka C#, `Main` Metoda może zostać pominięta, a aplikacja jako prosta jest prawidłowa:

   ```csharp
   System.Console.Write("Hello world!");
   ```

- Wskaźniki funkcji: konstrukcje języka, które uwidaczniają następujące kod w języku pośrednim (IL): `ldftn` i `calli` .

Aby uzyskać więcej informacji na temat dostępnych funkcji języka C# 9, zobacz [co nowego w języku c# 9](../csharp/whats-new/csharp-9.md).

#### <a name="source-generators"></a>Generatory źródeł

Oprócz niektórych wyróżnionych nowych funkcji języka C#, generatory źródeł są gotowe do projektów deweloperskich. Generatory źródła umożliwiają kod, który jest uruchamiany podczas kompilacji w celu sprawdzenia programu i tworzenia dodatkowych plików, które są kompilowane razem z resztą kodu.

Aby uzyskać więcej informacji na temat generatorów źródeł, zobacz [wprowadzenie do źródłowych generatorów języka c#](https://devblogs.microsoft.com/dotnet/introducing-c-source-generators) i [próbek generatora źródła c#](https://devblogs.microsoft.com/dotnet/new-c-source-generator-samples).

### <a name="f-updates"></a>Aktualizacje języka F #

F # to język programowania funkcjonalny .NET, a w przypadku platformy .NET 5 deweloperzy mają dostęp do programu F # 5. Oto kilka nowych funkcji języka F # 5:

#### <a name="interpolated-strings"></a>Ciągi interpolowane

Podobnie jak ciąg interpolowany w języku C#, a nawet JavaScript, język F # obsługuje interpolację ciągów podstawowych.

```fsharp
let name = "David"
let age = 36
let message = $"{name} is {age} years old."
```

Oprócz podstawowej interpolacji ciągów jest wpisana Interpolacja. Po wpisaniu interpolacji, dany typ musi być zgodny ze specyfikatorem formatu.

```fsharp
let name = "David"
let age = 36
let message = $"%s{name} is %d{age} years old."
```

Jest to podobne do [`sprintf`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-printfmodule.html#sprintf) funkcji, która formatuje ciąg w oparciu o dane wejściowe bezpieczne dla typów. <!-- For more information, see [What's new in F# 5](fsharp/whats-new/fsharp-50.md). -->

### <a name="visual-basic-updates"></a>Aktualizacje Visual Basic

Nie ma nowych funkcji języka dla Visual Basic w programie .NET 5. Jednak w przypadku platformy .NET 5 obsługa Visual Basic została rozszerzona o następujące:

| Opis                            | `dotnet new` konstruktora |
|----------------------------------------|------------------------|
| Aplikacja konsoli                    | `console`              |
| Biblioteka klas                          | `classlib`             |
| Aplikacja WPF                        | `wpf`                  |
| Biblioteka klas WPF                      | `wpflib`               |
| Biblioteka kontrolek niestandardowych WPF             | `wpfcustomcontrollib`  |
| Biblioteka kontrolek użytkownika WPF               | `wpfusercontrollib`    |
| Aplikacja Windows Forms (WinForms)   | `winforms`             |
| Biblioteka klas Windows Forms (WinForms) | `winformslib`          |
| Projekt testu jednostkowego                      | `mstest`               |
| Projekt testowy NUnit 3                   | `nunit`                |
| Element testowy NUnit 3                      | `nunit-test`           |
| Projekt testu xUnit                     | `xunit`                |

Aby uzyskać więcej informacji na temat szablonów projektów z interfejsu wiersza polecenia platformy .NET, zobacz [`dotnet new`](tools/dotnet-new.md) .

## <a name="net-maui"></a>MAUI .NET

.NET MAUI to ewolucja coraz większego popularnego zestawu narzędzi Xamarin. Forms i jest typu open source w witrynie GitHub na platformie [dotnet/Maui](https://github.com/dotnet/maui). W przypadku programu .NET MAUI wybór dla deweloperów platformy .NET jest uproszczony, zapewniając pojedynczy stos obsługujący wszystkie nowoczesne obciążenia: Android, iOS, macOS i Windows. Za pomocą programu .NET MAUI uzyskasz jeden środowisko dewelopera projektu, które jest przeznaczone dla wielu platform i urządzeń.

> [!IMPORTANT]
> Program .NET MAUI jest w wczesnej wersji zapoznawczej. Przykładowy kod źródłowy można znaleźć na platformie [Xamarin/net6-Samples](https://github.com/xamarin/net6-samples).

### <a name="model-view-update-pattern"></a>Model-View-Update — wzorzec

Deweloperzy lubią nowoczesne wzorce projektowania. Podejście do tworzenia interfejsu użytkownika, które jest inspirowane "architekturą Elm", jest wzorcem [Model-View-Update](https://elmprogramming.com/model-view-update-part-1.html) lub MVU. MVU promuje jednokierunkową przepływ zarządzania danymi i Stanami, a także środowisko programistyczne, które szybko aktualizuje interfejs użytkownika, stosując tylko te zmiany.

Na przykład rozważmy następujący licznik zapisany w programie .NET MAUI przy użyciu wzorca MVU:

```csharp
readonly State<int> _count = 0;

[Body]
View body() => new StackLayout
{
    new Label("Welcome to .NET MAUI!"),
    new Button(
        () => $"You clicked {_count} times.",
        () => ++ _count.Value)
    )
};
```

Aby uzyskać więcej informacji, zobacz [plan .NET Maui](https://github.com/dotnet/maui/wiki/Roadmap)i wprowadzenie do artykułu [.NET Maui](https://devblogs.microsoft.com/dotnet/introducing-net-multi-platform-app-ui) .

## <a name="see-also"></a>Zobacz też

- [Podróż do jednego programu .NET](https://channel9.msdn.com/Events/Build/2020/BOD106)
- [Ulepszenia wydajności w programie .NET 5](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5)
