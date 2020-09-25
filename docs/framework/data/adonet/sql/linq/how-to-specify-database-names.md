---
title: 'Instrukcje: Określanie nazw bazy danych'
ms.date: 03/30/2017
ms.assetid: b80f0fd2-7f75-45fe-9e12-496f80f183df
ms.openlocfilehash: 82cb3f8f31af433b0299b4fec742b548d61921e4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197160"
---
# <a name="how-to-specify-database-names"></a><span data-ttu-id="974a0-102">Instrukcje: Określanie nazw bazy danych</span><span class="sxs-lookup"><span data-stu-id="974a0-102">How to: Specify Database Names</span></span>

<span data-ttu-id="974a0-103">Użyj <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> właściwości dla atrybutu, <xref:System.Data.Linq.Mapping.DatabaseAttribute> Aby określić nazwę bazy danych, gdy nazwa nie jest dostarczana przez połączenie.</span><span class="sxs-lookup"><span data-stu-id="974a0-103">Use the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property on a <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to specify the name of a database when a name is not supplied by the connection.</span></span>  
  
 <span data-ttu-id="974a0-104">Aby zapoznać się z przykładami kodu, zobacz <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> .</span><span class="sxs-lookup"><span data-stu-id="974a0-104">For code samples, see <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>.</span></span>  
  
### <a name="to-specify-the-name-of-the-database"></a><span data-ttu-id="974a0-105">Aby określić nazwę bazy danych</span><span class="sxs-lookup"><span data-stu-id="974a0-105">To specify the name of the database</span></span>  
  
1. <span data-ttu-id="974a0-106">Dodaj <xref:System.Data.Linq.Mapping.DatabaseAttribute> atrybut do deklaracji klasy dla bazy danych.</span><span class="sxs-lookup"><span data-stu-id="974a0-106">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute to the class declaration for the database.</span></span>  
  
2. <span data-ttu-id="974a0-107">Dodaj <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> Właściwość do <xref:System.Data.Linq.Mapping.DatabaseAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="974a0-107">Add the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property to the <xref:System.Data.Linq.Mapping.DatabaseAttribute> attribute.</span></span>  
  
3. <span data-ttu-id="974a0-108">Ustaw <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> wartość właściwości na nazwę, która ma zostać określona.</span><span class="sxs-lookup"><span data-stu-id="974a0-108">Set the <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A> property value to the name that you want to specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="974a0-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="974a0-109">See also</span></span>

- [<span data-ttu-id="974a0-110">Model obiektu LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="974a0-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="974a0-111">Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu</span><span class="sxs-lookup"><span data-stu-id="974a0-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
