---
title: Funkcje Canonical
ms.date: 03/30/2017
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
ms.openlocfilehash: 11e22d527c4266f45ea5d26f2ec95926ebe46332
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185252"
---
# <a name="canonical-functions"></a>Funkcje Canonical

W tej sekcji omówiono funkcje kanoniczne, które są obsługiwane przez wszystkich dostawców danych, i mogą być używane przez wszystkie technologie zapytań. Nie można rozszerzyć funkcji kanonicznych przez dostawcę.  
  
 Te funkcje kanoniczne zostaną przetłumaczone na odpowiednie funkcje źródła danych dla dostawcy. Pozwala to na wywołania funkcji wyrażone w typowym formacie między źródłami danych.  
  
 Ponieważ te funkcje kanoniczne są niezależne od źródeł danych, argument i zwracane typy funkcji kanonicznych są zdefiniowane w kategoriach typów w modelu koncepcyjnym. Jednak niektóre źródła danych mogą nie obsługiwać wszystkich typów w modelu koncepcyjnym.  
  
 Jeśli w zapytaniu są używane funkcje kanoniczne [!INCLUDE[esql](../../../../../../includes/esql-md.md)] , odpowiednia funkcja zostanie wywołana w źródle danych.  
  
 Wszystkie funkcje kanoniczne mają zarówno zachowanie danych wejściowych, jak i jawne określone warunki błędu. Dostawcy sklepu powinni przestrzegać tego zachowania, ale Entity Framework nie wymusza tego zachowania.  
  
 W przypadku scenariuszy LINQ zapytania dotyczące Entity Framework obejmują mapowanie metod CLR do metod w podstawowym źródle danych. Metody CLR mapują na funkcje kanoniczne, dzięki czemu określony zestaw metod będzie poprawnie mapowany, niezależnie od źródła danych.  
  
## <a name="canonical-functions-namespace"></a>Przestrzeń nazw funkcji kanonicznych  

 Przestrzeń nazw dla funkcji kanonicznej to <xref:System.Data.Metadata.Edm> . <xref:System.Data.Metadata.Edm>Przestrzeń nazw jest automatycznie dołączana do wszystkich zapytań. Jeśli jednak zostanie zaimportowana inna przestrzeń nazw, która zawiera funkcję o takiej samej nazwie jak funkcja kanoniczna (w <xref:System.Data.Metadata.Edm> przestrzeni nazw), należy określić przestrzeń nazw.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Funkcje agregujące Canonical](aggregate-canonical-functions.md)  
 Omawia agregacje funkcji w postaci [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kanonicznej.  
  
 [Funkcje matematyczne Canonical](math-canonical-functions.md)  
 Omawia funkcje matematyczne w postaci [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kanonicznej.  
  
 [Funkcje ciągów Canonical](string-canonical-functions.md)  
 Omawia [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Funkcje ciągów kanonicznych.  
  
 [Funkcji daty i godziny Canonical](date-and-time-canonical-functions.md)  
 Omawia [!INCLUDE[esql](../../../../../../includes/esql-md.md)] funkcje kanoniczne daty i godziny.  
  
 [Funkcje bitowe Canonical](bitwise-canonical-functions.md)  
 Omawia bitowe [!INCLUDE[esql](../../../../../../includes/esql-md.md)] funkcje kanoniczne.  
  
 [Funkcje przestrzenne](spatial-functions.md)  
 Omawia funkcje przestrzenne w postaci [!INCLUDE[esql](../../../../../../includes/esql-md.md)] kanonicznej.  
  
 [Inne funkcje Canonical](other-canonical-functions.md)  
 Omawia funkcje niesklasyfikowane jako bitowe, daty/godziny, String, Math lub Aggregate.  
  
## <a name="see-also"></a>Zobacz też

- [Omówienie jednostki SQL](entity-sql-overview.md)
- [Odwołanie do jednostki SQL](entity-sql-reference.md)
- [Model koncepcyjny Canonical do mapowania funkcji serwera SQL](../conceptual-model-canonical-to-sql-server-functions-mapping.md)
- [Funkcje zdefiniowane przez użytkownika](user-defined-functions-entity-sql.md)
