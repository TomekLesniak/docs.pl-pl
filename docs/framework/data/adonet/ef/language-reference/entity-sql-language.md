---
title: Język Entity SQL
ms.date: 03/30/2017
ms.assetid: 9e7d8837-28c5-429d-a824-7bafb59724cf
ms.openlocfilehash: 721a4cd9d4e5618c083392bbe1ae203f285f8feb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148117"
---
# <a name="entity-sql-language"></a>Język Entity SQL

Entity SQL to język zapytań niezależnych od magazynu, podobny do SQL. Entity SQL umożliwia wykonywanie zapytań dotyczących danych jednostki jako obiektów lub w formie tabelarycznej. Należy rozważyć użycie Entity SQL w następujących przypadkach:  
  
- Gdy zapytanie musi być skonstruowane dynamicznie w czasie wykonywania. W takim przypadku należy również rozważyć użycie metod konstruktora zapytań <xref:System.Data.Objects.ObjectQuery%601> zamiast konstruowania Entity SQL ciągu zapytania w czasie wykonywania.  
  
- Jeśli chcesz zdefiniować zapytanie jako część definicji modelu. Tylko Entity SQL jest obsługiwane w modelu danych. Aby uzyskać więcej informacji, zobacz [QueryView element (MSL)](/ef/ef6/modeling/designer/advanced/edmx/msl-spec#queryview-element-msl)  
  
- W przypadku używania EntityClient do zwracania danych jednostki tylko do odczytu jako zestawów wierszy przy użyciu <xref:System.Data.EntityClient.EntityDataReader> . Aby uzyskać więcej informacji, zobacz [EntityClient Provider for the Entity Framework](../entityclient-provider-for-the-entity-framework.md).  
  
- Jeśli już jesteś ekspertem w językach zapytań opartych na języku SQL, Entity SQL mogą być najbardziej naturalne.  
  
## <a name="using-entity-sql-with-the-entityclient-provider"></a>Używanie Entity SQL z dostawcą EntityClient  

 Jeśli chcesz użyć Entity SQL z dostawcą EntityClient, zobacz następujące tematy, aby uzyskać więcej informacji:  
  
 [Dostawca EntityClient dla programu Entity Framework](../entityclient-provider-for-the-entity-framework.md)  
  
 [Instrukcje: Tworzenie parametrów połączenia EntityConnection](../how-to-build-an-entityconnection-connection-string.md)  
  
 [Instrukcje: Wykonywanie zapytania, które zwraca wyniki PrimitiveType](../how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
 [Instrukcje: Wykonywanie zapytania, które zwraca wyniki StructuralType](../how-to-execute-a-query-that-returns-structuraltype-results.md)  
  
 [Instrukcje: Wykonywanie zapytania, które zwraca wyniki RefType](../how-to-execute-a-query-that-returns-reftype-results.md)  
  
 [Instrukcje: Wykonywanie zapytania, które zwraca typy złożone](../how-to-execute-a-query-that-returns-complex-types.md)  
  
 [Instrukcje: Wykonywanie zapytania, które zwraca kolekcje zagnieżdżone](../how-to-execute-a-query-that-returns-nested-collections.md)  
  
 [Instrukcje: Wykonywanie zapytania SQL do sparametryzowanej jednostki przy użyciu EntityCommand](../how-to-execute-a-parameterized-entity-sql-query-using-entitycommand.md)  
  
 [Instrukcje: Wykonywanie zapytania SQL do sparametryzowanej procedury składowanej przy użyciu EntityCommand](../how-to-execute-a-parameterized-stored-procedure-using-entitycommand.md)  
  
 [Instrukcje: Wykonywanie zapytania polimorficznego](../how-to-execute-a-polymorphic-query.md)  
  
 [Instrukcje: Nawigowanie po relacjach za pomocą operatora nawigowania](../how-to-navigate-relationships-with-the-navigate-operator.md)  
  
## <a name="using-entity-sql-with-object-queries"></a>Używanie Entity SQL z kwerendami obiektów  

 Jeśli chcesz użyć Entity SQL z kwerendami obiektów, zobacz następujące tematy, aby uzyskać więcej informacji:  
  
 [Instrukcje: wykonywanie zapytania, które zwraca obiekty typu jednostki](/previous-versions/dotnet/netframework-4.0/bb738694(v=vs.100))  
  
 [Instrukcje: wykonywanie zapytania parametrycznego](/previous-versions/dotnet/netframework-4.0/bb738521(v=vs.100))  
  
 [Instrukcje: nawigowanie po relacjach przy użyciu właściwości nawigacji](/previous-versions/dotnet/netframework-4.0/bb896321(v=vs.100))  
  
 [Instrukcje: wywoływanie funkcji zdefiniowanej przez użytkownika](/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100))  
  
 [Instrukcje: filtrowanie danych](/previous-versions/dotnet/netframework-4.0/cc716755(v=vs.100))  
  
 [Instrukcje: sortowanie danych](/previous-versions/dotnet/netframework-4.0/cc716784(v=vs.100))  
  
 [Instrukcje: grupowanie danych](/previous-versions/dotnet/netframework-4.0/bb896341(v=vs.100))  
  
 [Instrukcje: agregowanie danych](/previous-versions/dotnet/netframework-4.0/cc716738(v=vs.100))  
  
 [Instrukcje: wykonywanie zapytania, które zwraca obiekty typu anonimowego](/previous-versions/dotnet/netframework-4.0/bb738512(v=vs.100))  
  
 [Instrukcje: wykonywanie zapytania, które zwraca kolekcję typów pierwotnych](/previous-versions/dotnet/netframework-4.0/bb738451(v=vs.100))  
  
 [Instrukcje: zapytanie dotyczące obiektów pokrewnych w obiekcie EntityCollection](/previous-versions/dotnet/netframework-4.0/cc716708(v=vs.100))  
  
 [Jak zamówić złożenie dwóch zapytań](/previous-versions/dotnet/netframework-4.0/bb896299(v=vs.100))  
  
 [Instrukcje: Strona za poorednictwem wyników zapytania](/previous-versions/dotnet/netframework-4.0/bb738702(v=vs.100))  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Omówienie jednostki SQL](entity-sql-overview.md)  
  
 [Odwołanie do jednostki SQL](entity-sql-reference.md)  
  
## <a name="see-also"></a>Zobacz też

- [Program Entity Framework na platformie ADO.NET](../index.md)
- [Dokumentacja języka](index.md)
