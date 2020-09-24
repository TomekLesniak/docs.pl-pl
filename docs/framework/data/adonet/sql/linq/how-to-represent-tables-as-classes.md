---
title: 'Instrukcje: Reprezentacja tabel jako klas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: c02922351909b097dc06085eefbcc0f131350505
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166225"
---
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="58afa-102">Instrukcje: Reprezentacja tabel jako klas</span><span class="sxs-lookup"><span data-stu-id="58afa-102">How to: Represent Tables as Classes</span></span>

<span data-ttu-id="58afa-103">Użyj [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> atrybutu, aby wyznaczyć klasę jako klasę jednostki skojarzoną z tabelą bazy danych.</span><span class="sxs-lookup"><span data-stu-id="58afa-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="58afa-104">Aby zmapować klasę do tabeli bazy danych</span><span class="sxs-lookup"><span data-stu-id="58afa-104">To map a class to a database table</span></span>  
  
- <span data-ttu-id="58afa-105">Dodaj <xref:System.Data.Linq.Mapping.TableAttribute> atrybut do deklaracji klasy.</span><span class="sxs-lookup"><span data-stu-id="58afa-105">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58afa-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="58afa-106">Example</span></span>  

 <span data-ttu-id="58afa-107">Poniższy kod tworzy `Customer` klasę jako klasę jednostki, która jest skojarzona z `Customers` tabelą bazy danych.</span><span class="sxs-lookup"><span data-stu-id="58afa-107">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="58afa-108">Nie trzeba określać <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> właściwości, jeśli można wywnioskować nazwę.</span><span class="sxs-lookup"><span data-stu-id="58afa-108">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="58afa-109">Jeśli nie określisz nazwy, przyjmuje się, że nazwa jest taka sama jak nazwa właściwości lub pola.</span><span class="sxs-lookup"><span data-stu-id="58afa-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58afa-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="58afa-110">See also</span></span>

- [<span data-ttu-id="58afa-111">Model obiektu LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="58afa-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="58afa-112">Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu</span><span class="sxs-lookup"><span data-stu-id="58afa-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
