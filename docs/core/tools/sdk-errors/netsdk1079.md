---
title: 'NETSDK1079: pakiet Microsoft. AspNetCore. All nie jest obsługiwany w przypadku programu .NET Core 3,0 lub nowszego.'
description: Jak rozwiązać migrację do programu Microsoft. AspNetCore. App
author: dsplaisted
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1079
ms.openlocfilehash: e0b7aba909dbd2931f755238a2de2418d294751d
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445781"
---
# <a name="netsdk1079-the-microsoftaspnetcoreall-package-is-not-supported-when-targeting-net-core-30-or-higher"></a>NETSDK1079: pakiet Microsoft. AspNetCore. All nie jest obsługiwany w przypadku programu .NET Core 3,0 lub nowszego.

**Ten artykuł ma zastosowanie do:** ✔️ zestaw .NET Core SDK 3.1.100 i nowszych wersjach

Ten komunikat o błędzie może pojawić się w następujący sposób:

- Należy przekierować projekt ASP.NET Core z platformy .NET Core 2,2 lub starszej do programu .NET Core 3,0 lub nowszego.
- Projekt używa pakietu Microsoft. AspNetCore. ALL.

Usuń `PackageReference` dla elementu Microsoft. AspNetCore. ALL.  Może być również konieczne dodanie odwołań pakietu dla pakietów, do których odwołuje się element Microsoft. AspNetCore. All, ale nie są uwzględnione w infrastrukturze udostępnionej ASP.NET Core.  Te pakiety są wymienione tutaj: [Migrowanie z Microsoft. AspNetCore. All do Microsoft. AspNetCore. app](/aspnet/core/fundamentals/metapackage#migrating-from-microsoftaspnetcoreall-to-microsoftaspnetcoreapp).

Zobacz również [Migrowanie z ASP.NET Core 2,2 do 3,0](/aspnet/core/migration/22-to-30)
