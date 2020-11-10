---
title: Ostrzeżenie SYSLIB0008
description: Dowiedz się więcej na temat obsoletion, który generuje ostrzeżenie SYSLIB0008 w czasie kompilacji.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 22ac5b4c5f57ec3f92585ee8d1f8cf278a15dbb0
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440598"
---
# <a name="syslib0008-createpdbgenerator-is-not-supported"></a><span data-ttu-id="896cd-103">SYSLIB0008: CreatePdbGenerator nie jest obsługiwana</span><span class="sxs-lookup"><span data-stu-id="896cd-103">SYSLIB0008: CreatePdbGenerator is not supported</span></span>

<span data-ttu-id="896cd-104"><xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType>Interfejs API jest oznaczony jako przestarzały, począwszy od platformy .net 5,0.</span><span class="sxs-lookup"><span data-stu-id="896cd-104">The <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> API is marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="896cd-105">Użycie tego interfejsu API generuje ostrzeżenie `SYSLIB0008` w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="896cd-105">Using this API generates warning `SYSLIB0008` at compile time.</span></span>

## <a name="suppress-the-warning"></a><span data-ttu-id="896cd-106">Pomiń ostrzeżenie</span><span class="sxs-lookup"><span data-stu-id="896cd-106">Suppress the warning</span></span>

<span data-ttu-id="896cd-107">Jeśli nie możesz zmienić kodu, możesz pominąć ostrzeżenie za pomocą `#pragma` dyrektywy lub `<NoWarn>` Ustawienia projektu.</span><span class="sxs-lookup"><span data-stu-id="896cd-107">If you cannot change your code, you can suppress the warning through a `#pragma` directive or a `<NoWarn>` project setting.</span></span> <span data-ttu-id="896cd-108">Aby zapoznać się z przykładami, zobacz [pomijanie ostrzeżeń](syslib-obsoletions.md#suppress-warnings).</span><span class="sxs-lookup"><span data-stu-id="896cd-108">For examples, see [Suppress warnings](syslib-obsoletions.md#suppress-warnings).</span></span>
