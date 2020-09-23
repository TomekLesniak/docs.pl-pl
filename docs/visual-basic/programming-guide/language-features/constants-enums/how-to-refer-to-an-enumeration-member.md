---
title: 'Porady: odwoływanie się do elementu członkowskiego wyliczenia'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: d1b239e7d6be3ebf1e64d6589a4cc14dce8946f5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095671"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a><span data-ttu-id="9ac0e-102">Porady: odwoływanie się do elementu członkowskiego wyliczenia (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ac0e-102">How to: Refer to an Enumeration Member (Visual Basic)</span></span>

<span data-ttu-id="9ac0e-103">Wyliczenia zapewniają wygodny sposób pracy z zestawami powiązanych stałych i kojarzenia wartości stałych z nazwami.</span><span class="sxs-lookup"><span data-stu-id="9ac0e-103">Enumerations provide a convenient way to work with sets of related constants and to associate constant values with names.</span></span> <span data-ttu-id="9ac0e-104">Na przykład można zadeklarować Wyliczenie dla zestawu stałych całkowitych skojarzonych z dniami tygodnia, a następnie użyć nazw dni, a nie ich wartości całkowitych w kodzie.</span><span class="sxs-lookup"><span data-stu-id="9ac0e-104">For example, you can declare an enumeration for a set of integer constants associated with the days of the week, and then use the names of the days rather than their integer values in your code.</span></span>  
  
 <span data-ttu-id="9ac0e-105">Można uniknąć używania w pełni kwalifikowanych nazw przy użyciu `Imports` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="9ac0e-105">You can avoid using fully qualified names with the `Imports` statement.</span></span> <span data-ttu-id="9ac0e-106">Aby uzyskać więcej informacji, zobacz [wyliczenia i kwalifikowanie nazw](enumerations-and-name-qualification.md).</span><span class="sxs-lookup"><span data-stu-id="9ac0e-106">For more information, see [Enumerations and Name Qualification](enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-refer-to-an-enumeration-member"></a><span data-ttu-id="9ac0e-107">Aby odwołać się do elementu członkowskiego wyliczenia</span><span class="sxs-lookup"><span data-stu-id="9ac0e-107">To refer to an enumeration member</span></span>  
  
- <span data-ttu-id="9ac0e-108">Zakwalifikuj nazwę elementu członkowskiego z wyliczeniem.</span><span class="sxs-lookup"><span data-stu-id="9ac0e-108">Qualify the member name with the enumeration.</span></span> <span data-ttu-id="9ac0e-109">Na przykład poniższy przykład przypisuje `Saturday` element członkowski `FirstDayOfWeek` wyliczenia do zmiennej `DayValue` .</span><span class="sxs-lookup"><span data-stu-id="9ac0e-109">For example, the following example assigns the `Saturday` member of the `FirstDayOfWeek` enumeration to the variable `DayValue`.</span></span>  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="9ac0e-110">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9ac0e-110">See also</span></span>

- [<span data-ttu-id="9ac0e-111">Instrukcje: deklarowanie wyliczenia</span><span class="sxs-lookup"><span data-stu-id="9ac0e-111">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="9ac0e-112">Wyliczenie i kwantyfikacja nazwy</span><span class="sxs-lookup"><span data-stu-id="9ac0e-112">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="9ac0e-113">Porady: iterowanie za pomocą wyliczania w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9ac0e-113">How to: Iterate Through An Enumeration in Visual Basic</span></span>](how-to-iterate-through-an-enumeration.md)
- [<span data-ttu-id="9ac0e-114">Instrukcje: określanie ciągu skojarzonego z wartością wyliczenia</span><span class="sxs-lookup"><span data-stu-id="9ac0e-114">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="9ac0e-115">Kiedy stosować wyliczanie</span><span class="sxs-lookup"><span data-stu-id="9ac0e-115">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
