---
title: Wyrażenia lambda nie są prawidłowe w pierwszym wyrażeniu instrukcji „Select Case"
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: 9f200ea44e7505c407c7df56e596435024394875
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873876"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a><span data-ttu-id="04a11-102">Wyrażenia lambda nie są prawidłowe w pierwszym wyrażeniu instrukcji „Select Case"</span><span class="sxs-lookup"><span data-stu-id="04a11-102">Lambda expressions are not valid in the first expression of a 'Select Case' statement</span></span>

<span data-ttu-id="04a11-103">Nie można użyć wyrażenia lambda dla wyrażenia testowego w `Select Case` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="04a11-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="04a11-104">Wyrażenia lambda zwracają funkcje, a wyrażenie testowe `Select Case` instrukcji musi być podstawowym typem danych.</span><span class="sxs-lookup"><span data-stu-id="04a11-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>  
  
 <span data-ttu-id="04a11-105">Następujący kod powoduje wystąpienie tego błędu:</span><span class="sxs-lookup"><span data-stu-id="04a11-105">The following code causes this error:</span></span>  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 <span data-ttu-id="04a11-106">**Identyfikator błędu:** BC36635</span><span class="sxs-lookup"><span data-stu-id="04a11-106">**Error ID:** BC36635</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="04a11-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="04a11-107">To correct this error</span></span>  
  
- <span data-ttu-id="04a11-108">Sprawdź swój kod, aby określić, czy inna, warunkowa konstrukcja, taka jak `If...Then...Else` instrukcja, będzie działała.</span><span class="sxs-lookup"><span data-stu-id="04a11-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>  
  
- <span data-ttu-id="04a11-109">Być może zaplanowano wywołanie funkcji, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="04a11-109">You may have intended to call the function, as shown in the following code:</span></span>  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a><span data-ttu-id="04a11-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="04a11-110">See also</span></span>

- [<span data-ttu-id="04a11-111">Wyrażenia lambda</span><span class="sxs-lookup"><span data-stu-id="04a11-111">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="04a11-112">If...Then...Else, instrukcja</span><span class="sxs-lookup"><span data-stu-id="04a11-112">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="04a11-113">Select...Case, instrukcja</span><span class="sxs-lookup"><span data-stu-id="04a11-113">Select...Case Statement</span></span>](../statements/select-case-statement.md)
