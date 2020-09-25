---
title: Jak zwrócić podzbiory właściwości elementów w przewodniku programowania zapytania — C#
description: Dowiedz się, jak używać typu anonimowego w wyrażeniu zapytania w języku C#, aby zwracać niektóre właściwości każdego elementu źródłowego.
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: 0ef68921b9d45e58024b37d559ee8291d8744af8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204024"
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a>Jak zwrócić podzbiory właściwości elementu w zapytaniu (Przewodnik programowania w języku C#)

Użyj typu anonimowego w wyrażeniu zapytania, jeśli są spełnione oba te warunki:  
  
- Chcesz zwrócić tylko niektóre właściwości każdego elementu źródłowego.  
  
- Nie jest konieczne przechowywanie wyników zapytania poza zakresem metody, w której jest wykonywane zapytanie.  
  
 Jeśli chcesz zwrócić tylko jedną właściwość lub pole z każdego elementu źródłowego, możesz po prostu użyć operatora kropki w `select` klauzuli. Aby na przykład zwrócić tylko te dane `ID` `student` , należy napisać `select` klauzulę w następujący sposób:  
  
```csharp  
select student.ID;  
```  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak używać typu anonimowego, aby zwrócić tylko podzestaw właściwości każdego elementu źródłowego, który jest zgodny z określonym warunkiem.  
  
 [!code-csharp[csProgGuideLINQ#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#31)]  
  
 Należy pamiętać, że typ anonimowy używa nazw elementów źródłowych dla jego właściwości, jeśli nie określono żadnych nazw. Aby nadać nowym nazw właściwościom typu anonimowego, należy napisać instrukcję w `select` następujący sposób:  
  
```csharp  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 Jeśli spróbujesz użyć tego w poprzednim przykładzie, `Console.WriteLine` należy również zmienić instrukcję:  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
  
Aby uruchomić ten kod, skopiuj i wklej klasę do aplikacji konsolowej C# z `using` dyrektywą dla System. LINQ.
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Typy anonimowe](./anonymous-types.md)
- [LINQ w C#](../../linq/index.md)
