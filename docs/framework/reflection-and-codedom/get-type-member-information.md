---
title: 'Instrukcje: uzyskiwanie informacji o typie i elemencie członkowskim za pomocą odbicia'
description: Dowiedz się, jak uzyskać informacje o typie i elemencie członkowskim za pomocą odbicia przy użyciu przestrzeni nazw System. odbicie.
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: 771917bb2ae5cae56c775ae23119d5eda9701df1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266327"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a><span data-ttu-id="2097e-103">Instrukcje: uzyskiwanie informacji o typie i elemencie członkowskim za pomocą odbicia</span><span class="sxs-lookup"><span data-stu-id="2097e-103">How to: Get type and member information by using reflection</span></span>

<span data-ttu-id="2097e-104"><xref:System.Reflection>Przestrzeń nazw zawiera wiele metod uzyskiwania informacji na temat typów i ich członków.</span><span class="sxs-lookup"><span data-stu-id="2097e-104">The <xref:System.Reflection> namespace contains many methods for obtaining information about types and their members.</span></span> <span data-ttu-id="2097e-105">W tym artykule przedstawiono jedną z tych metod <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="2097e-105">This article demonstrates one of these methods, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2097e-106">Aby uzyskać dodatkowe informacje, zobacz [Omówienie odbicia](reflection.md).</span><span class="sxs-lookup"><span data-stu-id="2097e-106">For additional information, see [Reflection overview](reflection.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="2097e-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="2097e-107">Example</span></span>

<span data-ttu-id="2097e-108">Poniższy przykład pobiera informacje o typie i elemencie członkowskim za pomocą odbicia:</span><span class="sxs-lookup"><span data-stu-id="2097e-108">The following example obtains type and member information by using reflection:</span></span>

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a><span data-ttu-id="2097e-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2097e-109">See also</span></span>

- [<span data-ttu-id="2097e-110">Program z domenami aplikacji</span><span class="sxs-lookup"><span data-stu-id="2097e-110">Program with application domains</span></span>](../app-domains/application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="2097e-111">Odbicie</span><span class="sxs-lookup"><span data-stu-id="2097e-111">Reflection</span></span>](reflection.md)
- [<span data-ttu-id="2097e-112">Korzystanie z domen aplikacji</span><span class="sxs-lookup"><span data-stu-id="2097e-112">Use application domains</span></span>](../app-domains/use.md)
