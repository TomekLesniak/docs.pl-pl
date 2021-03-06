---
title: Operacje projekcji (C#)
description: Dowiedz się więcej na temat operacji projekcji. Te operacje przekształcają obiekt w nowy formularz, który często zawiera tylko właściwości, które zostaną użyte później.
ms.date: 07/20/2015
ms.assetid: 98df573a-aad9-4b8c-9a71-844be2c4fb41
ms.openlocfilehash: 6128b1bb2e7ba3dbb1b428d475acc307ba931013
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186006"
---
# <a name="projection-operations-c"></a>Operacje projekcji (C#)

Projekcja odnosi się do operacji przekształcenia obiektu w nowy formularz, który często składa się tylko z tych właściwości, które zostaną następnie użyte. Korzystając z projekcji, można utworzyć nowy typ, który jest zbudowany z każdego obiektu. Można projektować Właściwość i wykonywać na niej funkcję matematyczną. Możesz również projektować oryginalny obiekt bez zmieniania go.  
  
 W poniższej sekcji przedstawiono standardowe metody operatorów zapytań, które wykonują projekcję.  
  
## <a name="methods"></a>Metody  
  
|Nazwa metody|Opis|Składnia wyrażenia zapytania C#|Więcej informacji|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Wybierz pozycję|Project wartości, które są oparte na funkcji transformacji.|`select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|  
|SelectMany|Projektuje sekwencje wartości, które są oparte na funkcji transformacji, a następnie spłaszcza je w jedną sekwencję.|Używanie wielu `from` klauzul|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Przykłady składni wyrażeń zapytania  
  
### <a name="select"></a>Wybierz pozycję  

 W poniższym przykładzie zastosowano `select` klauzulę, aby zaprojektować pierwszą literę z każdego ciągu na liście ciągów.  
  
```csharp  
List<string> words = new List<string>() { "an", "apple", "a", "day" };  
  
var query = from word in words  
            select word.Substring(0, 1);  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    a  
    a  
    a  
    d  
*/  
```  
  
### <a name="selectmany"></a>SelectMany  

 Poniższy przykład używa wielu `from` klauzul do tworzenia projektów każdego wyrazu z każdego ciągu na liście ciągów.  
  
```csharp  
List<string> phrases = new List<string>() { "an apple a day", "the quick brown fox" };  
  
var query = from phrase in phrases  
            from word in phrase.Split(' ')  
            select word;  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    an  
    apple  
    a  
    day  
    the  
    quick  
    brown  
    fox  
*/  
```  
  
## <a name="select-versus-selectmany"></a>Wybierz i SelectMany  

 Prace obu `Select()` i `SelectMany()` to generowanie wartości wyniku (lub wartości) z wartości źródłowych. `Select()` tworzy jedną wartość wynikową dla każdej wartości źródłowej. Ogólny wynik to kolekcja, która ma taką samą liczbę elementów jak kolekcja źródłowa. Z kolei program `SelectMany()` tworzy pojedynczy wynik ogólny, który zawiera połączone podkolekcje z każdej wartości źródłowej. Funkcja Transform, która jest przenoszona jako argument do `SelectMany()` musi zwracać wyliczalną sekwencję wartości dla każdej wartości źródłowej. Te wyliczalne sekwencje są następnie łączone przez program, `SelectMany()` Aby utworzyć jedną dużą sekwencję.  
  
 Poniższe dwa ilustracje pokazują różnicę koncepcyjną między działaniami tych dwóch metod. W każdym przypadku Załóżmy, że funkcja selektor (Transform) wybiera tablicę kwiatów z każdej wartości źródłowej.  
  
 Na tej ilustracji przedstawiono sposób, w jaki `Select()` zwraca kolekcję, która ma taką samą liczbę elementów jak kolekcja źródłowa.  
  
 ![Ilustracja przedstawiająca akcję wyboru&#40;&#41;](./media/projection-operations/select-action-graphic.png)  
  
 Na tej ilustracji przedstawiono sposób `SelectMany()` łączenia pośredniej sekwencji tablic w jedną końcową wartość wynikową, która zawiera każdą wartość z każdej tablicy pośredniej.  
  
 ![Ilustracja przedstawiająca akcję SelectMany&#40;&#41;.](./media/projection-operations/select-many-action-graphic.png )  
  
### <a name="code-example"></a>Przykład kodu  

 Poniższy przykład porównuje zachowanie `Select()` i `SelectMany()` . Kod tworzy "bukiet" kwiatów, pobierając pierwsze dwa elementy z każdej listy nazw kwiatów w kolekcji źródłowej. W tym przykładzie "pojedyncza wartość", która jest wykorzystywana przez funkcję transformacji, <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> jest sama kolekcją wartości. Wymaga to dodatkowej `foreach` pętli, aby wyliczyć każdy ciąg w każdej sekwencji podrzędnej.  
  
```csharp  
class Bouquet  
{  
    public List<string> Flowers { get; set; }  
}  
  
static void SelectVsSelectMany()  
{  
    List<Bouquet> bouquets = new List<Bouquet>() {  
        new Bouquet { Flowers = new List<string> { "sunflower", "daisy", "daffodil", "larkspur" }},  
        new Bouquet{ Flowers = new List<string> { "tulip", "rose", "orchid" }},  
        new Bouquet{ Flowers = new List<string> { "gladiolis", "lily", "snapdragon", "aster", "protea" }},  
        new Bouquet{ Flowers = new List<string> { "larkspur", "lilac", "iris", "dahlia" }}  
    };  
  
    // *********** Select ***********
    IEnumerable<List<string>> query1 = bouquets.Select(bq => bq.Flowers);  
  
    // ********* SelectMany *********  
    IEnumerable<string> query2 = bouquets.SelectMany(bq => bq.Flowers);  
  
    Console.WriteLine("Results by using Select():");  
    // Note the extra foreach loop here.  
    foreach (IEnumerable<String> collection in query1)  
        foreach (string item in collection)  
            Console.WriteLine(item);  
  
    Console.WriteLine("\nResults by using SelectMany():");  
    foreach (string item in query2)  
        Console.WriteLine(item);  
  
    /* This code produces the following output:  
  
       Results by using Select():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
  
       Results by using SelectMany():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
    */  
  
}  
```  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Linq>
- [Standardowe operatory zapytań — Omówienie (C#)](./standard-query-operators-overview.md)
- [SELECT — klauzula](../../../language-reference/keywords/select-clause.md)
- [Jak wypełnić kolekcje obiektów z wielu źródeł (LINQ) (C#)](./how-to-populate-object-collections-from-multiple-sources-linq.md)
- [Jak podzielić plik na wiele plików przy użyciu grup (LINQ) (C#)](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
