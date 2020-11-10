---
title: Ostrzeżenie SYSLIB0009
description: Dowiedz się więcej o Obsoletions, które generują ostrzeżenie SYSLIB0009 w czasie kompilacji.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 47b4f595a54800370da90f61d838c665df8b6091
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439979"
---
# <a name="syslib0009-the-authenticationmanager-authenticate-and-preauthenticate-methods-are-not-supported"></a>SYSLIB0009: metody uwierzytelniania i wstępnego uwierzytelnianiamanager nie są obsługiwane

Następujące interfejsy API są oznaczone jako przestarzałe, począwszy od platformy .NET 5,0. Użycie tych interfejsów API generuje ostrzeżenie `SYSLIB0009` w czasie kompilacji.

- <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType>
- <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType>

## <a name="suppress-the-warning"></a>Pomiń ostrzeżenie

Jeśli nie możesz zmienić kodu, możesz pominąć ostrzeżenie za pomocą `#pragma` dyrektywy lub `<NoWarn>` Ustawienia projektu. Aby zapoznać się z przykładami, zobacz [pomijanie ostrzeżeń](syslib-obsoletions.md#suppress-warnings).
