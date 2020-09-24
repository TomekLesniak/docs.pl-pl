---
title: Powiązanie danych i LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 310bff4a-32dd-4f20-a271-6dbd82912631
ms.openlocfilehash: 3203310029f463e55d7517e79f5a1f0424a0a80c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166875"
---
# <a name="data-binding-and-linq-to-dataset"></a>Powiązanie danych i LINQ to DataSet

*Powiązanie danych* to proces, który ustanawia połączenie między interfejsem użytkownika aplikacji i logiką biznesową. Jeśli powiązanie ma poprawne ustawienia, a dane udostępniają odpowiednie powiadomienia, gdy zmieniają się dane, elementy, które są powiązane z danymi, odzwierciedlają zmiany automatycznie. <xref:System.Data.DataSet>Jest reprezentacja danych w pamięci, która zapewnia spójny relacyjny model programowania, niezależnie od źródła danych, które zawiera. ADO.NET 2,0 <xref:System.Data.DataView> pozwala sortować i filtrować dane przechowywane w <xref:System.Data.DataTable> . Ta funkcja jest często używana w aplikacjach do wiązania danych. Za pomocą <xref:System.Data.DataView> , można uwidocznić dane w tabeli z różnymi kolejności sortowania i można filtrować dane według stanu wiersza lub w oparciu o wyrażenie filtru. Aby uzyskać więcej informacji na temat <xref:System.Data.DataView> obiektu, zobacz [DataViews](./dataset-datatable-dataview/dataviews.md).  
  
 LINQ to DataSet umożliwia deweloperom tworzenie złożonych, zaawansowanych zapytań w odniesieniu do programu <xref:System.Data.DataSet> przy użyciu technologii LINQ (Language-Integrated Query). Jednak zapytanie LINQ to DataSet zwraca Wyliczenie <xref:System.Data.DataRow> obiektów, które nie jest łatwo używane w scenariuszu powiązania. Aby ułatwić tworzenie powiązań, można utworzyć zapytanie na <xref:System.Data.DataView> podstawie LINQ to DataSet. Powoduje to <xref:System.Data.DataView> użycie filtrowania i sortowania określonego w zapytaniu, ale jest lepiej dopasowane do powiązania danych. LINQ to DataSet rozszerza funkcje programu, <xref:System.Data.DataView> zapewniając filtrowanie i sortowanie oparte na wyrażeniach LINQ, które pozwala na znacznie bardziej złożone i zaawansowane operacje filtrowania i sortowania niż oparte na ciągach filtrowanie i sortowanie.  
  
 Należy zauważyć, że <xref:System.Data.DataView> reprezentuje kwerendę i nie jest widokiem na górze zapytania. <xref:System.Data.DataView>Jest powiązany z kontrolką interfejsu użytkownika, taką jak <xref:System.Windows.Forms.DataGrid> lub <xref:System.Windows.Forms.DataGridView> , dostarczając prosty model powiązań danych. <xref:System.Data.DataView>Można również utworzyć z <xref:System.Data.DataTable> , dostarczając widok domyślny tej tabeli.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Tworzenie obiektu widoku danych](creating-a-dataview-object-linq-to-dataset.md)  
 Zawiera informacje na temat tworzenia <xref:System.Data.DataView> .  
  
 [Filtrowanie za pomocą widoku danych](filtering-with-dataview-linq-to-dataset.md)  
 Opisuje sposób filtrowania przy użyciu <xref:System.Data.DataView> .  
  
 [Sortowanie za pomocą widoku danych](sorting-with-dataview-linq-to-dataset.md)  
 Opisuje sposób sortowania przy użyciu <xref:System.Data.DataView> .  
  
 [Wykonywanie zapytania do kolekcji DataRowView w widoku danych](querying-the-datarowview-collection-in-a-dataview.md)  
 Zawiera informacje o wysyłaniu zapytań do <xref:System.Data.DataRowView> kolekcji uwidocznionej przez program <xref:System.Data.DataView> .  
  
 [Wydajność widoku danych](dataview-performance.md)  
 Zawiera informacje o <xref:System.Data.DataView> wydajności i.  
  
 [Instrukcje: Wiązanie obiektu widoku danych z kontrolką DataGridView formularzy systemu Windows](how-to-bind-a-dataview-object-to-a-winforms-datagridview-control.md)  
 Opisuje sposób powiązania <xref:System.Data.DataView> obiektu z <xref:System.Windows.Forms.DataGridView> .  
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania](programming-guide-linq-to-dataset.md)
