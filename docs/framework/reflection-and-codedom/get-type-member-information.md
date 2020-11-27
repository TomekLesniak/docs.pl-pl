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
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a>Instrukcje: uzyskiwanie informacji o typie i elemencie członkowskim za pomocą odbicia

<xref:System.Reflection>Przestrzeń nazw zawiera wiele metod uzyskiwania informacji na temat typów i ich członków. W tym artykule przedstawiono jedną z tych metod <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> . Aby uzyskać dodatkowe informacje, zobacz [Omówienie odbicia](reflection.md).
  
## <a name="example"></a>Przykład

Poniższy przykład pobiera informacje o typie i elemencie członkowskim za pomocą odbicia:

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a>Zobacz też

- [Program z domenami aplikacji](../app-domains/application-domains.md#programming-with-application-domains)
- [Odbicie](reflection.md)
- [Korzystanie z domen aplikacji](../app-domains/use.md)
