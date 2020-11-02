---
title: Współdziałanie modelu COM w programie .NET
description: Dowiedz się, jak współpracować z bibliotekami COM w programie .NET.
ms.date: 07/11/2019
ms.openlocfilehash: 9c436019c800a68ffe2cd5011e14bd804384afaa
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2020
ms.locfileid: "93187778"
---
# <a name="com-interop-in-net"></a><span data-ttu-id="509d5-103">Współdziałanie modelu COM w programie .NET</span><span class="sxs-lookup"><span data-stu-id="509d5-103">COM Interop in .NET</span></span>

<span data-ttu-id="509d5-104">Component Object Model (COM) umożliwia obiektowi uwidocznienie jego funkcjonalności innym składnikom i hostowanie aplikacji na platformach Windows.</span><span class="sxs-lookup"><span data-stu-id="509d5-104">The Component Object Model (COM) lets an object expose its functionality to other components and to host applications on Windows platforms.</span></span> <span data-ttu-id="509d5-105">Aby ułatwić użytkownikom współdziałanie z istniejącymi bazami kodu, .NET Framework zawsze zapewniała silną obsługę współpracy z bibliotekami COM.</span><span class="sxs-lookup"><span data-stu-id="509d5-105">To help enable users to interoperate with their existing code bases, .NET Framework has always provided strong support for interoperating with COM libraries.</span></span> <span data-ttu-id="509d5-106">W przypadku platformy .NET Core 3,0 w systemie Windows dodano dużą część tego wsparcia do programu .NET Core.</span><span class="sxs-lookup"><span data-stu-id="509d5-106">In .NET Core 3.0, a large portion of this support has been added to .NET Core on Windows.</span></span> <span data-ttu-id="509d5-107">W tej dokumentacji wyjaśniono, jak działają wspólne technologie międzyoperacyjności modelu COM oraz jak można je wykorzystać do współpracy z istniejącymi bibliotekami COM.</span><span class="sxs-lookup"><span data-stu-id="509d5-107">The documentation here explains how the common COM interop technologies work and how you can utilize them to interoperate with your existing COM libraries.</span></span>

- [<span data-ttu-id="509d5-108">Otoki COM</span><span class="sxs-lookup"><span data-stu-id="509d5-108">COM Wrappers</span></span>](./com-wrappers.md)
- [<span data-ttu-id="509d5-109">Wywoływane otoki COM</span><span class="sxs-lookup"><span data-stu-id="509d5-109">COM Callable Wrappers</span></span>](./com-callable-wrapper.md)
- [<span data-ttu-id="509d5-110">Wywoływane otoki środowiska uruchomieniowego</span><span class="sxs-lookup"><span data-stu-id="509d5-110">Runtime Callable Wrappers</span></span>](./runtime-callable-wrapper.md)
- [<span data-ttu-id="509d5-111">Kwalifikowanie typów .NET do współdziałania z modelem COM</span><span class="sxs-lookup"><span data-stu-id="509d5-111">Qualifying .NET Types for COM Interoperation</span></span>](./qualify-net-types-for-interoperation.md)
