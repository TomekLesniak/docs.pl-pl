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
# <a name="syslib0010-unsupported-remoting-apis"></a>SYSLIB0010: nieobsługiwane interfejsy API komunikacji zdalnej

[Komunikacja zdalna .NET](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) to Starsza technologia, a infrastruktura istnieje tylko w .NET Framework. Następujące interfejsy API związane z usługami zdalnymi są oznaczone jako przestarzałe, począwszy od platformy .NET 5,0. Użycie ich w kodzie generuje ostrzeżenie `SYSLIB0010` w czasie kompilacji.

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType>

## <a name="workaround"></a>Obejście

Należy rozważyć użycie usług REST lub opartych na protokole HTTP w celu komunikowania się z obiektami w innych aplikacjach lub na różnych komputerach. Aby uzyskać więcej informacji, zobacz [technologie .NET Framework niedostępne w programie .NET Core](../porting/net-framework-tech-unavailable.md).

## <a name="see-also"></a>Zobacz też

- [Komunikacja zdalna .NET](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))
