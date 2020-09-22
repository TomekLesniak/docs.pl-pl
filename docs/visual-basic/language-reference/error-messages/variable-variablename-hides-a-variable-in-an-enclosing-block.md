---
title: Zmienna „<variablename>” ukrywa zmienną w otaczającym bloku
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 04538be3431fb06518051db4378e986ea5711219
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875054"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="44845-102">Zmienna „\<variablename>” ukrywa zmienną w otaczającym bloku</span><span class="sxs-lookup"><span data-stu-id="44845-102">Variable '\<variablename>' hides a variable in an enclosing block</span></span>

<span data-ttu-id="44845-103">Zmienna ujęta w bloku ma taką samą nazwę jak inna zmienna lokalna.</span><span class="sxs-lookup"><span data-stu-id="44845-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="44845-104">**Identyfikator błędu:** BC30616</span><span class="sxs-lookup"><span data-stu-id="44845-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="44845-105">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="44845-105">To correct this error</span></span>  
  
- <span data-ttu-id="44845-106">Zmień nazwę zmiennej w załączonym bloku, tak aby nie była taka sama jak jakakolwiek inna zmienna lokalna.</span><span class="sxs-lookup"><span data-stu-id="44845-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="44845-107">Przykład:</span><span class="sxs-lookup"><span data-stu-id="44845-107">For example:</span></span>  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- <span data-ttu-id="44845-108">Typową przyczyną tego błędu jest użycie `Catch e As Exception` wewnątrz procedury obsługi zdarzeń.</span><span class="sxs-lookup"><span data-stu-id="44845-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="44845-109">W takim przypadku należy nazwać `Catch` zmienną bloku `ex` zamiast `e` .</span><span class="sxs-lookup"><span data-stu-id="44845-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
- <span data-ttu-id="44845-110">Innym wspólnym źródłem tego błędu jest próba uzyskania dostępu do zmiennej lokalnej zadeklarowanej w `Try` bloku w oddzielnym `Catch` bloku.</span><span class="sxs-lookup"><span data-stu-id="44845-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="44845-111">Aby to poprawić, zadeklaruj zmienną poza `Try...Catch...Finally` strukturą.</span><span class="sxs-lookup"><span data-stu-id="44845-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44845-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="44845-112">See also</span></span>

- [<span data-ttu-id="44845-113">Try...Catch...Finally, instrukcja</span><span class="sxs-lookup"><span data-stu-id="44845-113">Try...Catch...Finally Statement</span></span>](../statements/try-catch-finally-statement.md)
- [<span data-ttu-id="44845-114">Deklaracja zmiennej</span><span class="sxs-lookup"><span data-stu-id="44845-114">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
