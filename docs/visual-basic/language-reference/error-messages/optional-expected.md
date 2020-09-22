---
title: Oczekiwano instrukcji „Optional”
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: e212939cf814a9ac632571b2203f2f256dea61ae
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873601"
---
# <a name="optional-expected"></a><span data-ttu-id="2f8d2-102">Oczekiwano instrukcji „Optional”</span><span class="sxs-lookup"><span data-stu-id="2f8d2-102">'Optional' expected</span></span>

<span data-ttu-id="2f8d2-103">Po argumencie opcjonalnym w deklaracji procedury występuje wymagany argument.</span><span class="sxs-lookup"><span data-stu-id="2f8d2-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="2f8d2-104">Każdy argument po opcjonalnym argumencie musi być również opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="2f8d2-104">Every argument following an optional argument must also be optional.</span></span>  
  
 <span data-ttu-id="2f8d2-105">**Identyfikator błędu:** BC30202</span><span class="sxs-lookup"><span data-stu-id="2f8d2-105">**Error ID:** BC30202</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2f8d2-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="2f8d2-106">To correct this error</span></span>  
  
1. <span data-ttu-id="2f8d2-107">Jeśli argument jest wymagany, przenieś go, aby poprzedzał pierwszy opcjonalny argument na liście argumentów.</span><span class="sxs-lookup"><span data-stu-id="2f8d2-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>  
  
2. <span data-ttu-id="2f8d2-108">Jeśli argument jest zamierzony jako opcjonalny, użyj `Optional` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="2f8d2-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f8d2-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2f8d2-109">See also</span></span>

- [<span data-ttu-id="2f8d2-110">Parametry opcjonalne</span><span class="sxs-lookup"><span data-stu-id="2f8d2-110">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
