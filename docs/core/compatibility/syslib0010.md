---
title: Ostrzeżenie SYSLIB0010
description: Dowiedz się więcej o Obsoletions, które generują ostrzeżenie SYSLIB0010 w czasie kompilacji.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 824423d58802d4a286bfed98422341097985990f
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440611"
---
# <a name="syslib0010-unsupported-remoting-apis"></a>SYSLIB0010: nieobsługiwane interfejsy API komunikacji zdalnej

[Komunikacja zdalna .NET](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) to Starsza technologia, a infrastruktura istnieje tylko w .NET Framework. Następujące interfejsy API związane z usługami zdalnymi są oznaczone jako przestarzałe, począwszy od platformy .NET 5,0. Użycie ich w kodzie generuje ostrzeżenie `SYSLIB0010` w czasie kompilacji.

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType>

## <a name="workarounds"></a>Obejścia

Należy rozważyć użycie usług REST lub opartych na protokole HTTP w celu komunikowania się z obiektami w innych aplikacjach lub na różnych komputerach. Aby uzyskać więcej informacji, zobacz [technologie .NET Framework niedostępne w programie .NET Core](../porting/net-framework-tech-unavailable.md).

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>Zobacz też

- [Komunikacja zdalna .NET](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))
