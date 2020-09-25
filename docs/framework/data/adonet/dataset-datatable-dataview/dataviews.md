---
title: Elementy DataView
ms.date: 03/30/2017
ms.assetid: 0fe5dfa2-c1cd-435f-90b6-b4dd2e3ef34b
ms.openlocfilehash: c5692fcfd1863642bcdf87cbd495d793bce0cbe4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203712"
---
# <a name="dataviews"></a>Elementy DataView

A <xref:System.Data.DataView> umożliwia tworzenie różnych widoków danych przechowywanych w programie <xref:System.Data.DataTable> , które są często używane w aplikacjach do wiązania danych. Za pomocą elementu **DataView**można uwidocznić dane w tabeli z różnymi kolejności sortowania i można filtrować dane według stanu wiersza lub w oparciu o wyrażenie filtru.

 **Element DataView** udostępnia dynamiczny widok danych w źródłowej **tabeli DataTable**: zawartość, kolejność i członkostwo odzwierciedlają zmiany w miarę ich występowania. To zachowanie różni się od metody **SELECT** **elementu DataTable**, która zwraca <xref:System.Data.DataRow> tablicę z tabeli na podstawie określonego filtru i/lub porządku sortowania: Ta zawartość odzwierciedla zmiany w tabeli źródłowej, ale jej członkostwo i porządkowanie pozostają statyczne. Dynamiczne możliwości obiektu **DataView** sprawiają, że są idealnym rozwiązaniem dla aplikacji do wiązania danych.

 **Element DataView** udostępnia dynamiczny widok pojedynczego zestawu danych, podobnie jak widok bazy danych, do którego można zastosować różne kryteria sortowania i filtrowania. W przeciwieństwie do widoku bazy danych, jednak **element DataView** nie może być traktowany jako tabela i nie może zawierać widoku sprzężonych tabel. Nie można również wykluczyć kolumn, które istnieją w tabeli źródłowej, lub dołączać kolumny, które nie istnieją w tabeli źródłowej, takie jak kolumny obliczeniowe.

 <xref:System.Data.DataView.DataViewManager%2A>Aby zarządzać ustawieniami widoku dla wszystkich tabel w **zestawie danych**, można użyć elementu. Element **DataViewManager** zapewnia wygodny sposób zarządzania domyślnymi ustawieniami widoku dla każdej tabeli. W przypadku wiązania kontrolki z więcej niż jedną tabelą **zestawu danych**powiązanie z elementem **DataViewManager** jest idealnym wyborem.

## <a name="in-this-section"></a>W tej sekcji

 [Tworzenie elementu DataView](creating-a-dataview.md) Opisuje sposób tworzenia elementu **DataView** dla **elementu DataTable**.

 [Sortowanie i filtrowanie danych](sorting-and-filtering-data.md) Opisuje sposób ustawiania właściwości elementu **DataView** do zwracania podzbiorów wierszy danych spełniających kryteria filtrowania lub do zwracania danych w określonej kolejności sortowania.

 [DataRows i DataRowView](datarows-and-datarowviews.md) Opisuje sposób uzyskiwania dostępu do danych uwidocznionych przez **Widok DataView**.

 [Znajdowanie wierszy](finding-rows.md) Opisuje, jak znaleźć konkretny wiersz w **widoku**danych.

 [ChildViews i relacje](childviews-and-relations.md) Opisuje sposób tworzenia widoków danych z relacji nadrzędny-podrzędny przy użyciu elementu **DataView**.

 [Modyfikowanie widoków](modifying-dataviews.md) Opisuje, jak modyfikować dane w źródłowej **DataTable** za pośrednictwem **widoku**danych, w tym Włączanie lub wyłączanie aktualizacji.

 [Obsługa zdarzeń DataView](handling-dataview-events.md) Opisuje sposób korzystania z zdarzenia **ListChanged** w celu otrzymywania powiadomień w przypadku aktualizowania zawartości lub kolejności elementu **DataView** .

 [Zarządzanie widokami](managing-dataviews.md) Opisuje, w jaki sposób używać elementu **DataViewManager** do zarządzania ustawieniami **DataView** dla każdej tabeli w **zestawie danych**.

## <a name="related-sections"></a>Sekcje pokrewne

 [ASP.NET aplikacje sieci Web](/previous-versions/655cec97(v=vs.100)) Oferuje przeglądy i szczegółowe procedury krok po kroku dotyczące tworzenia aplikacji ASP.NET, formularzy sieci Web i usług sieci Web.

 [Aplikacje systemu Windows](/previous-versions/ms184421(v=vs.100)) Zawiera szczegółowe informacje dotyczące pracy z aplikacjami Windows Forms i konsolą programu.

 [Zestawy danych, DataTables i DataViews](index.md) Opisuje obiekt **DataSet** i jak można go użyć do zarządzania danymi aplikacji.

 [Tabele DataTables](datatables.md) Opisuje obiekt **DataTable** i sposób, w jaki można go użyć do zarządzania danymi aplikacji przez siebie lub jako część **zestawu danych**.

 [ADO.NET](../index.md) Opisuje architekturę i składniki ADO.NET oraz sposób używania ADO.NET do uzyskiwania dostępu do istniejących źródeł danych i zarządzania danymi aplikacji.

## <a name="see-also"></a>Zobacz też

- [Omówienie ADO.NET](../ado-net-overview.md)
