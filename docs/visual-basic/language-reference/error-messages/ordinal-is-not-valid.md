---
title: Liczba porządkowa nie jest prawidłowa
ms.date: 07/20/2015
f1_keywords:
- vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
ms.openlocfilehash: 64f56b2ecace0ceafb310a175ea605e6959b7256
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871388"
---
# <a name="ordinal-is-not-valid"></a><span data-ttu-id="f9483-102">Liczba porządkowa nie jest prawidłowa</span><span class="sxs-lookup"><span data-stu-id="f9483-102">Ordinal is not valid</span></span>

<span data-ttu-id="f9483-103">Wywołanie do biblioteki dołączanej dynamicznie (DLL) wskazane do użycia numeru zamiast nazwy procedury, przy użyciu `#num` składni.</span><span class="sxs-lookup"><span data-stu-id="f9483-103">Your call to a dynamic-link library (DLL) indicated to use a number instead of a procedure name, using the `#num` syntax.</span></span> <span data-ttu-id="f9483-104">Ten błąd ma następujące możliwe przyczyny:</span><span class="sxs-lookup"><span data-stu-id="f9483-104">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="f9483-105">Próba konwersji `#num` wyrażenia na numer porządkowy nie powiodła się.</span><span class="sxs-lookup"><span data-stu-id="f9483-105">An attempt to convert the `#num` expression to an ordinal failed.</span></span>  
  
- <span data-ttu-id="f9483-106">`#num`Określony nie określa żadnej funkcji w bibliotece DLL.</span><span class="sxs-lookup"><span data-stu-id="f9483-106">The `#num` specified does not specify any function in the DLL.</span></span>  
  
- <span data-ttu-id="f9483-107">Biblioteka typów ma nieprawidłową deklarację powodującą użycie wewnętrznego nieprawidłowego numeru porządkowego.</span><span class="sxs-lookup"><span data-stu-id="f9483-107">A type library has an invalid declaration resulting in internal use of an invalid ordinal number.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f9483-108">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="f9483-108">To correct this error</span></span>  
  
1. <span data-ttu-id="f9483-109">Upewnij się, że wyrażenie reprezentuje poprawną liczbę, lub wywołaj procedurę według nazwy.</span><span class="sxs-lookup"><span data-stu-id="f9483-109">Make sure the expression represents a valid number, or call the procedure by name.</span></span>  
  
2. <span data-ttu-id="f9483-110">Upewnij się `#num` , że w bibliotece DLL zidentyfikowano prawidłową funkcję.</span><span class="sxs-lookup"><span data-stu-id="f9483-110">Make sure `#num` identifies a valid function in the DLL.</span></span>  
  
3. <span data-ttu-id="f9483-111">Wyodrębnij wywołanie procedury powodujące problem, dodając komentarz do kodu.</span><span class="sxs-lookup"><span data-stu-id="f9483-111">Isolate the procedure call causing the problem by commenting out the code.</span></span> <span data-ttu-id="f9483-112">Napisz `Declare` instrukcję do procedury i Zgłoś problem dla dostawcy biblioteki typów.</span><span class="sxs-lookup"><span data-stu-id="f9483-112">Write a `Declare` statement for the procedure, and report the problem to the type library vendor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9483-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f9483-113">See also</span></span>

- [<span data-ttu-id="f9483-114">Declare — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="f9483-114">Declare Statement</span></span>](../statements/declare-statement.md)
