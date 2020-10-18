---
title: Właściwość „<propertyname>” nie zwraca wartości we wszystkich ścieżkach kodu
ms.date: 07/20/2015
f1_keywords:
- bc42107
- vbc42107
helpviewer_keywords:
- BC42107
ms.assetid: 06800966-9c3b-4844-9f13-83ac95607d32
ms.openlocfilehash: 0736e2cbcdea1422d40161c88f898d487f72e3bc
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162391"
---
# <a name="bc42107-property-propertyname-doesnt-return-a-value-on-all-code-paths"></a><span data-ttu-id="45814-102">BC42107: Właściwość " \<propertyname> " nie zwraca wartości we wszystkich ścieżkach kodu</span><span class="sxs-lookup"><span data-stu-id="45814-102">BC42107: Property '\<propertyname>' doesn't return a value on all code paths</span></span>

<span data-ttu-id="45814-103">Właściwość " \<propertyname> " nie zwraca wartości we wszystkich ścieżkach kodu.</span><span class="sxs-lookup"><span data-stu-id="45814-103">Property '\<propertyname>' doesn't return a value on all code paths.</span></span> <span data-ttu-id="45814-104">W czasie wykonywania może wystąpić wyjątek odwołania o wartości null, gdy zostanie użyty wynik.</span><span class="sxs-lookup"><span data-stu-id="45814-104">A null reference exception could occur at run time when the result is used.</span></span>

<span data-ttu-id="45814-105">Procedura właściwości `Get` ma co najmniej jedną możliwą ścieżkę za pomocą kodu, który nie zwraca wartości.</span><span class="sxs-lookup"><span data-stu-id="45814-105">A property `Get` procedure has at least one possible path through its code that does not return a value.</span></span>

 <span data-ttu-id="45814-106">Można zwrócić wartość z `Get` procedury właściwości w dowolny z następujących sposobów:</span><span class="sxs-lookup"><span data-stu-id="45814-106">You can return a value from a property `Get` procedure in any of the following ways:</span></span>

- <span data-ttu-id="45814-107">Przypisz wartość do nazwy właściwości, a następnie wykonaj `Exit Property` instrukcję.</span><span class="sxs-lookup"><span data-stu-id="45814-107">Assign the value to the property name and then perform an `Exit Property` statement.</span></span>

- <span data-ttu-id="45814-108">Przypisz wartość do nazwy właściwości, a następnie wykonaj `End Get` instrukcję.</span><span class="sxs-lookup"><span data-stu-id="45814-108">Assign the value to the property name and then perform the `End Get` statement.</span></span>

- <span data-ttu-id="45814-109">Dołącz wartość do [instrukcji return](../statements/return-statement.md).</span><span class="sxs-lookup"><span data-stu-id="45814-109">Include the value in a [Return Statement](../statements/return-statement.md).</span></span>

<span data-ttu-id="45814-110">Jeśli kontrola przechodzi do `Exit Property` lub `End Get` i nie przypisano żadnej wartości do nazwy właściwości, `Get` procedura zwraca wartość domyślną typu danych właściwości.</span><span class="sxs-lookup"><span data-stu-id="45814-110">If control passes to `Exit Property` or `End Get` and you have not assigned any value to the property name, the `Get` procedure returns the default value of the property's data type.</span></span> <span data-ttu-id="45814-111">Aby uzyskać więcej informacji, zobacz "zachowanie" w [instrukcji funkcji](../statements/function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="45814-111">For more information, see "Behavior" in [Function Statement](../statements/function-statement.md).</span></span>

<span data-ttu-id="45814-112">Domyślnie ten komunikat jest ostrzeżeniem.</span><span class="sxs-lookup"><span data-stu-id="45814-112">By default, this message is a warning.</span></span> <span data-ttu-id="45814-113">Aby uzyskać więcej informacji na temat ukrywania ostrzeżeń lub leczenia ostrzeżeń jako błędów, zobacz [Konfigurowanie ostrzeżeń w Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="45814-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

<span data-ttu-id="45814-114">**Identyfikator błędu:** BC42107</span><span class="sxs-lookup"><span data-stu-id="45814-114">**Error ID:** BC42107</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="45814-115">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="45814-115">To correct this error</span></span>

- <span data-ttu-id="45814-116">Sprawdź logikę przepływu sterowania i upewnij się, że przypiszesz wartość przed każdą instrukcją, która powoduje zwrócenie.</span><span class="sxs-lookup"><span data-stu-id="45814-116">Check your control flow logic and make sure you assign a value before every statement that causes a return.</span></span>

  <span data-ttu-id="45814-117">Łatwiej jest zagwarantować, że każde zwrócenie z procedury zwraca wartość, jeśli zawsze używasz `Return` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="45814-117">It's easier to guarantee that every return from the procedure returns a value if you always use the `Return` statement.</span></span> <span data-ttu-id="45814-118">Jeśli to zrobisz, ostatnią instrukcją przed `End Get` powinien być `Return` instrukcja.</span><span class="sxs-lookup"><span data-stu-id="45814-118">If you do this, the last statement before `End Get` should be a `Return` statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="45814-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="45814-119">See also</span></span>

- [<span data-ttu-id="45814-120">Procedury własności</span><span class="sxs-lookup"><span data-stu-id="45814-120">Property Procedures</span></span>](../../programming-guide/language-features/procedures/property-procedures.md)
- [<span data-ttu-id="45814-121">Property — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="45814-121">Property Statement</span></span>](../statements/property-statement.md)
- [<span data-ttu-id="45814-122">Get — Instrukcja</span><span class="sxs-lookup"><span data-stu-id="45814-122">Get Statement</span></span>](../statements/get-statement.md)
