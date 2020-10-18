---
title: Oczekiwano instrukcji „Optional”
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 9c717cef2052722563e04595ef7a808ea103a75d
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159823"
---
# <a name="bc30202-optional-expected"></a><span data-ttu-id="803d3-102">BC30202: Oczekiwano instrukcji "optional"</span><span class="sxs-lookup"><span data-stu-id="803d3-102">BC30202: 'Optional' expected</span></span>

<span data-ttu-id="803d3-103">Po argumencie opcjonalnym w deklaracji procedury występuje wymagany argument.</span><span class="sxs-lookup"><span data-stu-id="803d3-103">An optional argument in a procedure declaration is followed by a required argument.</span></span> <span data-ttu-id="803d3-104">Każdy argument po opcjonalnym argumencie musi być również opcjonalny.</span><span class="sxs-lookup"><span data-stu-id="803d3-104">Every argument following an optional argument must also be optional.</span></span>

 <span data-ttu-id="803d3-105">**Identyfikator błędu:** BC30202</span><span class="sxs-lookup"><span data-stu-id="803d3-105">**Error ID:** BC30202</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="803d3-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="803d3-106">To correct this error</span></span>

- <span data-ttu-id="803d3-107">Jeśli argument jest wymagany, przenieś go, aby poprzedzał pierwszy opcjonalny argument na liście argumentów.</span><span class="sxs-lookup"><span data-stu-id="803d3-107">If the argument is intended to be required, move it to precede the first optional argument in the argument list.</span></span>

- <span data-ttu-id="803d3-108">Jeśli argument jest zamierzony jako opcjonalny, użyj `Optional` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="803d3-108">If the argument is intended to be optional, use the `Optional` keyword.</span></span>

## <a name="see-also"></a><span data-ttu-id="803d3-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="803d3-109">See also</span></span>

- [<span data-ttu-id="803d3-110">Parametry opcjonalne</span><span class="sxs-lookup"><span data-stu-id="803d3-110">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
