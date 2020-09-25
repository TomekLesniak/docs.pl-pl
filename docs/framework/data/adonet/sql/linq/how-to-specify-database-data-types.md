---
title: 'Instrukcje: Określanie typów danych bazy danych'
ms.date: 03/30/2017
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
ms.openlocfilehash: f070ff718ac10b9681c5ab3c0f4b46547349101b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197238"
---
# <a name="how-to-specify-database-data-types"></a><span data-ttu-id="121bf-102">Instrukcje: Określanie typów danych bazy danych</span><span class="sxs-lookup"><span data-stu-id="121bf-102">How to: Specify Database Data Types</span></span>

<span data-ttu-id="121bf-103">Użyj [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> właściwości dla atrybutu, <xref:System.Data.Linq.Mapping.ColumnAttribute> Aby określić dokładny tekst, który definiuje kolumnę w deklaracji tabeli T-SQL.</span><span class="sxs-lookup"><span data-stu-id="121bf-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify the exact text that defines the column in a T-SQL table declaration.</span></span>  
  
 <span data-ttu-id="121bf-104">Właściwość należy określić <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> tylko wtedy, gdy planujesz użyć, <xref:System.Data.Linq.DataContext.CreateDatabase%2A> Aby utworzyć wystąpienie bazy danych.</span><span class="sxs-lookup"><span data-stu-id="121bf-104">You must specify the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property only if you plan to use <xref:System.Data.Linq.DataContext.CreateDatabase%2A> to create an instance of the database.</span></span>  
  
 <span data-ttu-id="121bf-105">Aby zapoznać się z przykładami kodu, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> .</span><span class="sxs-lookup"><span data-stu-id="121bf-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a><span data-ttu-id="121bf-106">Aby określić tekst definiujący typ danych w tabeli T-SQL</span><span class="sxs-lookup"><span data-stu-id="121bf-106">To specify text to define a data type in a T-SQL table</span></span>  
  
1. <span data-ttu-id="121bf-107">Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> Właściwość do <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="121bf-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="121bf-108">Ustaw wartość <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> właściwości na dokładny tekst, który jest używany przez język T-SQL.</span><span class="sxs-lookup"><span data-stu-id="121bf-108">Set the value of the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the exact text that is used by T-SQL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="121bf-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="121bf-109">See also</span></span>

- [<span data-ttu-id="121bf-110">Model obiektu LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="121bf-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="121bf-111">Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu</span><span class="sxs-lookup"><span data-stu-id="121bf-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
