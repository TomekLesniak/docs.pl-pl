---
title: Instrukcje „Module” mogą wystąpić tylko na poziomie pliku lub przestrzeni nazw
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: b946a527d3de3a030ac03691c77afcf440f518ee
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160317"
---
# <a name="bc30617-module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="6b74a-102">BC30617: instrukcje "module" mogą wystąpić tylko na poziomie pliku lub przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="6b74a-102">BC30617: 'Module' statements can occur only at file or namespace level</span></span>

<span data-ttu-id="6b74a-103">`Module` instrukcje muszą pojawić się w górnej części pliku źródłowego bezpośrednio po `Option` i `Imports` instrukcjach, atrybutach globalnych i deklaracjach przestrzeni nazw, ale przed wszystkimi innymi deklaracjami.</span><span class="sxs-lookup"><span data-stu-id="6b74a-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>

 <span data-ttu-id="6b74a-104">**Identyfikator błędu:** BC30617</span><span class="sxs-lookup"><span data-stu-id="6b74a-104">**Error ID:** BC30617</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="6b74a-105">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="6b74a-105">To correct this error</span></span>

- <span data-ttu-id="6b74a-106">Przenieś `Module` instrukcję do początku deklaracji przestrzeni nazw lub pliku źródłowego.</span><span class="sxs-lookup"><span data-stu-id="6b74a-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b74a-107">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="6b74a-107">See also</span></span>

- [<span data-ttu-id="6b74a-108">Module — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="6b74a-108">Module Statement</span></span>](../statements/module-statement.md)
