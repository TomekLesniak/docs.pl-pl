---
title: Dostęp do ciągów opartych na protokole zero zamiast jednego
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: 91d3fb9d7bfdf3d5af27fc6499583640946a802f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072291"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="df788-102">Dostęp do ciągów opartych na zerze i na jedynce w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df788-102">Zero-based vs. One-based String Access in Visual Basic</span></span>

<span data-ttu-id="df788-103">W tym temacie porównano, jak Visual Basic i .NET Framework zapewniają dostęp do znaków w ciągu.</span><span class="sxs-lookup"><span data-stu-id="df788-103">This topic compares how Visual Basic and the .NET Framework provide access to the characters in a string.</span></span> <span data-ttu-id="df788-104">.NET Framework zawsze zapewnia od zera dostęp do znaków w ciągu, podczas gdy Visual Basic zapewnia dostęp oparty na zerowym i jednokrotnym, w zależności od funkcji.</span><span class="sxs-lookup"><span data-stu-id="df788-104">The .NET Framework always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="df788-105">Oparte na jednym</span><span class="sxs-lookup"><span data-stu-id="df788-105">One-Based</span></span>  

 <span data-ttu-id="df788-106">Przykład funkcji Visual Basic opartej na jednym miejscu, należy wziąć pod uwagę `Mid` funkcję.</span><span class="sxs-lookup"><span data-stu-id="df788-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="df788-107">Przyjmuje argument, który wskazuje położenie znaku, w którym rozpocznie się podciąg, zaczynając od pozycji 1.</span><span class="sxs-lookup"><span data-stu-id="df788-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="df788-108">Metoda .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> przyjmuje indeks znaku w ciągu, w którym ma zostać uruchomiony podciąg, zaczynając od pozycji 0.</span><span class="sxs-lookup"><span data-stu-id="df788-108">The .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="df788-109">W takim przypadku, jeśli masz ciąg "ABCDe", poszczególne znaki są numerowane 1, 2, 3, 4, 5 do użycia z `Mid` funkcją, ale 0, 1, 2, 3, 4 do użycia z <xref:System.String.Substring%2A?displayProperty=nameWithType> metodą.</span><span class="sxs-lookup"><span data-stu-id="df788-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="df788-110">W oparciu o zero</span><span class="sxs-lookup"><span data-stu-id="df788-110">Zero-Based</span></span>  

 <span data-ttu-id="df788-111">Przykład funkcji Visual Basic opartej na zero, należy wziąć pod uwagę `Split` funkcję.</span><span class="sxs-lookup"><span data-stu-id="df788-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="df788-112">Dzieli ciąg i zwraca tablicę zawierającą podciągi.</span><span class="sxs-lookup"><span data-stu-id="df788-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="df788-113">Metoda .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> dzieli również ciąg i zwraca tablicę zawierającą podciągi.</span><span class="sxs-lookup"><span data-stu-id="df788-113">The .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="df788-114">Ponieważ `Split` Funkcja i <xref:System.String.Split%2A> metoda zwracają .NET Framework tablic, muszą one być oparte na zero.</span><span class="sxs-lookup"><span data-stu-id="df788-114">Because the `Split` function and <xref:System.String.Split%2A> method return .NET Framework arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df788-115">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="df788-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="df788-116">Wprowadzenie do ciągów w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="df788-116">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
