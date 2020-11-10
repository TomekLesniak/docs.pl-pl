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
# <a name="syslib0009-the-authenticationmanager-authenticate-and-preauthenticate-methods-are-not-supported"></a><span data-ttu-id="4b94c-103">SYSLIB0009: metody uwierzytelniania i wstępnego uwierzytelnianiamanager nie są obsługiwane</span><span class="sxs-lookup"><span data-stu-id="4b94c-103">SYSLIB0009: The AuthenticationManager Authenticate and PreAuthenticate methods are not supported</span></span>

<span data-ttu-id="4b94c-104">Następujące interfejsy API są oznaczone jako przestarzałe, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="4b94c-104">The following APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="4b94c-105">Użycie tych interfejsów API generuje ostrzeżenie `SYSLIB0009` w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="4b94c-105">Use of these APIs generates warning `SYSLIB0009` at compile time.</span></span>

- <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType>
- <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType>

## <a name="suppress-the-warning"></a><span data-ttu-id="4b94c-106">Pomiń ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="4b94c-106">Suppress the warning</span></span>

<span data-ttu-id="4b94c-107">Jeśli nie możesz zmienić kodu, możesz pominąć ostrzeżenie za pomocą `#pragma` dyrektywy lub `<NoWarn>` Ustawienia projektu.</span><span class="sxs-lookup"><span data-stu-id="4b94c-107">If you cannot change your code, you can suppress the warning through a `#pragma` directive or a `<NoWarn>` project setting.</span></span> <span data-ttu-id="4b94c-108">Aby zapoznać się z przykładami, zobacz [pomijanie ostrzeżeń](syslib-obsoletions.md#suppress-warnings).</span><span class="sxs-lookup"><span data-stu-id="4b94c-108">For examples, see [Suppress warnings](syslib-obsoletions.md#suppress-warnings).</span></span>
