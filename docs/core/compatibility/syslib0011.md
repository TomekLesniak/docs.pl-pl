---
title: Ostrzeżenie SYSLIB0011
description: Dowiedz się więcej o Obsoletions, które generują ostrzeżenie SYSLIB0011 w czasie kompilacji.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 99cdd9f5335f71eb9325039891db17972fb48532
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685009"
---
# <a name="syslib0011-binaryformatter-serialization-is-obsolete"></a><span data-ttu-id="e8c1b-103">SYSLIB0011: serializacja BinaryFormatter jest przestarzała</span><span class="sxs-lookup"><span data-stu-id="e8c1b-103">SYSLIB0011: BinaryFormatter serialization is obsolete</span></span>

<span data-ttu-id="e8c1b-104">Ze względu na [luki w zabezpieczeniach](../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> następujące interfejsy API są oznaczane jako przestarzałe, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="e8c1b-104">Due to [security vulnerabilities](../../standard/serialization/binaryformatter-security-guide.md#binaryformatter-security-vulnerabilities) in <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, the following APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="e8c1b-105">Użycie ich w kodzie generuje ostrzeżenie `SYSLIB0011` w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="e8c1b-105">Using them in code generates warning `SYSLIB0011` at compile time.</span></span>

- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.Formatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.Serialization.IFormatter.Deserialize(System.IO.Stream)?displayProperty=nameWithType>

## <a name="workarounds"></a><span data-ttu-id="e8c1b-106">Obejścia</span><span class="sxs-lookup"><span data-stu-id="e8c1b-106">Workarounds</span></span>

<span data-ttu-id="e8c1b-107">Rozważ użycie <xref:System.Text.Json.JsonSerializer> lub <xref:System.Xml.Serialization.XmlSerializer> zamiast <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> .</span><span class="sxs-lookup"><span data-stu-id="e8c1b-107">Consider using <xref:System.Text.Json.JsonSerializer> or <xref:System.Xml.Serialization.XmlSerializer> instead of <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>.</span></span>

<span data-ttu-id="e8c1b-108">Aby uzyskać więcej informacji na temat zalecanych akcji, zobacz [Rozwiązywanie problemów z BinaryFormatter obsoletion i wyłączanie](https://aka.ms/binaryformatter).</span><span class="sxs-lookup"><span data-stu-id="e8c1b-108">For more information about recommended actions, see [Resolving BinaryFormatter obsoletion and disablement errors](https://aka.ms/binaryformatter).</span></span>

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a><span data-ttu-id="e8c1b-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="e8c1b-109">See also</span></span>

- [<span data-ttu-id="e8c1b-110">Rozwiązywanie błędów BinaryFormatter i wyłączania</span><span class="sxs-lookup"><span data-stu-id="e8c1b-110">Resolving BinaryFormatter obsoletion and disablement errors</span></span>](https://aka.ms/binaryformatter)
- [<span data-ttu-id="e8c1b-111">Metody serializacji BinaryFormatter są przestarzałe i zabronione w aplikacjach ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e8c1b-111">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](core-libraries/5.0/binaryformatter-serialization-obsolete.md)
