---
title: Przestarzałe funkcje w programie .NET 5 lub nowszym
description: Dowiedz się więcej na temat interfejsów API, które są oznaczone jako przestarzałe w programie .NET 5,0 i nowszych wersjach, które generują ostrzeżenia kompilatora SYSLIB.
ms.date: 10/20/2020
ms.openlocfilehash: 13f5fb10cfe693ed621b3f45fc22e024875890c8
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333355"
---
# <a name="obsolete-features-in-net-5"></a><span data-ttu-id="b5327-103">Przestarzałe funkcje w programie .NET 5</span><span class="sxs-lookup"><span data-stu-id="b5327-103">Obsolete features in .NET 5</span></span>

<span data-ttu-id="b5327-104">Począwszy od platformy .NET 5,0, niektóre interfejsy API, które są nowo oznaczone jako przestarzałe, używają dwóch nowych właściwości w programie <xref:System.ObsoleteAttribute> .</span><span class="sxs-lookup"><span data-stu-id="b5327-104">Starting in .NET 5.0, some APIs that are newly marked as obsolete make use of two new properties on <xref:System.ObsoleteAttribute>.</span></span>

- <span data-ttu-id="b5327-105"><xref:System.ObsoleteAttribute.DiagnosticId?displayProperty=nameWithType>Właściwość nakazuje kompilatorowi generowanie ostrzeżeń kompilacji przy użyciu NIESTANDARDOWEGO identyfikatora diagnostyki.</span><span class="sxs-lookup"><span data-stu-id="b5327-105">The <xref:System.ObsoleteAttribute.DiagnosticId?displayProperty=nameWithType> property tells the compiler to generate build warnings using a custom diagnostic ID.</span></span> <span data-ttu-id="b5327-106">Identyfikator niestandardowy pozwala na Pomijanie ostrzeżenia obsoletion, w odniesieniu do siebie i niezależnie od siebie.</span><span class="sxs-lookup"><span data-stu-id="b5327-106">The custom ID allows for obsoletion warning to be suppressed specifically and separately from one another.</span></span> <span data-ttu-id="b5327-107">W przypadku platformy .NET 5 i Obsoletions format niestandardowego identyfikatora diagnostyki to `SYSLIBxxxx` .</span><span class="sxs-lookup"><span data-stu-id="b5327-107">In the case of the .NET 5+ obsoletions, the format for the custom diagnostic ID is `SYSLIBxxxx`.</span></span>

- <span data-ttu-id="b5327-108"><xref:System.ObsoleteAttribute.UrlFormat?displayProperty=nameWithType>Właściwość nakazuje kompilatorowi dołączenie linku adresu URL, aby dowiedzieć się więcej na temat obsoletion.</span><span class="sxs-lookup"><span data-stu-id="b5327-108">The <xref:System.ObsoleteAttribute.UrlFormat?displayProperty=nameWithType> property tells the compiler to include a URL link to learn more about the obsoletion.</span></span>

<span data-ttu-id="b5327-109">Jeśli występują ostrzeżenia lub błędy kompilacji z powodu użycia przestarzałego interfejsu API, postępuj zgodnie ze szczegółowymi wskazówkami dotyczącymi identyfikatora diagnostyki wymienionymi w sekcji [Reference](#reference) .</span><span class="sxs-lookup"><span data-stu-id="b5327-109">If you encounter build warnings or errors due to usage of an obsolete API, follow the specific guidance provided for the diagnostic ID listed in the [Reference](#reference) section.</span></span> <span data-ttu-id="b5327-110">*Nie* można pominąć ostrzeżeń ani błędów dla tych Obsoletions przy użyciu [standardowego identyfikatora diagnostyki (CS0618)](../../csharp/language-reference/compiler-messages/cs0618.md) dla przestarzałych typów lub członków; `SYSLIBxxxx`zamiast tego użyj niestandardowych identyfikatorów diagnostyki.</span><span class="sxs-lookup"><span data-stu-id="b5327-110">Warnings or errors for these obsoletions *can't* be suppressed using the [standard diagnostic ID (CS0618)](../../csharp/language-reference/compiler-messages/cs0618.md) for obsolete types or members; use the custom `SYSLIBxxxx` diagnostic ID values instead.</span></span> <span data-ttu-id="b5327-111">Aby uzyskać więcej informacji, zobacz [pomijanie ostrzeżeń](#suppress-warnings).</span><span class="sxs-lookup"><span data-stu-id="b5327-111">For more information, see [Suppress warnings](#suppress-warnings).</span></span>

## <a name="reference"></a><span data-ttu-id="b5327-112">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="b5327-112">Reference</span></span>

<span data-ttu-id="b5327-113">Poniższa tabela zawiera indeks `SYSLIBxxxx` Obsoletions w programie .NET 5 lub nowszym.</span><span class="sxs-lookup"><span data-stu-id="b5327-113">The following table provides an index to the `SYSLIBxxxx` obsoletions in .NET 5+.</span></span>

| <span data-ttu-id="b5327-114">Identyfikator diagnostyki</span><span class="sxs-lookup"><span data-stu-id="b5327-114">Diagnostic ID</span></span> | <span data-ttu-id="b5327-115">Opis</span><span class="sxs-lookup"><span data-stu-id="b5327-115">Description</span></span> |
| - | - |
| [<span data-ttu-id="b5327-116">SYSLIB0001</span><span class="sxs-lookup"><span data-stu-id="b5327-116">SYSLIB0001</span></span>](syslib0001.md) | <span data-ttu-id="b5327-117">Kodowanie UTF-7 jest niezabezpieczone i nie powinno być używane.</span><span class="sxs-lookup"><span data-stu-id="b5327-117">The UTF-7 encoding is insecure and should not be used.</span></span> <span data-ttu-id="b5327-118">Zamiast tego należy rozważyć użycie UTF-8.</span><span class="sxs-lookup"><span data-stu-id="b5327-118">Consider using UTF-8 instead.</span></span> |
| [<span data-ttu-id="b5327-119">SYSLIB0002</span><span class="sxs-lookup"><span data-stu-id="b5327-119">SYSLIB0002</span></span>](syslib0002.md) | <span data-ttu-id="b5327-120"><xref:System.Security.Permissions.PrincipalPermissionAttribute> nie jest uznawany przez środowisko uruchomieniowe i nie może być używany.</span><span class="sxs-lookup"><span data-stu-id="b5327-120"><xref:System.Security.Permissions.PrincipalPermissionAttribute> is not honored by the runtime and must not be used.</span></span> |
| [<span data-ttu-id="b5327-121">SYSLIB0003</span><span class="sxs-lookup"><span data-stu-id="b5327-121">SYSLIB0003</span></span>](syslib0003.md) | <span data-ttu-id="b5327-122">Zabezpieczenia dostępu kodu (CAS) nie są obsługiwane ani honorowane przez środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="b5327-122">Code access security (CAS) is not supported or honored by the runtime.</span></span> |
| [<span data-ttu-id="b5327-123">SYSLIB0004</span><span class="sxs-lookup"><span data-stu-id="b5327-123">SYSLIB0004</span></span>](syslib0004.md) | <span data-ttu-id="b5327-124">Funkcja ograniczonego regionu wykonywania (CER) nie jest obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="b5327-124">The constrained execution region (CER) feature is not supported.</span></span> |
| [<span data-ttu-id="b5327-125">SYSLIB0005</span><span class="sxs-lookup"><span data-stu-id="b5327-125">SYSLIB0005</span></span>](syslib0005.md) | <span data-ttu-id="b5327-126">Globalna pamięć podręczna zestawów (GAC) nie jest obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="b5327-126">The global assembly cache (GAC) is not supported.</span></span> |
| [<span data-ttu-id="b5327-127">SYSLIB0006</span><span class="sxs-lookup"><span data-stu-id="b5327-127">SYSLIB0006</span></span>](syslib0006.md) | <span data-ttu-id="b5327-128"><xref:System.Threading.Thread.Abort?displayProperty=nameWithType> nie jest obsługiwane i zgłasza <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="b5327-128"><xref:System.Threading.Thread.Abort?displayProperty=nameWithType> is not supported and throws <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="b5327-129">SYSLIB0007</span><span class="sxs-lookup"><span data-stu-id="b5327-129">SYSLIB0007</span></span>](syslib0007.md) | <span data-ttu-id="b5327-130">Domyślna implementacja tego algorytmu kryptografii nie jest obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="b5327-130">The default implementation of this cryptography algorithm is not supported.</span></span> |
| [<span data-ttu-id="b5327-131">SYSLIB0008</span><span class="sxs-lookup"><span data-stu-id="b5327-131">SYSLIB0008</span></span>](syslib0008.md) | <span data-ttu-id="b5327-132"><xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator>Interfejs API nie jest obsługiwany i zgłasza <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="b5327-132">The <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator> API is not supported and throws <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="b5327-133">SYSLIB0009</span><span class="sxs-lookup"><span data-stu-id="b5327-133">SYSLIB0009</span></span>](syslib0009.md) | <span data-ttu-id="b5327-134"><xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType>Metody i <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> nie są obsługiwane i throw <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="b5327-134">The <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> and <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> methods are not supported and throw <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="b5327-135">SYSLIB0010</span><span class="sxs-lookup"><span data-stu-id="b5327-135">SYSLIB0010</span></span>](syslib0010.md) | <span data-ttu-id="b5327-136">Niektóre interfejsy API komunikacji zdalnej nie są obsługiwane i throw <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="b5327-136">Some remoting APIs are not supported and throw <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="b5327-137">SYSLIB0011</span><span class="sxs-lookup"><span data-stu-id="b5327-137">SYSLIB0011</span></span>](syslib0011.md) | <span data-ttu-id="b5327-138"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> Serializacja jest przestarzała i nie powinna być używana.</span><span class="sxs-lookup"><span data-stu-id="b5327-138"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization is obsolete and should not be used.</span></span> |
| [<span data-ttu-id="b5327-139">SYSLIB0012</span><span class="sxs-lookup"><span data-stu-id="b5327-139">SYSLIB0012</span></span>](syslib0012.md) | <span data-ttu-id="b5327-140"><xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> i <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType> są dołączone tylko do .NET Framework zgodności.</span><span class="sxs-lookup"><span data-stu-id="b5327-140"><xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> and <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType> are only included for .NET Framework compatibility.</span></span> <span data-ttu-id="b5327-141">Zamiast tego użyj polecenia cmdlet <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b5327-141">Use <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> instead.</span></span> |

## <a name="suppress-warnings"></a><span data-ttu-id="b5327-142">Pomijanie ostrzeżeń</span><span class="sxs-lookup"><span data-stu-id="b5327-142">Suppress warnings</span></span>

<span data-ttu-id="b5327-143">Jeśli musisz użyć przestarzałych interfejsów API, a `SYSLIBxxxx` Diagnostyka nie jest powierzchnią jako błąd, możesz pominąć ostrzeżenie w kodzie lub w pliku projektu.</span><span class="sxs-lookup"><span data-stu-id="b5327-143">If you must use the obsolete APIs and the `SYSLIBxxxx` diagnostic does not surface as an error, you can suppress the warning in code or in your project file.</span></span>

<span data-ttu-id="b5327-144">W kodzie:</span><span class="sxs-lookup"><span data-stu-id="b5327-144">In code:</span></span>

```csharp
// Disable the warning.
#pragma warning disable SYSLIB0001
// Code that uses obsolete API.
...
// Re-enable the warning.
#pragma warning restore SYSLIB0001
```

<span data-ttu-id="b5327-145">Plik projektu:</span><span class="sxs-lookup"><span data-stu-id="b5327-145">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
   <TargetFramework>net5.0</TargetFramework>
   <!-- NoWarn below suppresses SYSLIB0001 project-wide -->
   <NoWarn>$(NoWarn);SYSLIB0001</NoWarn>
  </PropertyGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="b5327-146">Pomijanie ostrzeżenia w ten sposób powoduje wyłączenie tylko określonego ostrzeżenia obsoletion.</span><span class="sxs-lookup"><span data-stu-id="b5327-146">Suppressing a warning in this way only disables that specific obsoletion warning.</span></span> <span data-ttu-id="b5327-147">Nie wyłącza żadnych innych ostrzeżeń, w tym innych ostrzeżeń obsoletion.</span><span class="sxs-lookup"><span data-stu-id="b5327-147">It doesn't disable any other warnings, including other obsoletion warnings.</span></span>
