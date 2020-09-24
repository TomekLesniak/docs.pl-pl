---
title: 'Instrukcje: Reprezentacja kolumn jako dopuszczających wartości Null'
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: ec88429ed9c1f91917476cc807bd6b53f0bcc3a3
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166368"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="9f3ed-102">Instrukcje: Reprezentacja kolumn jako dopuszczających wartości Null</span><span class="sxs-lookup"><span data-stu-id="9f3ed-102">How to: Represent Columns as Allowing Null Values</span></span>

<span data-ttu-id="9f3ed-103">Użyj [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> właściwości w atrybucie, <xref:System.Data.Linq.Mapping.ColumnAttribute> Aby określić, że skojarzona kolumna bazy danych może zawierać wartości null.</span><span class="sxs-lookup"><span data-stu-id="9f3ed-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="9f3ed-104">Aby zapoznać się z przykładami kodu, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> .</span><span class="sxs-lookup"><span data-stu-id="9f3ed-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="9f3ed-105">Aby wyznaczyć kolumnę jako zezwalającą na wartości null</span><span class="sxs-lookup"><span data-stu-id="9f3ed-105">To designate a column as allowing null values</span></span>  
  
1. <span data-ttu-id="9f3ed-106">Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> Właściwość do <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="9f3ed-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="9f3ed-107">Ustaw <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> wartość właściwości na `true` .</span><span class="sxs-lookup"><span data-stu-id="9f3ed-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f3ed-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9f3ed-108">See also</span></span>

- [<span data-ttu-id="9f3ed-109">Model obiektu LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="9f3ed-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="9f3ed-110">Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu</span><span class="sxs-lookup"><span data-stu-id="9f3ed-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
