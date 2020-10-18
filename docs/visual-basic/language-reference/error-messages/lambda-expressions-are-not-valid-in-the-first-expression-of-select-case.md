---
title: Wyrażenia lambda nie są prawidłowe w pierwszym wyrażeniu instrukcji „Select Case"
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: 448a685a7c174ce212389842c31066f1c4557cdf
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162534"
---
# <a name="bc36635-lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a><span data-ttu-id="82976-102">BC36635: wyrażenia lambda nie są prawidłowe w pierwszym wyrażeniu instrukcji "Select Case"</span><span class="sxs-lookup"><span data-stu-id="82976-102">BC36635: Lambda expressions are not valid in the first expression of a 'Select Case' statement</span></span>

<span data-ttu-id="82976-103">Nie można użyć wyrażenia lambda dla wyrażenia testowego w `Select Case` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="82976-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="82976-104">Wyrażenia lambda zwracają funkcje, a wyrażenie testowe `Select Case` instrukcji musi być podstawowym typem danych.</span><span class="sxs-lookup"><span data-stu-id="82976-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>

 <span data-ttu-id="82976-105">Następujący kod powoduje wystąpienie tego błędu:</span><span class="sxs-lookup"><span data-stu-id="82976-105">The following code causes this error:</span></span>

```vb
' Select Case (Function(arg) arg Is Nothing)
    ' List of the cases.
' End Select
```

 <span data-ttu-id="82976-106">**Identyfikator błędu:** BC36635</span><span class="sxs-lookup"><span data-stu-id="82976-106">**Error ID:** BC36635</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="82976-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="82976-107">To correct this error</span></span>

- <span data-ttu-id="82976-108">Sprawdź swój kod, aby określić, czy inna, warunkowa konstrukcja, taka jak `If...Then...Else` instrukcja, będzie działała.</span><span class="sxs-lookup"><span data-stu-id="82976-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>

- <span data-ttu-id="82976-109">Być może zaplanowano wywołanie funkcji, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="82976-109">You may have intended to call the function, as shown in the following code:</span></span>

```vb
Dim num? As Integer
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))
    ' List of the cases
End Select
```

## <a name="see-also"></a><span data-ttu-id="82976-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="82976-110">See also</span></span>

- [<span data-ttu-id="82976-111">Wyrażenia lambda</span><span class="sxs-lookup"><span data-stu-id="82976-111">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="82976-112">If...Then...Else, instrukcja</span><span class="sxs-lookup"><span data-stu-id="82976-112">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="82976-113">Select...Case, instrukcja</span><span class="sxs-lookup"><span data-stu-id="82976-113">Select...Case Statement</span></span>](../statements/select-case-statement.md)
