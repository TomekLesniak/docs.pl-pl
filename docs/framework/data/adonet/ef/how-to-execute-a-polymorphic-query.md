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
# <a name="how-to-execute-a-polymorphic-query"></a><span data-ttu-id="d3dfe-102">Instrukcje: Wykonywanie zapytania polimorficznego</span><span class="sxs-lookup"><span data-stu-id="d3dfe-102">How to: Execute a Polymorphic Query</span></span>

<span data-ttu-id="d3dfe-103">W tym temacie pokazano, jak wykonać zapytanie polimorficzne [!INCLUDE[esql](../../../../../includes/esql-md.md)] przy użyciu operatora [OFTYPE](./language-reference/oftype-entity-sql.md) .</span><span class="sxs-lookup"><span data-stu-id="d3dfe-103">This topic shows how to execute a polymorphic [!INCLUDE[esql](../../../../../includes/esql-md.md)] query using the [OFTYPE](./language-reference/oftype-entity-sql.md) operator.</span></span>

### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="d3dfe-104">Aby uruchomić kod w tym przykładzie</span><span class="sxs-lookup"><span data-stu-id="d3dfe-104">To run the code in this example</span></span>

1. <span data-ttu-id="d3dfe-105">Dodaj [model szkoły](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) do projektu i skonfiguruj projekt tak, aby korzystał z Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="d3dfe-105">Add the [School Model](/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100)) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="d3dfe-106">Aby uzyskać więcej informacji, zobacz [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d3dfe-106">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>

2. <span data-ttu-id="d3dfe-107">Na stronie kodowej aplikacji Dodaj następujące `using` instrukcje ( `Imports` w Visual Basic):</span><span class="sxs-lookup"><span data-stu-id="d3dfe-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. <span data-ttu-id="d3dfe-108">Zmodyfikuj model koncepcyjny w taki sposób, aby miał dziedziczenie na poziomie tabeli, wykonując czynności opisane w [przewodniku: mapowanie dziedziczenia — tabela-na-hierarchia](/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="d3dfe-108">Modify the conceptual model to have a table-per-hierarchy inheritance by following the steps in [Walkthrough: Mapping Inheritance - Table-per-Hierarchy](/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100)).</span></span>

## <a name="example"></a><span data-ttu-id="d3dfe-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="d3dfe-109">Example</span></span>

<span data-ttu-id="d3dfe-110">Poniższy przykład używa operatora OFTYPE do pobierania i wyświetlania kolekcji tylko `OnsiteCourses` z kolekcji `Courses` .</span><span class="sxs-lookup"><span data-stu-id="d3dfe-110">The following example uses an OFTYPE operator to get and display a collection of only `OnsiteCourses` from a collection of `Courses`.</span></span>

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a><span data-ttu-id="d3dfe-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="d3dfe-111">See also</span></span>

- [<span data-ttu-id="d3dfe-112">Dostawca EntityClient dla programu Entity Framework</span><span class="sxs-lookup"><span data-stu-id="d3dfe-112">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
- [<span data-ttu-id="d3dfe-113">Jednostki języka SQL</span><span class="sxs-lookup"><span data-stu-id="d3dfe-113">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
