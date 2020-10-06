---
title: Wprowadzenie do analizy składni (interfejsy API Roslyn)
description: Wprowadzenie do przechodzenia, wykonywania zapytań i eksplorowania drzew składni.
ms.date: 02/05/2018
ms.custom: mvc
ms.openlocfilehash: 8b9dd909a83877755dc1ebafd58aae892e460b93
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756159"
---
# <a name="get-started-with-syntax-analysis"></a>Wprowadzenie do analizy składni

W tym samouczku poznasz **składnię interfejsu API**. Interfejs API składni zapewnia dostęp do struktur danych, które opisują program C# lub Visual Basic. Te struktury danych mają wystarczającą ilość szczegółów, aby można było w pełni reprezentować każdy program dowolnego rozmiaru. Struktury te mogą opisywać kompletne programy, które kompilują i działają poprawnie. Mogą również opisywać niekompletne programy podczas pisania ich w edytorze.

Aby włączyć to wyrażenie bogate, struktury danych i interfejsy API, które składają się na interfejs API składni, muszą być złożone. Zacznijmy od tego, jak wygląda struktura danych dla typowego programu "Hello world":

```csharp
using System;
using System.Collections.Generic;
using System.Linq;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

Spójrz na tekst poprzedniego programu. Rozpoznajesz znane elementy. Cały tekst reprezentuje pojedynczy plik źródłowy lub **jednostkę kompilacji**. Trzy pierwsze wiersze tego pliku źródłowego **używają dyrektyw**. Pozostałe źródło jest zawarte w **deklaracji przestrzeni nazw**. Deklaracja przestrzeni nazw zawiera podrzędną **deklarację klasy**. Deklaracja klasy zawiera jedną **deklarację metody**.

Interfejs API składni tworzy strukturę drzewa z elementem głównym reprezentującym jednostkę kompilacji. Węzły w drzewie reprezentują dyrektywy using, deklarację przestrzeni nazw i wszystkie inne elementy programu. Struktura drzewa przechodzi do najniższych poziomów: ciąg "Hello world!" jest **tokenem literału ciągu** , który jest elementem podrzędnym **argumentu**. Interfejs API składni zapewnia dostęp do struktury programu. Można wykonywać zapytania dotyczące określonych rozwiązań kodu, przeszukać całe drzewo, aby zrozumieć kod i utworzyć nowe drzewa modyfikując istniejące drzewo.

Ten krótki opis zawiera przegląd rodzaju informacji dostępnych przy użyciu interfejsu API składni. Interfejs API składni nie ma więcej niż formalny interfejs API, który opisuje znane konstrukcje kodu znane z języka C#. Pełne możliwości obejmują informacje o sposobie formatowania kodu, w tym podziały wierszy, biały znak i wcięcia. Korzystając z tych informacji, można w pełni przedstawić kod jako zapisany i odczytany przez programistów lub kompilator. Użycie tej struktury umożliwia współpracę z kodem źródłowym na poziomie głęboko zrozumiałym. Nie są już ciągami tekstowymi, ale dane reprezentują strukturę programu w języku C#.

Aby rozpocząć, musisz zainstalować **zestaw SDK .NET compiler platform**:

[!INCLUDE[interactive-note](~/includes/roslyn-installation.md)]

## <a name="understanding-syntax-trees"></a>Opis drzew składni

Za pomocą interfejsu API składni można analizować strukturę kodu w języku C#. **Interfejs API składni** udostępnia analizatory, drzewa składni i narzędzia do analizowania i konstruowania drzew składniowych. Jest to sposób wyszukiwania kodu dla określonych elementów składniowych lub odczytywania kodu dla programu.

Drzewo składni jest strukturą danych używaną przez kompilatory C# i Visual Basic do zrozumienia programów C# i Visual Basic. Drzewa składni są tworzone przez ten sam parser, który jest uruchamiany, gdy projekt jest skompilowany lub deweloper trafi na F5. Drzewa składni mają pełną wierność w języku; każdy bit informacji w pliku kodu jest reprezentowany w drzewie. Zapisanie drzewa składni do tekstu powoduje odtworzenie dokładnego, przeanalizowanego tekstu. Drzewa składniowe są również **niezmienne**; Po utworzeniu drzewa składni nie można go zmienić. Odbiorcy drzew mogą analizować drzewa na wielu wątkach, bez blokowania ani innych miar współbieżności, wiedząc, że dane nigdy nie ulegną zmianie. Za pomocą interfejsów API można tworzyć nowe drzewa, które są wynikiem modyfikacji istniejącego drzewa.

Cztery główne bloki konstrukcyjne drzew składni są następujące:

* <xref:Microsoft.CodeAnalysis.SyntaxTree?displayProperty=nameWithType>Klasa, wystąpienie reprezentujące całe drzewo analizy. <xref:Microsoft.CodeAnalysis.SyntaxTree> jest klasą abstrakcyjną, która ma pochodne specyficzne dla języka. Metody analizy <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxTree?displayProperty=nameWithType> klasy (lub) służą <xref:Microsoft.CodeAnalysis.VisualBasic.VisualBasicSyntaxTree?displayProperty=nameWithType> do analizowania tekstu w języku C# (lub Visual Basic).
* <xref:Microsoft.CodeAnalysis.SyntaxNode?displayProperty=nameWithType>Klasa, wystąpienia reprezentujące konstrukcje składniowe, takie jak deklaracje, instrukcje, klauzule i wyrażenia.
* <xref:Microsoft.CodeAnalysis.SyntaxToken?displayProperty=nameWithType>Struktura, która reprezentuje pojedyncze słowo kluczowe, identyfikator, operator lub interpunkcja.
* I na końcu <xref:Microsoft.CodeAnalysis.SyntaxTrivia?displayProperty=nameWithType> struktury, która reprezentuje składniowo nieznaczące bity informacji, takie jak odstęp między tokenami, dyrektywy przetwarzania wstępnego i komentarze.

Kwizy, tokeny i węzły składają się hierarchicznie w celu utworzenia drzewa, które całkowicie reprezentuje wszystko w fragmencie kodu Visual Basic lub C#. Tę strukturę można zobaczyć przy użyciu okna **Syntax Visualizer** . W programie Visual Studio wybierz pozycję **Wyświetl**  >  **inne okna**  >  **Syntax Visualizer**. Na przykład poprzedni plik źródłowy C# zbadany przy użyciu **Syntax Visualizer** wygląda następująco:

**SyntaxNode**: Blue | **SyntaxToken**: zielony | **SyntaxTrivia**: czerwony ![ plik kodu C#](media/walkthrough-csharp-syntax-figure1.png)

Przechodząc do tej struktury drzewa, można znaleźć dowolne instrukcje, wyrażenie, token lub bit białych znaków w pliku kodu.

Chociaż można znaleźć coś w pliku kodu przy użyciu składni interfejsów API, większość scenariuszy obejmuje badanie małych fragmentów kodu lub wyszukiwanie konkretnych instrukcji lub fragmentów. Dwa przykłady, które obserwują typowe zastosowania do przeglądania struktury kodu lub wyszukiwania pojedynczych instrukcji.

## <a name="traversing-trees"></a>Przechodzenie między drzewami

Węzły w drzewie składni można przeanalizować na dwa sposoby. Można przechodzić przez drzewo, aby zbadać każdy węzeł, lub można wykonywać zapytania dotyczące określonych elementów lub węzłów.

### <a name="manual-traversal"></a>Ręczne przechodzenie

Gotowy kod dla tego przykładu można zobaczyć w [naszym repozytorium GitHub](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/SyntaxQuickStart).

> [!NOTE]
> Typy drzewa składni używają dziedziczenia do opisywania różnych elementów składni, które są prawidłowe w różnych lokalizacjach w programie. Użycie tych interfejsów API często oznacza rzutowanie właściwości lub członków kolekcji na określone typy pochodne. W poniższych przykładach przypisanie i rzutowania są oddzielnymi instrukcjami przy użyciu jawnie wpisanych zmiennych. Kod można odczytać, aby wyświetlić typy zwracane przez interfejs API i typ środowiska uruchomieniowego zwracanych obiektów. W rzeczywistości jest to bardziej powszechne użycie niejawnie wpisanych zmiennych i poleganie na nazwach interfejsów API do opisywania typu badanych obiektów.

Utwórz nowy projekt **Narzędzia do analizy kodu autonomicznego** w języku C#:

* W programie Visual Studio wybierz kolejno pozycje **plik**  >  **Nowy**  >  **projekt** , aby wyświetlić okno dialogowe Nowy projekt.
* W **Visual C#** obszarze  >  **rozszerzalność**Visual C# wybierz pozycję **Narzędzie do analizy kodu autonomicznego**.
* Nadaj projektowi nazwę "**SyntaxTreeManualTraversal**" i kliknij przycisk OK.

Zamierzasz analizować podstawową "Hello world!" pokazany wcześniej program.
Dodaj tekst dla programu Hello world jako stałą w swojej `Program` klasie:

[!code-csharp[Declare the program text](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#1 "Declare a constant string for the program text to analyze")]

Następnie Dodaj następujący kod, aby skompilować **drzewo składni** dla tekstu kodu w `programText` stałej.  Dodaj następujący wiersz do `Main` metody:

[!code-csharp[Create the tree](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#2 "Create the syntax tree")]

Te dwa wiersze tworzą drzewo i pobierają węzeł główny tego drzewa. Teraz można przeanalizować węzły w drzewie. Dodaj te wiersze do `Main` metody, aby wyświetlić niektóre właściwości węzła głównego w drzewie:

[!code-csharp[Examine the root node](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#3 "Examine the root node")]

Uruchom aplikację, aby zobaczyć, co Twój kod wykrył w węźle głównym w tym drzewie.

Zwykle przejdziesz do drzewa, aby dowiedzieć się więcej o kodzie. W tym przykładzie analizujesz kod, który znasz, aby poznać interfejsy API. Dodaj następujący kod, aby przeanalizować pierwszego elementu członkowskiego `root` węzła:

[!code-csharp[Find the first member](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#4 "Find the first member")]

Ten element członkowski jest <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NamespaceDeclarationSyntax?displayProperty=nameWithType> . Reprezentuje wszystko w zakresie `namespace HelloWorld` deklaracji. Dodaj następujący kod, aby ocenić, które węzły są zadeklarowane wewnątrz `HelloWorld` przestrzeni nazw:

[!code-csharp[Find the class declaration](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#5 "Find the class declaration")]

Uruchom program, aby zobaczyć, co się stało.

Teraz, gdy znasz deklarację <xref:Microsoft.CodeAnalysis.CSharp.Syntax.ClassDeclarationSyntax?displayProperty=nameWithType> , Zadeklaruj nową zmienną tego typu, aby sprawdzić deklarację klasy. Ta klasa zawiera tylko jedną składową: `Main` metodę. Dodaj następujący kod, aby znaleźć `Main` metodę i rzutować ją na <xref:Microsoft.CodeAnalysis.CSharp.Syntax.MethodDeclarationSyntax?displayProperty=nameWithType> .

[!code-csharp[Find the main declaration](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#6 "Find the main declaration")]

Węzeł deklaracji metody zawiera wszystkie informacje o składni metody. Umożliwia wyświetlenie zwracanego typu `Main` metody, liczby i typów argumentów oraz tekstu treści metody. Dodaj następujący kod:

[!code-csharp[Examine the syntax of the main method](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#7 "Display information about the main method")]

Uruchom program, aby wyświetlić wszystkie wykryte informacje o tym programie:

```text
The tree is a CompilationUnit node.
The tree has 1 elements in it.
The tree has 4 using statements. They are:
        System
        System.Collections
        System.Linq
        System.Text
The first member is a NamespaceDeclaration.
There are 1 members declared in this namespace.
The first member is a ClassDeclaration.
There are 1 members declared in the Program class.
The first member is a MethodDeclaration.
The return type of the Main method is void.
The method has 1 parameters.
The type of the args parameter is string[].
The body text of the Main method follows:
        {
            Console.WriteLine("Hello, World!");
        }
```

### <a name="query-methods"></a>Metody zapytań

Oprócz przechodzenia między drzewami można także eksplorować drzewo składni przy użyciu metod zapytania zdefiniowanych w <xref:Microsoft.CodeAnalysis.SyntaxNode?displayProperty=nameWithType> . Metody te powinny być od razu znane dla każdego, kto zna wyrażenie XPath. Za pomocą tych metod można szybko znaleźć elementy w drzewie. <xref:Microsoft.CodeAnalysis.SyntaxNode>Ma metody zapytania, takie jak <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantNodes%2A> , <xref:Microsoft.CodeAnalysis.SyntaxNode.AncestorsAndSelf%2A> i <xref:Microsoft.CodeAnalysis.SyntaxNode.ChildNodes%2A> .

Za pomocą tych metod zapytania można znaleźć argument `Main` metody jako alternatywę dla nawigowania po drzewie. Dodaj następujący kod na końcu `Main` metody:

[!code-csharp[Query the tree for the arguments to Main](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/HelloSyntaxTree/Program.cs#8 "Query the tree for the arguments to Main")]

Pierwsza instrukcja używa wyrażenia LINQ i <xref:Microsoft.CodeAnalysis.SyntaxNode.DescendantNodes%2A> metody do lokalizowania tego samego parametru, jak w poprzednim przykładzie.

Uruchom program i sprawdź, czy wyrażenie LINQ znalazło ten sam parametr co ręczne nawigowanie po drzewie.

Przykład używa `WriteLine` instrukcji, aby wyświetlić informacje o drzewach składni w miarę ich przechodzenia. Więcej informacji można również uzyskać, uruchamiając gotowy program w debugerze. Można zapoznać się z większą liczbą właściwości i metod, które są częścią drzewa składni utworzonego dla programu Hello World.

## <a name="syntax-walkers"></a>Instruktaże składniowe

Często chcesz znaleźć wszystkie węzły określonego typu w drzewie składni, na przykład każdą deklarację właściwości w pliku. Rozszerzając <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker?displayProperty=nameWithType> klasę i zastępując <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitPropertyDeclaration(Microsoft.CodeAnalysis.CSharp.Syntax.PropertyDeclarationSyntax)> metodę, przetwarzasz każdą deklarację właściwości w drzewie składni bez uprzedniego znajomości swojej struktury. <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> jest określonym rodzajem <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor> , który rekursywnie odwiedza węzeł i każdy z jego elementów podrzędnych.

Ten przykład implementuje <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> drzewo składni. Zbiera `using` dyrektywy stwierdzające, że nie importuje `System` przestrzeni nazw.

Utwórz nowy projekt **Narzędzia do analizy kodu autonomicznego** w języku C#; Nadaj mu nazwę "**SyntaxWalker**".

Gotowy kod dla tego przykładu można zobaczyć w [naszym repozytorium GitHub](https://github.com/dotnet/samples/tree/master/csharp/roslyn-sdk/SyntaxQuickStart). Przykład w witrynie GitHub zawiera projekty opisane w tym samouczku.

Tak jak w poprzednim przykładzie, można zdefiniować stałą ciągu, aby pomieścić tekst programu, który ma być analizowany:

[!code-csharp[Define the code text to analyzer](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/Program.cs#1 "Define the program text to analyze")]

Ten tekst źródłowy zawiera `using` dyrektywy rozłożone na cztery różne lokalizacje: na poziomie pliku, w przestrzeni nazw najwyższego poziomu i w dwóch zagnieżdżonych obszarach nazw. Ten przykład wyróżnia scenariusz podstawowy dla użycia <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> klasy do wykonywania zapytań w kodzie. Aby znaleźć deklaracje, można odwiedzać każdy węzeł w głównym drzewie składni. Zamiast tego należy utworzyć klasę pochodną i zastąpić metodę, która jest wywoływana tylko wtedy, gdy bieżący węzeł drzewa jest dyrektywą using. Odwiedzający nie wykonuje żadnej pracy na żadnym innym typie węzła. Ta pojedyncza Metoda analizuje poszczególne `using` instrukcje i tworzy kolekcję przestrzeni nazw, które nie znajdują się w `System` przestrzeni nazw. Tworzysz, <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> który bada wszystkie `using` instrukcje, ale tylko te `using` instrukcje.

Po zdefiniowaniu tekstu programu należy utworzyć `SyntaxTree` i uzyskać katalog główny tego drzewa:

[!code-csharp[Create the Syntax tree and access the root](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/Program.cs#2 "Create the Syntax tree and access the root node.")]

Następnie utwórz nową klasę. W programie Visual Studio wybierz pozycję **projekt**  >  **Dodaj nowy element**. W oknie dialogowym **Dodaj nowy element** wpisz *UsingCollector.cs* jako nazwę pliku.

Zaimplementowanie `using` funkcji odwiedzających w `UsingCollector` klasie. Zacznij `UsingCollector` od wprowadzenia klasy pochodnej od <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> .

[!code-csharp[Declare the base class for the using collector](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/UsingCollector.cs#3 "Declare the base class for the UsingCollector")]

Potrzebujesz magazynu, w którym będą przechowywane węzły przestrzeni nazw, które są zbierane.  Zadeklaruj publiczną właściwość tylko do odczytu w `UsingCollector` klasie; ta zmienna służy do przechowywania <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax> odnalezionych węzłów:

[!code-csharp[Declare storage for the using syntax nodes](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/UsingCollector.cs#4 "Declare storage for the using syntax nodes")]

Klasa bazowa, <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxWalker> implementuje logikę, aby odwiedzać każdy węzeł w drzewie składni. Klasa pochodna przesłania metody wywoływane dla określonych odpowiednich węzłów. W takim przypadku interesuje Cię jakąkolwiek `using` dyrektywę. Oznacza to, że należy zastąpić <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitUsingDirective(Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax)> metodę. Jeden argument tej metody jest <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax?displayProperty=nameWithType> obiektem. Jest to ważna korzyść przy użyciu osób odwiedzających: wywołuje zastąpione metody z argumentami, które są już rzutowane na określony typ węzła. <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax?displayProperty=nameWithType>Klasa ma <xref:Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax.Name> Właściwość, która przechowuje nazwę importowanej przestrzeni nazw. Jest to <xref:Microsoft.CodeAnalysis.CSharp.Syntax.NameSyntax?displayProperty=nameWithType> . Dodaj następujący kod w <xref:Microsoft.CodeAnalysis.CSharp.CSharpSyntaxVisitor.VisitUsingDirective(Microsoft.CodeAnalysis.CSharp.Syntax.UsingDirectiveSyntax)> przesłonięciu:

[!code-csharp[Examine using nodes for the System namespace](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/UsingCollector.cs#5 "Examine all using nodes for the System namespace.")]

Podobnie jak w przypadku wcześniejszego przykładu dodano różne `WriteLine` instrukcje ułatwiające zrozumienie tej metody. Możesz zobaczyć, kiedy jest wywoływana, i jakie argumenty są do niego przesyłane za każdym razem.

Na koniec należy dodać dwa wiersze kodu w celu utworzenia `UsingCollector` i odwiedzania węzła głównego, zbierając wszystkie `using` instrukcje. Następnie Dodaj `foreach` pętlę, aby wyświetlić wszystkie `using` instrukcje znalezione przez moduł zbierający:

[!code-csharp[Create the UsingCollector and visit the root node.](../../../../samples/snippets/csharp/roslyn-sdk/SyntaxQuickStart/SyntaxWalker/Program.cs#6 "Create the UsingCollector and visit the root node.")]

Skompiluj i uruchom program. Powinny zostać wyświetlone następujące dane wyjściowe:

```console
        VisitUsingDirective called with System.
        VisitUsingDirective called with System.Collections.Generic.
        VisitUsingDirective called with System.Linq.
        VisitUsingDirective called with System.Text.
        VisitUsingDirective called with Microsoft.CodeAnalysis.
                Success. Adding Microsoft.CodeAnalysis.
        VisitUsingDirective called with Microsoft.CodeAnalysis.CSharp.
                Success. Adding Microsoft.CodeAnalysis.CSharp.
        VisitUsingDirective called with Microsoft.
                Success. Adding Microsoft.
        VisitUsingDirective called with System.ComponentModel.
        VisitUsingDirective called with Microsoft.Win32.
                Success. Adding Microsoft.Win32.
        VisitUsingDirective called with System.Runtime.InteropServices.
        VisitUsingDirective called with System.CodeDom.
        VisitUsingDirective called with Microsoft.CSharp.
                Success. Adding Microsoft.CSharp.
Microsoft.CodeAnalysis
Microsoft.CodeAnalysis.CSharp
Microsoft
Microsoft.Win32
Microsoft.CSharp
Press any key to continue . . .
```

Gratulacje! **Interfejs API składni** jest używany do lokalizowania określonych rodzajów instrukcji i deklaracji języka c# w kodzie źródłowym języka c#.
