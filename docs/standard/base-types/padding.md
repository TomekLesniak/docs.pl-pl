---
title: Uzupełnianie ciągów w programie .NET
description: Dowiedz się, jak uzupełniać ciągi w programie .NET. Użyj metod String. PadLeft i String. PadRight, aby dodać znaki wiodące lub końcowe w celu osiągnięcia określonej całkowitej długości.
ms.date: 03/15/2018
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strings [.NET], padding
- white space
- PadRight method
- PadLeft method
- padding strings
ms.assetid: 84a9f142-3244-4c90-ba02-21af9bbaff71
ms.openlocfilehash: b8dbea862acb87c1db2d23b11bac597eaa27d6b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683787"
---
# <a name="padding-strings-in-net"></a><span data-ttu-id="7f6e2-104">Uzupełnianie ciągów w programie .NET</span><span class="sxs-lookup"><span data-stu-id="7f6e2-104">Padding Strings in .NET</span></span>

<span data-ttu-id="7f6e2-105">Użyj jednej z następujących <xref:System.String> metod, aby utworzyć nowy ciąg, który składa się z oryginalnego ciągu, który jest uzupełniony znakami początkowymi lub końcowymi do określonej całkowitej długości.</span><span class="sxs-lookup"><span data-stu-id="7f6e2-105">Use one of the following <xref:System.String> methods to create a new string that consists of an original string that is padded with leading or trailing characters to a specified total length.</span></span> <span data-ttu-id="7f6e2-106">Znak uzupełniania może być spacją lub określonym znakiem.</span><span class="sxs-lookup"><span data-stu-id="7f6e2-106">The padding character can be a space or a specified character.</span></span> <span data-ttu-id="7f6e2-107">Ciąg wyników wydaje się być wyrównany do prawej lub wyrównany do lewej.</span><span class="sxs-lookup"><span data-stu-id="7f6e2-107">The resulting string appears to be either right-aligned or left-aligned.</span></span> <span data-ttu-id="7f6e2-108">Jeśli pierwotna długość ciągu jest już równa lub większa od żądanej całkowitej długości, metody uzupełniania zwracają oryginalny ciąg niezmieniony; Aby uzyskać więcej informacji, zobacz sekcje **zwraca** dwa przeciążenia <xref:System.String.PadLeft%2A?displayProperty=nameWithType> <xref:System.String.PadRight%2A?displayProperty=nameWithType> metod i.</span><span class="sxs-lookup"><span data-stu-id="7f6e2-108">If the original string's length is already equal to or greater than the desired total length, the padding methods return the original string unchanged; for more information, see the **Returns** sections of the two overloads of the <xref:System.String.PadLeft%2A?displayProperty=nameWithType> and <xref:System.String.PadRight%2A?displayProperty=nameWithType> methods.</span></span>
  
|<span data-ttu-id="7f6e2-109">Nazwa metody</span><span class="sxs-lookup"><span data-stu-id="7f6e2-109">Method name</span></span>|<span data-ttu-id="7f6e2-110">Zastosowanie</span><span class="sxs-lookup"><span data-stu-id="7f6e2-110">Use</span></span>|  
|-----------------|---------|  
|<xref:System.String.PadLeft%2A?displayProperty=nameWithType>|<span data-ttu-id="7f6e2-111">Tworzy w postaci ciągu znaki wiodące z określoną łączną długością.</span><span class="sxs-lookup"><span data-stu-id="7f6e2-111">Pads a string with leading characters to a specified total length.</span></span>|  
|<xref:System.String.PadRight%2A?displayProperty=nameWithType>|<span data-ttu-id="7f6e2-112">Tworzy w postaci ciągu znaki końcowe z określoną całkowitą długością.</span><span class="sxs-lookup"><span data-stu-id="7f6e2-112">Pads a string with trailing characters to a specified total length.</span></span>|  
  
## <a name="padleft"></a><span data-ttu-id="7f6e2-113">PadLeft</span><span class="sxs-lookup"><span data-stu-id="7f6e2-113">PadLeft</span></span>  

 <span data-ttu-id="7f6e2-114"><xref:System.String.PadLeft%2A?displayProperty=nameWithType>Metoda tworzy nowy ciąg przez złączenie wystarczającej liczby wiodących znaków pad do oryginalnego ciągu, aby osiągnąć określoną łączną długość.</span><span class="sxs-lookup"><span data-stu-id="7f6e2-114">The <xref:System.String.PadLeft%2A?displayProperty=nameWithType> method creates a new string by concatenating enough leading pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="7f6e2-115"><xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType>Metoda używa odstępu jako znaku uzupełniania, a <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> Metoda umożliwia określenie własnego znaku uzupełniania.</span><span class="sxs-lookup"><span data-stu-id="7f6e2-115">The <xref:System.String.PadLeft%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadLeft%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="7f6e2-116">Poniższy przykład kodu używa metody, <xref:System.String.PadLeft%2A> Aby utworzyć nowy ciąg o długości dwudziestu znaków.</span><span class="sxs-lookup"><span data-stu-id="7f6e2-116">The following code example uses the <xref:System.String.PadLeft%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="7f6e2-117">W przykładzie zostanie wyświetlony komunikat " `--------Hello World!` " w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="7f6e2-117">The example displays "`--------Hello World!`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#3)]
 [!code-csharp[Conceptual.String.BasicOps#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#3)]
 [!code-vb[Conceptual.String.BasicOps#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#3)]  
  
## <a name="padright"></a><span data-ttu-id="7f6e2-118">PadRight</span><span class="sxs-lookup"><span data-stu-id="7f6e2-118">PadRight</span></span>  

 <span data-ttu-id="7f6e2-119"><xref:System.String.PadRight%2A?displayProperty=nameWithType>Metoda tworzy nowy ciąg, łącząc wystarczającą liczbę końcową znaków uzupełniających do oryginalnego ciągu, aby osiągnąć określoną łączną długość.</span><span class="sxs-lookup"><span data-stu-id="7f6e2-119">The <xref:System.String.PadRight%2A?displayProperty=nameWithType> method creates a new string by concatenating enough trailing pad characters to an original string to achieve a specified total length.</span></span> <span data-ttu-id="7f6e2-120"><xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType>Metoda używa odstępu jako znaku uzupełniania, a <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> Metoda umożliwia określenie własnego znaku uzupełniania.</span><span class="sxs-lookup"><span data-stu-id="7f6e2-120">The <xref:System.String.PadRight%28System.Int32%29?displayProperty=nameWithType> method uses white space as the padding character and the <xref:System.String.PadRight%28System.Int32%2CSystem.Char%29?displayProperty=nameWithType> method enables you to specify your own padding character.</span></span>  
  
 <span data-ttu-id="7f6e2-121">Poniższy przykład kodu używa metody, <xref:System.String.PadRight%2A> Aby utworzyć nowy ciąg o długości dwudziestu znaków.</span><span class="sxs-lookup"><span data-stu-id="7f6e2-121">The following code example uses the <xref:System.String.PadRight%2A> method to create a new string that is twenty characters long.</span></span> <span data-ttu-id="7f6e2-122">W przykładzie zostanie wyświetlony komunikat " `Hello World!--------` " w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="7f6e2-122">The example displays "`Hello World!--------`" to the console.</span></span>  
  
 [!code-cpp[Conceptual.String.BasicOps#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.basicops/cpp/padding.cpp#4)]
 [!code-csharp[Conceptual.String.BasicOps#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/padding.cs#4)]
 [!code-vb[Conceptual.String.BasicOps#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/padding.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="7f6e2-123">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7f6e2-123">See also</span></span>

- [<span data-ttu-id="7f6e2-124">Podstawowe operacje na ciągach</span><span class="sxs-lookup"><span data-stu-id="7f6e2-124">Basic String Operations</span></span>](basic-string-operations.md)
