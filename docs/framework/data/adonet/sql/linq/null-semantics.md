---
title: Semantyka wartości Null
ms.date: 03/30/2017
ms.assetid: a97017ae-d634-4cf3-bbaf-054a528fd683
ms.openlocfilehash: 739ee95be45d7d64a4ad1678837b9706a533f07d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147544"
---
# <a name="null-semantics"></a><span data-ttu-id="93505-102">Semantyka wartości Null</span><span class="sxs-lookup"><span data-stu-id="93505-102">Null Semantics</span></span>

<span data-ttu-id="93505-103">Poniższa tabela zawiera linki do różnych części dokumentacji, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] w których `null` `Nothing` omówiono problemy (w Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="93505-103">The following table provides links to various parts of the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] documentation where `null` (`Nothing` in Visual Basic) issues are discussed.</span></span>  
  
|<span data-ttu-id="93505-104">Temat</span><span class="sxs-lookup"><span data-stu-id="93505-104">Topic</span></span>|<span data-ttu-id="93505-105">Opis</span><span class="sxs-lookup"><span data-stu-id="93505-105">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="93505-106">Niezgodność typu SQL CLR</span><span class="sxs-lookup"><span data-stu-id="93505-106">SQL-CLR Type Mismatches</span></span>](sql-clr-type-mismatches.md)|<span data-ttu-id="93505-107">Sekcja "semantyka wartości null" w tym temacie zawiera dyskusje na temat wartości logicznej SQL, a także dwustanowego środowiska uruchomieniowego języka wspólnego (CLR) <xref:System.Boolean> , literału `Nothing` (Visual Basic) i `null` (C#) oraz innych podobnych problemów.</span><span class="sxs-lookup"><span data-stu-id="93505-107">The "Null Semantics" section of this topic includes discussion of the three-state SQL Boolean versus the two-state common language runtime (CLR) <xref:System.Boolean>, the literal `Nothing` (Visual Basic) and `null` (C#), and other similar issues.</span></span>|  
|[<span data-ttu-id="93505-108">Translacja standardowego operatora zapytania</span><span class="sxs-lookup"><span data-stu-id="93505-108">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)|<span data-ttu-id="93505-109">Sekcja "semantyka wartości null" w tym temacie opisuje semantykę porównania wartości null w [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="93505-109">The "Null Semantics" section of this topic describes null comparison semantics in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>|  
|[<span data-ttu-id="93505-110">System.String, metody</span><span class="sxs-lookup"><span data-stu-id="93505-110">System.String Methods</span></span>](system-string-methods.md)|<span data-ttu-id="93505-111">Sekcja "różnice między platformą .NET" w tym temacie opisuje, jak zwracana wartość 0 z <xref:System.String.LastIndexOf%2A> może oznaczać, że ciąg ma wartość null lub że znaleziona pozycja wynosi 0.</span><span class="sxs-lookup"><span data-stu-id="93505-111">The "Differences from .NET" section of this topic describes how a return of 0 from <xref:System.String.LastIndexOf%2A> might mean either that the string is null or that the found position is 0.</span></span>|  
|[<span data-ttu-id="93505-112">Obliczanie sumy wartości w sekwencji numerycznej</span><span class="sxs-lookup"><span data-stu-id="93505-112">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)|<span data-ttu-id="93505-113">Opisuje sposób, <xref:System.Linq.Enumerable.Sum%2A> w jaki operator oblicza wartość `null` ( `Nothing` w Visual Basic) zamiast 0 dla sekwencji zawierającej tylko wartości null lub pustą sekwencję.</span><span class="sxs-lookup"><span data-stu-id="93505-113">Describes how the <xref:System.Linq.Enumerable.Sum%2A> operator evaluates to `null` (`Nothing` in Visual Basic) instead of 0 for a sequence that contains only nulls or for an empty sequence.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="93505-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="93505-114">See also</span></span>

- [<span data-ttu-id="93505-115">Typy danych i funkcje</span><span class="sxs-lookup"><span data-stu-id="93505-115">Data Types and Functions</span></span>](data-types-and-functions.md)
