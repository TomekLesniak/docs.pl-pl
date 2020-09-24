---
title: 'Instrukcje: Reprezentacja kolumn obliczanych'
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: d952a6c22cd96bbc89aeebfa4b13e9727a363c73
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166329"
---
# <a name="how-to-represent-computed-columns"></a><span data-ttu-id="8713d-102">Instrukcje: Reprezentacja kolumn obliczanych</span><span class="sxs-lookup"><span data-stu-id="8713d-102">How to: Represent Computed Columns</span></span>

<span data-ttu-id="8713d-103">Użyj [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> właściwości dla atrybutu, <xref:System.Data.Linq.Mapping.ColumnAttribute> aby reprezentować kolumnę, której zawartość jest wynikiem obliczania.</span><span class="sxs-lookup"><span data-stu-id="8713d-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to represent a column whose contents are the result of calculation.</span></span>  
  
 <span data-ttu-id="8713d-104">Aby zapoznać się z przykładami kodu, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> .</span><span class="sxs-lookup"><span data-stu-id="8713d-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="8713d-105">Program nie obsługuje kolumn obliczanych jako kluczy podstawowych.</span><span class="sxs-lookup"><span data-stu-id="8713d-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-represent-a-computed-column"></a><span data-ttu-id="8713d-106">Aby przedstawić kolumnę obliczaną</span><span class="sxs-lookup"><span data-stu-id="8713d-106">To represent a computed column</span></span>  
  
1. <span data-ttu-id="8713d-107">Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> Właściwość do <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="8713d-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="8713d-108">Przypisz ciąg reprezentujący formułę do <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="8713d-108">Assign a string representation of the formula to the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8713d-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="8713d-109">See also</span></span>

- [<span data-ttu-id="8713d-110">Model obiektu LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="8713d-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="8713d-111">Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu</span><span class="sxs-lookup"><span data-stu-id="8713d-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
