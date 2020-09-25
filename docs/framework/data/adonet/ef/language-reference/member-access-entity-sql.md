---
title: . (Dostęp do elementów członkowskich) (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: 82cd2f17b2b5ea484a8202b50619047b428fe94a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192155"
---
# <a name="-member-access-entity-sql"></a><span data-ttu-id="39567-103">.</span><span class="sxs-lookup"><span data-stu-id="39567-103">.</span></span> <span data-ttu-id="39567-104">(Dostęp do elementów członkowskich) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="39567-104">(Member Access) (Entity SQL)</span></span>

<span data-ttu-id="39567-105">Operator kropki (.) jest [!INCLUDE[esql](../../../../../../includes/esql-md.md)] operatorem dostępu elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="39567-105">The dot operator (.) is the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] member access operator.</span></span> <span data-ttu-id="39567-106">Operator dostępu do elementu członkowskiego jest używany do uzyskania wartości właściwości lub pola wystąpienia typu modelu koncepcyjnego koncepcyjny.</span><span class="sxs-lookup"><span data-stu-id="39567-106">You use the member access operator to yield the value of a property or field of an instance of structural conceptual model type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39567-107">Składnia</span><span class="sxs-lookup"><span data-stu-id="39567-107">Syntax</span></span>  
  
```sql  
expression.identifier  
```  
  
## <a name="arguments"></a><span data-ttu-id="39567-108">Argumenty</span><span class="sxs-lookup"><span data-stu-id="39567-108">Arguments</span></span>  

 `expression`  
 <span data-ttu-id="39567-109">Wystąpienie strukturalnego modelu koncepcyjnego.</span><span class="sxs-lookup"><span data-stu-id="39567-109">An instance of a structural conceptual model type.</span></span>  
  
 `identifier`  
 <span data-ttu-id="39567-110">Właściwość lub pole, które należy do wystąpienia obiektu.</span><span class="sxs-lookup"><span data-stu-id="39567-110">A property or field that belongs to an object instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39567-111">Uwagi</span><span class="sxs-lookup"><span data-stu-id="39567-111">Remarks</span></span>  

 <span data-ttu-id="39567-112">Operator kropki (.) może służyć do wyodrębniania pól z rekordu, podobnie jak w przypadku wyodrębniania właściwości typu złożonego lub jednostki.</span><span class="sxs-lookup"><span data-stu-id="39567-112">The dot (.) operator may be used to extract fields from a record, similar to extracting properties of a complex or entity type.</span></span> <span data-ttu-id="39567-113">Na przykład jeśli n typu nazwa jest członkiem typu osoba, a p jest wystąpieniem typu Person, a p. n jest dozwolonym wyrażeniem dostępu do elementu członkowskiego, który zwraca wartość typu Name.</span><span class="sxs-lookup"><span data-stu-id="39567-113">For example, if n of type Name is a member of type Person, and p is an instance of type Person, then p.n is a legal member access expression that yields a value of type Name.</span></span>  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a><span data-ttu-id="39567-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="39567-114">See also</span></span>

- [<span data-ttu-id="39567-115">Odwołanie do jednostki SQL</span><span class="sxs-lookup"><span data-stu-id="39567-115">Entity SQL Reference</span></span>](entity-sql-reference.md)
