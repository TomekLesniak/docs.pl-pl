---
title: Elementy DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 911a45dad3d5d82ab5e5752b1c12f7d8a6ab1563
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202321"
---
# <a name="datatablereaders"></a>Elementy DataTableReader

<xref:System.Data.DataTableReader>Przedstawia zawartość a <xref:System.Data.DataTable> lub a <xref:System.Data.DataSet> w postaci co najmniej jednego zestawu wyników tylko do odczytu.  
  
 Po utworzeniu **DataTableReader** z **tabeli DataTable**wynikowy obiekt **DataTableReader** zawiera jeden zestaw wyników z tymi samymi danymi co element **DataTable** , z którego został utworzony, z wyjątkiem wierszy, które zostały oznaczone jako usunięte. Kolumny są wyświetlane w takiej samej kolejności jak w oryginalnej **tabeli DataTable**.  
  
 **DataTableReader** może zawierać wiele zestawów wyników, jeśli został utworzony przez wywołanie <xref:System.Data.DataSet.CreateDataReader%2A> . Wyniki znajdują się w takiej samej kolejności jak w **tabelach** danych w kolekcji obiektów **DataSet** <xref:System.Data.DataSet.Tables%2A> .  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Tworzenie elementu DataReader](creating-a-datareader.md)  
 W tym artykule omówiono sposób tworzenia obiektu **DataTableReader** .  
  
 [Nawigowanie w elementach DataTable](navigating-datatables.md)  
 Opisuje użycie metody **Read** , aby przejść przez zawartość **DataTableReader**.  
  
## <a name="see-also"></a>Zobacz też

- [Pobieranie i modyfikowanie danych ADO.NET](../retrieving-and-modifying-data.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
