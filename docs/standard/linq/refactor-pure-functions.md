---
title: Refaktoryzacja do czystych funkcji — LINQ to XML
description: Uzyskaj informacje na temat czystych funkcji i sposobu ich używania w kodzie refaktoryzacji.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 2944a0d4-fd33-4e2e-badd-abb0f9be2fcc
ms.openlocfilehash: 18418a1fc39bee9f08cbe92d42c842e3fc9e148a
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553774"
---
# <a name="refactor-into-pure-functions-linq-to-xml"></a>Refaktoryzacja do czystych funkcji (LINQ to XML)

Ważnym aspektem czystych transformacji funkcjonalnych jest uczenie się, jak kod refaktoryzacji przy użyciu czystych funkcji.

> [!NOTE]
> Wspólna Nomenklatura w programowaniu funkcjonalnym polega na tym, że programy refaktoryzacji używają czystych funkcji. W Visual Basic i C++ jest to zgodne z użyciem funkcji w odpowiednich językach. Jednak w języku C# funkcje są nazywane metodami. Na potrzeby tej dyskusji czysta funkcja jest implementowana jako metoda w języku C#.

Jak wspomniano wcześniej w tej sekcji, czysta funkcja ma dwie przydatne cechy:

- Nie ma żadnych efektów ubocznych. Funkcja nie zmienia żadnych zmiennych ani danych dowolnego typu poza funkcją.
- Jest ona spójna. Mając ten sam zestaw danych wejściowych, zawsze zwróci tę samą wartość wyjściową.

Jednym ze sposobów przejścia do programowania funkcjonalnego jest Refaktoryzacja istniejącego kodu w celu wyeliminowania zbędnych efektów ubocznych i zewnętrznych zależności. W ten sposób można utworzyć czystą wersję funkcji istniejącego kodu.

W tym artykule opisano, co to jest czysta funkcja i czego nie. [Samouczek: manipulowanie zawartością w samouczku dokumentu WordprocessingML](xml-shape-wordprocessingml-documents.md) pokazuje, jak manipulować dokumentem WordprocessingML i zawiera dwa przykłady sposobu refaktoryzacji przy użyciu czystej funkcji.

Poniższe przykłady różnią się dwoma nieczystymi funkcjami i czystą funkcją.

## <a name="example-implement-a-non-pure-function-that-changes-a-static-class-member"></a>Przykład: Zaimplementuj nieczystą funkcję, która zmienia statyczną składową klasy

W poniższym kodzie `HyphenatedConcat` Funkcja nie jest czystą funkcją, ponieważ modyfikuje `aMember` statyczną składową klasy:

```csharp
public class Program
{
    private static string aMember = "StringOne";

    public static void HyphenatedConcat(string appendStr)
    {
        aMember += '-' + appendStr;
    }

    public static void Main()
    {
        HyphenatedConcat("StringTwo");
        Console.WriteLine(aMember);
    }
}
```

```vb
Module Module1
    Dim aMember As String = "StringOne"

    Public Sub HyphenatedConcat(ByVal appendStr As String)
        aMember = aMember & "-" & appendStr
    End Sub

    Sub Main()
        HyphenatedConcat("StringTwo")
        Console.WriteLine(aMember)
    End Sub
End Module
```

Ten przykład generuje następujące wyniki:

```output
StringOne-StringTwo
```

Należy zauważyć, że nie ma znaczenia, czy modyfikowane dane mają `public` lub mają `private` dostęp, czy jest członkiem `static` , `shared` członkiem lub wystąpieniem. Czysta funkcja nie zmienia żadnych danych poza funkcją.

## <a name="example-implement-a-non-pure-function-that-changes-a-parameter"></a>Przykład: Zaimplementuj nieczystą funkcję, która zmienia parametr

Ponadto następująca wersja tej samej funkcji nie jest czysta, ponieważ modyfikuje zawartość jej parametru, `sb` .

```csharp
public class Program
{
    public static void HyphenatedConcat(StringBuilder sb, String appendStr)
    {
        sb.Append('-' + appendStr);
    }

    public static void Main()
    {
        StringBuilder sb1 = new StringBuilder("StringOne");
        HyphenatedConcat(sb1, "StringTwo");
        Console.WriteLine(sb1);
    }
}
```

```vb
Module Module1
    Public Sub HyphenatedConcat(ByVal sb As StringBuilder, ByVal appendStr As String)
        sb.Append("-" & appendStr)
    End Sub

    Sub Main()
        Dim sb1 As StringBuilder = New StringBuilder("StringOne")
        HyphenatedConcat(sb1, "StringTwo")
        Console.WriteLine(sb1)
    End Sub
End Module
```

Ta wersja programu daje te same dane wyjściowe co pierwsza wersja, ponieważ `HyphenatedConcat` Funkcja zmieniła wartość (stan) pierwszego parametru przez wywołanie <xref:System.Text.StringBuilder.Append%2A> funkcji członkowskiej. Należy zauważyć, że ta zmiana występuje pomimo faktu, który `HyphenatedConcat` używa przekazywania parametrów wywołania przez wartość.

> [!IMPORTANT]
> W przypadku typów referencyjnych, Jeśli przekażesz parametr według wartości, wynikiem jest kopia odwołania do obiektu, który jest przekazywany. Ta kopia jest nadal skojarzona z tymi samymi danymi wystąpienia co oryginalne odwołanie (do momentu przypisania zmiennej odniesienia do nowego obiektu). Wywołanie przez odwołanie nie musi być wymagane do zmodyfikowania parametru przez funkcję.

## <a name="example-implement-a-pure-function"></a>Przykład: Zaimplementuj czystą funkcję

Ta Następna wersja programu pokazuje, jak zaimplementować `HyphenatedConcat` funkcję jako czystą funkcję.

```csharp
class Program
{
    public static string HyphenatedConcat(string s, string appendStr)
    {
        return (s + '-' + appendStr);
    }

    public static void Main(string[] args)
    {
        string s1 = "StringOne";
        string s2 = HyphenatedConcat(s1, "StringTwo");
        Console.WriteLine(s2);
    }
}
```

```vb
Module Module1
    Public Function HyphenatedConcat(ByVal s As String, ByVal appendStr As String) As String
        Return (s & "-" & appendStr)
    End Function

    Sub Main()
        Dim s1 As String = "StringOne"
        Dim s2 As String = HyphenatedConcat(s1, "StringTwo")
        Console.WriteLine(s2)
    End Sub
End Module
```

Ta wersja generuje ten sam wiersz danych wyjściowych: `StringOne-StringTwo` . Należy pamiętać, że aby zachować łączną wartość, jest ona przechowywana w zmiennej pośredniej `s2` .

Jednym z metod, które może być bardzo przydatne, jest zapisanie funkcji, które są w sposób nieczysty (to oznacza, że deklarują i modyfikują zmienne lokalne), ale są globalnie czyste. Takie funkcje mają wiele pożądanych cech tworzenia, ale unikają niektórych bardziej zawiłeych idiomy programowania, takich jak korzystanie z rekursji, gdy pętla prosta osiągnie tę samą wartość.

## <a name="standard-query-operators"></a>Standardowe operatory zapytań

Ważną cechą standardowych operatorów zapytań jest to, że są one implementowane jako funkcje czyste.

Aby uzyskać więcej informacji, zobacz [standardowe operatory zapytań — Omówienie (C#)](../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) i [standardowe operatory zapytań — Omówienie (Visual Basic)](../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).

## <a name="see-also"></a>Zobacz też

- [Wprowadzenie do czystych transformacji funkcjonalnych](introduction-pure-functional-transformations.md)
- [Programowanie funkcjonalne a programowanie bezwzględne](functional-vs-imperative-programming.md)
