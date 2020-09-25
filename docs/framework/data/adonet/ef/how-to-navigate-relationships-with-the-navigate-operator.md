---
title: 'Instrukcje: Nawigowanie po relacjach za pomocą operatora nawigowania'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79996d2d-9b03-4a9d-82cc-7c5e7c2ad93d
ms.openlocfilehash: 7d0dbb590555f3e525cd328e4f4b0ad3584f108b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198252"
---
# <a name="how-to-navigate-relationships-with-the-navigate-operator"></a>Instrukcje: Nawigowanie po relacjach za pomocą operatora nawigowania

W tym temacie pokazano, jak wykonać polecenie względem modelu koncepcyjnego za pomocą <xref:System.Data.EntityClient.EntityCommand> obiektu i jak pobrać <xref:System.Data.Metadata.Edm.RefType> wyniki przy użyciu <xref:System.Data.EntityClient.EntityDataReader> .  
  
### <a name="to-run-the-code-in-this-example"></a>Aby uruchomić kod w tym przykładzie  
  
1. Dodaj [model sprzedaży AdventureWorks](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) do projektu i skonfiguruj projekt tak, aby korzystał z Entity Framework. Aby uzyskać więcej informacji, zobacz [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
2. Na stronie kodowej aplikacji Dodaj następujące `using` instrukcje ( `Imports` w Visual Basic):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład pokazuje, jak nawigować w relacji [!INCLUDE[esql](../../../../../includes/esql-md.md)] za pomocą operatora [nawigacji](./language-reference/navigate-entity-sql.md) . `Navigate`Operator przyjmuje następujące parametry: wystąpienie jednostki, typ relacji, koniec relacji i początek relacji... Opcjonalnie można przekazać tylko wystąpienie jednostki i typ relacji do `Navigate` operatora.  
  
 [!code-csharp[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#navigatewithnavoperatorwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#navigatewithnavoperatorwithentitycommand)]  
  
## <a name="see-also"></a>Zobacz też

- [Dostawca EntityClient dla programu Entity Framework](entityclient-provider-for-the-entity-framework.md)
- [Jednostki języka SQL](./language-reference/entity-sql-language.md)
