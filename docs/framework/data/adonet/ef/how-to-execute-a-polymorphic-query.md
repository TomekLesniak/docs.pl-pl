---
title: 'Instrukcje: Wykonywanie zapytania polimorficznego'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: ad6fd7bf6a23f4cd1591a17b25042fd76ff1d08d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90545340"
---
# <a name="how-to-execute-a-polymorphic-query"></a>Instrukcje: Wykonywanie zapytania polimorficznego

W tym temacie pokazano, jak wykonać zapytanie polimorficzne [!INCLUDE[esql](../../../../../includes/esql-md.md)] przy użyciu operatora [OFTYPE](./language-reference/oftype-entity-sql.md) .

### <a name="to-run-the-code-in-this-example"></a>Aby uruchomić kod w tym przykładzie

1. Dodaj [model szkoły](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) do projektu i skonfiguruj projekt tak, aby korzystał z Entity Framework. Aby uzyskać więcej informacji, zobacz [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).

2. Na stronie kodowej aplikacji Dodaj następujące `using` instrukcje ( `Imports` w Visual Basic):

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. Zmodyfikuj model koncepcyjny w taki sposób, aby miał dziedziczenie na poziomie tabeli, wykonując czynności opisane w [przewodniku: mapowanie dziedziczenia — tabela-na-hierarchia](/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).

## <a name="example"></a>Przykład

Poniższy przykład używa operatora OFTYPE do pobierania i wyświetlania kolekcji tylko `OnsiteCourses` z kolekcji `Courses` .

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a>Zobacz także

- [Dostawca EntityClient dla programu Entity Framework](entityclient-provider-for-the-entity-framework.md)
- [Jednostki języka SQL](./language-reference/entity-sql-language.md)
