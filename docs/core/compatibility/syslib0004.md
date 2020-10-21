---
title: Ostrzeżenie SYSLIB0004
description: Dowiedz się więcej o Obsoletions, które generują ostrzeżenie SYSLIB0004 w czasie kompilacji.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: ba7cd8a890a89000b241d286c9d8069ba1398849
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333348"
---
# <a name="syslib0004-the-constrained-execution-region-cer-feature-is-not-supported"></a><span data-ttu-id="c978f-103">SYSLIB0004: funkcja ograniczonego regionu wykonywania (CER) nie jest obsługiwana</span><span class="sxs-lookup"><span data-stu-id="c978f-103">SYSLIB0004: The constrained execution region (CER) feature is not supported</span></span>

<span data-ttu-id="c978f-104">Funkcja [ograniczone regiony wykonywania (CER)](../../framework/performance/constrained-execution-regions.md) jest obsługiwana tylko w .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c978f-104">The [Constrained execution regions (CER)](../../framework/performance/constrained-execution-regions.md) feature is supported only in .NET Framework.</span></span> <span data-ttu-id="c978f-105">W związku z tym różne interfejsy API związane z programem CER są oznaczane jako przestarzałe, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="c978f-105">As such, various CER-related APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="c978f-106">Użycie tych interfejsów API generuje ostrzeżenie `SYSLIB0004` w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="c978f-106">Using these APIs generates warning `SYSLIB0004` at compile time.</span></span>

<span data-ttu-id="c978f-107">Następujące interfejsy API związane z programem CER są przestarzałe:</span><span class="sxs-lookup"><span data-stu-id="c978f-107">The following CER-related APIs are obsolete:</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(System.Runtime.CompilerServices.RuntimeHelpers.TryCode,System.Runtime.CompilerServices.RuntimeHelpers.CleanupCode,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegionsNoOP?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareContractedDelegate(System.Delegate)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ProbeForSufficientStack?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Cer?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Consistency?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute?displayProperty=nameWithType>

## <a name="see-also"></a><span data-ttu-id="c978f-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c978f-108">See also</span></span>

- [<span data-ttu-id="c978f-109">Ograniczone regiony wykonywania</span><span class="sxs-lookup"><span data-stu-id="c978f-109">Constrained execution regions</span></span>](../../framework/performance/constrained-execution-regions.md)
