---
title: Ostrzeżenie SYSLIB0012
description: Dowiedz się więcej o Obsoletions, które generują ostrzeżenie SYSLIB0012 w czasie kompilacji.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: dc139d5c5cb6d6a34d161147b350b3324d15117e
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440585"
---
# <a name="syslib0012-assemblycodebase-and-assemblyescapedcodebase-are-obsolete"></a>SYSLIB0012: zestaw. CodeBase i Assembly. EscapedCodeBase są przestarzałe

Następujące interfejsy API są oznaczone jako przestarzałe, począwszy od platformy .NET 5,0. Użycie ich w kodzie generuje ostrzeżenie `SYSLIB0012` w czasie kompilacji.

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>

## <a name="workarounds"></a>Obejścia

Zamiast tego użyj polecenia cmdlet <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>.

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]
