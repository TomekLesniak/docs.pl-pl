---
title: Parametry opcjonalne muszą określać wartość domyślną
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 3718fe5c42c8af0948f3b5cb0d120c6876c6f98f
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162456"
---
# <a name="bc30812-optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="9a0a0-102">BC30812: parametry opcjonalne muszą określać wartość domyślną</span><span class="sxs-lookup"><span data-stu-id="9a0a0-102">BC30812: Optional parameters must specify a default value</span></span>

<span data-ttu-id="9a0a0-103">Parametry opcjonalne muszą podawać wartości domyślne, których można użyć, jeśli żaden parametr nie jest dostarczany przez procedurę wywołującą.</span><span class="sxs-lookup"><span data-stu-id="9a0a0-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>

<span data-ttu-id="9a0a0-104">**Identyfikator błędu:** BC30812</span><span class="sxs-lookup"><span data-stu-id="9a0a0-104">**Error ID:** BC30812</span></span>

## <a name="example"></a><span data-ttu-id="9a0a0-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="9a0a0-105">Example</span></span>

<span data-ttu-id="9a0a0-106">Poniższy przykład generuje BC30812:</span><span class="sxs-lookup"><span data-stu-id="9a0a0-106">The following example generates BC30812:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a><span data-ttu-id="9a0a0-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="9a0a0-107">To correct this error</span></span>

<span data-ttu-id="9a0a0-108">Określ wartości domyślne dla parametrów opcjonalnych:</span><span class="sxs-lookup"><span data-stu-id="9a0a0-108">Specify default values for optional parameters:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a><span data-ttu-id="9a0a0-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="9a0a0-109">See also</span></span>

- [<span data-ttu-id="9a0a0-110">Opcjonalne</span><span class="sxs-lookup"><span data-stu-id="9a0a0-110">Optional</span></span>](../modifiers/optional.md)
