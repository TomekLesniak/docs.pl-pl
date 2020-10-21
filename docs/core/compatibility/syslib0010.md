---
title: Ostrzeżenie SYSLIB0010
description: Dowiedz się więcej o Obsoletions, które generują ostrzeżenie SYSLIB0010 w czasie kompilacji.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: dcd331aa5c68381ea29848bc54ee4b1a5e75330d
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333331"
---
# <a name="syslib0010-unsupported-remoting-apis"></a><span data-ttu-id="b8d3c-103">SYSLIB0010: nieobsługiwane interfejsy API komunikacji zdalnej</span><span class="sxs-lookup"><span data-stu-id="b8d3c-103">SYSLIB0010: Unsupported remoting APIs</span></span>

<span data-ttu-id="b8d3c-104">[Komunikacja zdalna .NET](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) to Starsza technologia, a infrastruktura istnieje tylko w .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b8d3c-104">[.NET remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) is a legacy technology, and the infrastructure exists only in .NET Framework.</span></span> <span data-ttu-id="b8d3c-105">Następujące interfejsy API związane z usługami zdalnymi są oznaczone jako przestarzałe, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="b8d3c-105">The following remoting-related APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="b8d3c-106">Użycie ich w kodzie generuje ostrzeżenie `SYSLIB0010` w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="b8d3c-106">Using them in code generates warning `SYSLIB0010` at compile time.</span></span>

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType>

## <a name="workaround"></a><span data-ttu-id="b8d3c-107">Obejście</span><span class="sxs-lookup"><span data-stu-id="b8d3c-107">Workaround</span></span>

<span data-ttu-id="b8d3c-108">Należy rozważyć użycie usług REST lub opartych na protokole HTTP w celu komunikowania się z obiektami w innych aplikacjach lub na różnych komputerach.</span><span class="sxs-lookup"><span data-stu-id="b8d3c-108">Consider using WCF or HTTP-based REST services to communicate with objects in other applications or across machines.</span></span> <span data-ttu-id="b8d3c-109">Aby uzyskać więcej informacji, zobacz [technologie .NET Framework niedostępne w programie .NET Core](../porting/net-framework-tech-unavailable.md).</span><span class="sxs-lookup"><span data-stu-id="b8d3c-109">For more information, see [.NET Framework technologies unavailable on .NET Core](../porting/net-framework-tech-unavailable.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8d3c-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="b8d3c-110">See also</span></span>

- <span data-ttu-id="b8d3c-111">[Komunikacja zdalna .NET](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))</span><span class="sxs-lookup"><span data-stu-id="b8d3c-111">[.NET remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))</span></span>
