---
title: Wykonywanie zapytania dotyczącego zestawów danych (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: bb68d2e4-623d-4d60-85e3-965254f6fee7
ms.openlocfilehash: f42cd792772a4e2b9f24ea8f76ea588da10d9c51
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184979"
---
# <a name="querying-datasets-linq-to-dataset"></a>Wykonywanie zapytania dotyczącego zestawów danych (LINQ to DataSet)

Po wypełnieniu <xref:System.Data.DataSet> obiektu danymi można rozpocząć wykonywanie zapytania. Formułowanie zapytań w LINQ to DataSet jest podobne do korzystania z funkcji CLR (Language-Integrated Query) dla innych źródeł danych obsługujących LINQ. Należy jednak pamiętać, że w przypadku korzystania z zapytań LINQ względem obiektu jest wysyłana <xref:System.Data.DataSet> kwerenda wyliczenia <xref:System.Data.DataRow> obiektów zamiast wyliczenia typu niestandardowego. Oznacza to, że można użyć dowolnego z elementów członkowskich <xref:System.Data.DataRow> klasy w zapytaniach LINQ. Dzięki temu można tworzyć rozbudowane, złożone zapytania.  
  
 Podobnie jak w przypadku innych implementacji LINQ, można utworzyć zapytania LINQ to DataSet w dwóch różnych formularzach: składni wyrażeń zapytania i składni zapytania opartego na metodzie. Można użyć składni wyrażeń zapytania lub składni zapytania opartej na metodzie, aby wykonywać zapytania dotyczące pojedynczych tabel w <xref:System.Data.DataSet> , względem wielu tabel w <xref:System.Data.DataSet> , lub względem tabel w określonym typie <xref:System.Data.DataSet> .  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Zapytania jednotabelowe](single-table-queries-linq-to-dataset.md)  
 Opisuje sposób wykonywania zapytań pojedynczej tabeli.  
  
 [Zapytania wielotabelowe](cross-table-queries-linq-to-dataset.md)  
 Opisuje sposób wykonywania zapytań między tabelami.  
  
 [Wykonywanie zapytania do typizowanych zestawów danych](querying-typed-datasets.md)  
 Opisuje sposób wykonywania zapytań względem wpisanych <xref:System.Data.DataSet> obiektów.  
  
## <a name="see-also"></a>Zobacz też

- [Przykłady LINQ to DataSet](linq-to-dataset-examples.md)
- [Ładowanie danych do zestawu danych](loading-data-into-a-dataset.md)
