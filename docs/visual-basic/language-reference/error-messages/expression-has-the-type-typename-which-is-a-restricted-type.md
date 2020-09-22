---
title: Wyrażenie zawiera typ „<typename>”, który jest typem ograniczonym i nie można go używać do uzyskiwania dostępu do członków dziedziczonych po elemencie „Object” lub „ValueType”.
ms.date: 07/20/2015
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
ms.openlocfilehash: 7fc3f36b28677ed5ebcc0b579f009c796dd431ff
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874219"
---
# <a name="expression-has-the-type-typename-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-object-or-valuetype"></a><span data-ttu-id="15987-102">Wyrażenie zawiera typ „\<typename>”, który jest typem ograniczonym i nie można go używać do uzyskiwania dostępu do członków dziedziczonych po elemencie „Object” lub „ValueType”.</span><span class="sxs-lookup"><span data-stu-id="15987-102">Expression has the type '\<typename>' which is a restricted type and cannot be used to access members inherited from 'Object' or 'ValueType'</span></span>

<span data-ttu-id="15987-103">Wyrażenie daje w wyniku typ, który nie może być opakowany przez środowisko uruchomieniowe języka wspólnego (CLR), ale uzyskuje dostęp do elementu członkowskiego, który wymaga opakowania.</span><span class="sxs-lookup"><span data-stu-id="15987-103">An expression evaluates to a type that cannot be boxed by the common language runtime (CLR) but accesses a member that requires boxing.</span></span>  
  
 <span data-ttu-id="15987-104">*Opakowanie* odnosi się do przetwarzania niezbędnego do wykonania konwersji typu do `Object` lub, w przypadku, do <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="15987-104">*Boxing* refers to the processing necessary to convert a type to `Object` or, on occasion, to <xref:System.ValueType>.</span></span> <span data-ttu-id="15987-105">Środowisko uruchomieniowe języka wspólnego nie może mieć pola niektórych typów struktur, na przykład, <xref:System.ArgIterator> <xref:System.RuntimeArgumentHandle> i <xref:System.TypedReference> .</span><span class="sxs-lookup"><span data-stu-id="15987-105">The common language runtime cannot box certain structure types, for example <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, and <xref:System.TypedReference>.</span></span>  
  
 <span data-ttu-id="15987-106">To wyrażenie próbuje użyć typu ograniczonego do wywołania metody dziedziczonej z <xref:System.Object> lub <xref:System.ValueType> , takich jak <xref:System.Object.GetHashCode%2A> lub <xref:System.Object.ToString%2A> .</span><span class="sxs-lookup"><span data-stu-id="15987-106">This expression attempts to use the restricted type to call a method inherited from <xref:System.Object> or <xref:System.ValueType>, such as <xref:System.Object.GetHashCode%2A> or <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="15987-107">Aby uzyskać dostęp do tej metody, Visual Basic próbowała niejawną konwersję opakowania powodującą ten błąd.</span><span class="sxs-lookup"><span data-stu-id="15987-107">To access this method, Visual Basic has attempted an implicit boxing conversion that causes this error.</span></span>  
  
 <span data-ttu-id="15987-108">**Identyfikator błędu:** BC31393</span><span class="sxs-lookup"><span data-stu-id="15987-108">**Error ID:** BC31393</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="15987-109">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="15987-109">To correct this error</span></span>  
  
1. <span data-ttu-id="15987-110">Znajdź wyrażenie, którego wynikiem jest typ cytowany.</span><span class="sxs-lookup"><span data-stu-id="15987-110">Locate the expression that evaluates to the cited type.</span></span>  
  
2. <span data-ttu-id="15987-111">Znajdź część instrukcji, która próbuje wywołać metodę dziedziczoną z <xref:System.Object> lub <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="15987-111">Locate the part of your statement that attempts to call the method inherited from <xref:System.Object> or <xref:System.ValueType>.</span></span>  
  
3. <span data-ttu-id="15987-112">Napisz ponownie instrukcję, aby uniknąć wywołania metody.</span><span class="sxs-lookup"><span data-stu-id="15987-112">Rewrite the statement to avoid the method call.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15987-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="15987-113">See also</span></span>

- [<span data-ttu-id="15987-114">Konwersje jawne i niejawne</span><span class="sxs-lookup"><span data-stu-id="15987-114">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
