---
title: Identyfikator jest za długi
ms.date: 07/20/2015
f1_keywords:
- bc30033
- vbc30033
helpviewer_keywords:
- BC30033
ms.assetid: 3d07f6d0-9a2f-49ca-94e8-1e354932e855
ms.openlocfilehash: eafcb2fdf706e12fa606a442ad577c88ed5a7427
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162859"
---
# <a name="bc30033-identifier-is-too-long"></a><span data-ttu-id="0dec1-102">BC30033: Identyfikator jest za długi</span><span class="sxs-lookup"><span data-stu-id="0dec1-102">BC30033: Identifier is too long</span></span>

<span data-ttu-id="0dec1-103">Nazwa lub identyfikator każdego elementu programistycznego jest ograniczone do 1023 znaków.</span><span class="sxs-lookup"><span data-stu-id="0dec1-103">The name, or identifier, of every programming element is limited to 1023 characters.</span></span> <span data-ttu-id="0dec1-104">Ponadto w pełni kwalifikowana nazwa nie może być dłuższa niż 1023 znaków.</span><span class="sxs-lookup"><span data-stu-id="0dec1-104">In addition, a fully qualified name cannot exceed 1023 characters.</span></span> <span data-ttu-id="0dec1-105">Oznacza to, że cały ciąg identyfikatora ( `<namespace>.<...>.<namespace>.<class>.<element>` ) nie może mieć więcej niż 1023 znaków, łącznie z znakami operator dostępu do składowych ( `.` ).</span><span class="sxs-lookup"><span data-stu-id="0dec1-105">This means that the entire identifier string (`<namespace>.<...>.<namespace>.<class>.<element>`) cannot be more than 1023 characters long, including the member-access operator (`.`) characters.</span></span>

 <span data-ttu-id="0dec1-106">**Identyfikator błędu:** BC30033</span><span class="sxs-lookup"><span data-stu-id="0dec1-106">**Error ID:** BC30033</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0dec1-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="0dec1-107">To correct this error</span></span>

- <span data-ttu-id="0dec1-108">Zmniejsz długość identyfikatora.</span><span class="sxs-lookup"><span data-stu-id="0dec1-108">Reduce the length of the identifier.</span></span>

## <a name="see-also"></a><span data-ttu-id="0dec1-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0dec1-109">See also</span></span>

- [<span data-ttu-id="0dec1-110">Nazwy zadeklarowanych elementów</span><span class="sxs-lookup"><span data-stu-id="0dec1-110">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
