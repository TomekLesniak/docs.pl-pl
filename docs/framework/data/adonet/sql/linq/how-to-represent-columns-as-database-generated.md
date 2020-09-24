---
title: 'Instrukcje: Reprezentacja kolumn jako wygenerowanych w bazie danych'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 914fdcb78efbaaddf08330e32e1d7f7c4e62436e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166316"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="a9142-102">Instrukcje: Reprezentacja kolumn jako wygenerowanych w bazie danych</span><span class="sxs-lookup"><span data-stu-id="a9142-102">How to: Represent Columns as Database-Generated</span></span>

<span data-ttu-id="a9142-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> Właściwość w <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybucie służy do wyznaczania pola lub właściwości reprezentującej kolumnę wygenerowaną przez bazę danych.</span><span class="sxs-lookup"><span data-stu-id="a9142-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="a9142-104">Aby zapoznać się z przykładami kodu, zobacz <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> .</span><span class="sxs-lookup"><span data-stu-id="a9142-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="a9142-105">Aby wyznaczyć pole lub właściwość reprezentującą kolumnę wygenerowaną przez bazę danych</span><span class="sxs-lookup"><span data-stu-id="a9142-105">To designate a field or property as representing a database-generated column</span></span>  
  
1. <span data-ttu-id="a9142-106">Dodaj <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> Właściwość do <xref:System.Data.Linq.Mapping.ColumnAttribute> atrybutu.</span><span class="sxs-lookup"><span data-stu-id="a9142-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="a9142-107">Ustaw wartość właściwości na `true` .</span><span class="sxs-lookup"><span data-stu-id="a9142-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9142-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a9142-108">See also</span></span>

- [<span data-ttu-id="a9142-109">Model obiektu LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a9142-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="a9142-110">Instrukcje: Dostosowywanie klas jednostek za pomocą edytora kodu</span><span class="sxs-lookup"><span data-stu-id="a9142-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
