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
# <a name="syslib0008-createpdbgenerator-is-not-supported"></a>SYSLIB0008: CreatePdbGenerator nie jest obsługiwana

<xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType>Interfejs API jest oznaczony jako przestarzały, począwszy od platformy .net 5,0. Użycie tego interfejsu API generuje ostrzeżenie `SYSLIB0008` w czasie kompilacji.

## <a name="suppress-the-warning"></a>Pomiń ostrzeżenie

Jeśli nie możesz zmienić kodu, możesz pominąć ostrzeżenie za pomocą `#pragma` dyrektywy lub `<NoWarn>` Ustawienia projektu. Aby zapoznać się z przykładami, zobacz [pomijanie ostrzeżeń](syslib-obsoletions.md#suppress-warnings).
