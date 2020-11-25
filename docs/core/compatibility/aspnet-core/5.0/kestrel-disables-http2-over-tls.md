---
title: 'Nieprzerwana zmiana: Kestrel: protokół HTTP/2 jest wyłączony przy użyciu protokołu TLS w niezgodnych wersjach systemu Windows'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej Kestrel: HTTP/2 wyłączonej przy użyciu protokołu TLS dla niezgodnych wersji systemu Windows'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: befd393795f3e1859d391bca513dd9856101d295
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761592"
---
# <a name="kestrel-http2-disabled-over-tls-on-incompatible-windows-versions"></a><span data-ttu-id="ff455-103">Kestrel: protokół HTTP/2 został wyłączony przy użyciu protokołu TLS dla niezgodnych wersji systemu Windows</span><span class="sxs-lookup"><span data-stu-id="ff455-103">Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions</span></span>

<span data-ttu-id="ff455-104">Aby włączyć protokół HTTP/2 dla Transport Layer Security (TLS) w systemie Windows, należy spełnić dwa wymagania:</span><span class="sxs-lookup"><span data-stu-id="ff455-104">To enable HTTP/2 over Transport Layer Security (TLS) on Windows, two requirements need to be met:</span></span>

- <span data-ttu-id="ff455-105">Obsługa negocjacji protokołów Application-Layer (CLIENTHELLO ALPN), która jest dostępna od Windows 8.1 i Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="ff455-105">Application-Layer Protocol Negotiation (ALPN) support, which is available starting with Windows 8.1 and Windows Server 2012 R2.</span></span>
- <span data-ttu-id="ff455-106">Zestaw szyfrów zgodny z protokołem HTTP/2, który jest dostępny od systemu Windows 10 i Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="ff455-106">A set of ciphers compatible with HTTP/2, which is available starting with Windows 10 and Windows Server 2016.</span></span>

<span data-ttu-id="ff455-107">W związku z tym zachowanie Kestrel w przypadku skonfigurowania protokołu HTTP/2 za pośrednictwem protokołu TLS zostało zmienione na:</span><span class="sxs-lookup"><span data-stu-id="ff455-107">As such, Kestrel's behavior when HTTP/2 over TLS is configured has changed to:</span></span>

- <span data-ttu-id="ff455-108">Obniżanie `Http1` poziomu i rejestrowanie komunikatów na `Information` poziomie, gdy [ListenOptions. HttpProtocols](/dotnet/api/microsoft.aspnetcore.server.kestrel.core.httpprotocols) jest ustawiony na `Http1AndHttp2` .</span><span class="sxs-lookup"><span data-stu-id="ff455-108">Downgrade to `Http1` and log a message at the `Information` level when [ListenOptions.HttpProtocols](/dotnet/api/microsoft.aspnetcore.server.kestrel.core.httpprotocols) is set to `Http1AndHttp2`.</span></span> <span data-ttu-id="ff455-109">`Http1AndHttp2` jest wartością domyślną dla `ListenOptions.HttpProtocols` .</span><span class="sxs-lookup"><span data-stu-id="ff455-109">`Http1AndHttp2` is the default value for `ListenOptions.HttpProtocols`.</span></span>
- <span data-ttu-id="ff455-110">Zgłoś, `NotSupportedException` gdy `ListenOptions.HttpProtocols` jest ustawiony na `Http2` .</span><span class="sxs-lookup"><span data-stu-id="ff455-110">Throw a `NotSupportedException` when `ListenOptions.HttpProtocols` is set to `Http2`.</span></span>

<span data-ttu-id="ff455-111">Aby zapoznać się z omówieniem, zobacz temat Issue [dotnet/aspnetcore # 23068](https://github.com/dotnet/aspnetcore/issues/23068).</span><span class="sxs-lookup"><span data-stu-id="ff455-111">For discussion, see issue [dotnet/aspnetcore#23068](https://github.com/dotnet/aspnetcore/issues/23068).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="ff455-112">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="ff455-112">Version introduced</span></span>

<span data-ttu-id="ff455-113">ASP.NET Core 5,0 wersja zapoznawcza 7</span><span class="sxs-lookup"><span data-stu-id="ff455-113">ASP.NET Core 5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="ff455-114">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="ff455-114">Old behavior</span></span>

<span data-ttu-id="ff455-115">W poniższej tabeli przedstawiono zachowanie w przypadku skonfigurowania protokołu HTTP/2 za pośrednictwem protokołu TLS.</span><span class="sxs-lookup"><span data-stu-id="ff455-115">The following table outlines the behavior when HTTP/2 over TLS is configured.</span></span>

| <span data-ttu-id="ff455-116">Protokoły</span><span class="sxs-lookup"><span data-stu-id="ff455-116">Protocols</span></span> | <span data-ttu-id="ff455-117">System Windows 7,</span><span class="sxs-lookup"><span data-stu-id="ff455-117">Windows 7,</span></span><br /><span data-ttu-id="ff455-118">Windows Server 2008 R2,</span><span class="sxs-lookup"><span data-stu-id="ff455-118">Windows Server 2008 R2,</span></span><br /><span data-ttu-id="ff455-119">lub starszy</span><span class="sxs-lookup"><span data-stu-id="ff455-119">or earlier</span></span> | <span data-ttu-id="ff455-120">System Windows 8,</span><span class="sxs-lookup"><span data-stu-id="ff455-120">Windows 8,</span></span><br /><span data-ttu-id="ff455-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ff455-121">Windows Server 2012</span></span> | <span data-ttu-id="ff455-122">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ff455-122">Windows 8.1,</span></span><br /><span data-ttu-id="ff455-123">Windows Server 2012 z dodatkiem R2</span><span class="sxs-lookup"><span data-stu-id="ff455-123">Windows Server 2012 R2</span></span> | <span data-ttu-id="ff455-124">System Windows 10,</span><span class="sxs-lookup"><span data-stu-id="ff455-124">Windows 10,</span></span><br /><span data-ttu-id="ff455-125">System Windows Server 2016,</span><span class="sxs-lookup"><span data-stu-id="ff455-125">Windows Server 2016,</span></span><br /><span data-ttu-id="ff455-126">lub nowszy</span><span class="sxs-lookup"><span data-stu-id="ff455-126">or newer</span></span> |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | <span data-ttu-id="ff455-127">Generować `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="ff455-127">Throw `NotSupportedException`</span></span>                   | <span data-ttu-id="ff455-128">Błąd podczas uzgadniania protokołu TLS</span><span class="sxs-lookup"><span data-stu-id="ff455-128">Error during TLS handshake</span></span>     | <span data-ttu-id="ff455-129">Błąd podczas uzgadniania protokołu TLS &ast;</span><span class="sxs-lookup"><span data-stu-id="ff455-129">Error during TLS handshake &ast;</span></span>     | <span data-ttu-id="ff455-130">Brak błędów</span><span class="sxs-lookup"><span data-stu-id="ff455-130">No error</span></span> |
| `Http1AndHttp2` | <span data-ttu-id="ff455-131">Obniżanie poziomu `Http1`</span><span class="sxs-lookup"><span data-stu-id="ff455-131">Downgrade to `Http1`</span></span>                    | <span data-ttu-id="ff455-132">Obniżanie poziomu `Http1`</span><span class="sxs-lookup"><span data-stu-id="ff455-132">Downgrade to `Http1`</span></span>     | <span data-ttu-id="ff455-133">Błąd podczas uzgadniania protokołu TLS &ast;</span><span class="sxs-lookup"><span data-stu-id="ff455-133">Error during TLS handshake &ast;</span></span>     | <span data-ttu-id="ff455-134">Brak błędów</span><span class="sxs-lookup"><span data-stu-id="ff455-134">No error</span></span> |

<span data-ttu-id="ff455-135">&ast; Skonfiguruj zgodne mechanizmy szyfrowania, aby włączyć te scenariusze.</span><span class="sxs-lookup"><span data-stu-id="ff455-135">&ast; Configure compatible cipher suites to enable these scenarios.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="ff455-136">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="ff455-136">New behavior</span></span>

<span data-ttu-id="ff455-137">W poniższej tabeli przedstawiono zachowanie w przypadku skonfigurowania protokołu HTTP/2 za pośrednictwem protokołu TLS.</span><span class="sxs-lookup"><span data-stu-id="ff455-137">The following table outlines the behavior when HTTP/2 over TLS is configured.</span></span>

| <span data-ttu-id="ff455-138">Protokoły</span><span class="sxs-lookup"><span data-stu-id="ff455-138">Protocols</span></span> | <span data-ttu-id="ff455-139">System Windows 7,</span><span class="sxs-lookup"><span data-stu-id="ff455-139">Windows 7,</span></span><br /><span data-ttu-id="ff455-140">Windows Server 2008 R2,</span><span class="sxs-lookup"><span data-stu-id="ff455-140">Windows Server 2008 R2,</span></span><br /><span data-ttu-id="ff455-141">lub starszy</span><span class="sxs-lookup"><span data-stu-id="ff455-141">or earlier</span></span> | <span data-ttu-id="ff455-142">System Windows 8,</span><span class="sxs-lookup"><span data-stu-id="ff455-142">Windows 8,</span></span><br /><span data-ttu-id="ff455-143">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ff455-143">Windows Server 2012</span></span> | <span data-ttu-id="ff455-144">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ff455-144">Windows 8.1,</span></span><br /><span data-ttu-id="ff455-145">Windows Server 2012 z dodatkiem R2</span><span class="sxs-lookup"><span data-stu-id="ff455-145">Windows Server 2012 R2</span></span> | <span data-ttu-id="ff455-146">System Windows 10,</span><span class="sxs-lookup"><span data-stu-id="ff455-146">Windows 10,</span></span><br /><span data-ttu-id="ff455-147">System Windows Server 2016,</span><span class="sxs-lookup"><span data-stu-id="ff455-147">Windows Server 2016,</span></span><br /><span data-ttu-id="ff455-148">lub nowszy</span><span class="sxs-lookup"><span data-stu-id="ff455-148">or newer</span></span> |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | <span data-ttu-id="ff455-149">Generować `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="ff455-149">Throw `NotSupportedException`</span></span>                   | <span data-ttu-id="ff455-150">Generować `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="ff455-150">Throw `NotSupportedException`</span></span>     | <span data-ttu-id="ff455-151">Zgłoś `NotSupportedException`&ast;&ast;</span><span class="sxs-lookup"><span data-stu-id="ff455-151">Throw `NotSupportedException` &ast;&ast;</span></span>     | <span data-ttu-id="ff455-152">Brak błędów</span><span class="sxs-lookup"><span data-stu-id="ff455-152">No error</span></span> |
| `Http1AndHttp2` | <span data-ttu-id="ff455-153">Obniżanie poziomu `Http1`</span><span class="sxs-lookup"><span data-stu-id="ff455-153">Downgrade to `Http1`</span></span>                    | <span data-ttu-id="ff455-154">Obniżanie poziomu `Http1`</span><span class="sxs-lookup"><span data-stu-id="ff455-154">Downgrade to `Http1`</span></span>     | <span data-ttu-id="ff455-155">`Http1`Obniżanie poziomu&ast;&ast;</span><span class="sxs-lookup"><span data-stu-id="ff455-155">Downgrade to `Http1` &ast;&ast;</span></span>     | <span data-ttu-id="ff455-156">Brak błędów</span><span class="sxs-lookup"><span data-stu-id="ff455-156">No error</span></span> |

<span data-ttu-id="ff455-157">&ast;&ast; Skonfiguruj zgodne mechanizmy szyfrowania i ustaw przełącznik kontekstu aplikacji, `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` Aby `true` włączyć te scenariusze.</span><span class="sxs-lookup"><span data-stu-id="ff455-157">&ast;&ast; Configure compatible cipher suites and set the app context switch `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` to `true` to enable these scenarios.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ff455-158">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="ff455-158">Reason for change</span></span>

<span data-ttu-id="ff455-159">Ta zmiana zapewnia, że błędy zgodności dla protokołu HTTP/2 za pośrednictwem protokołu TLS w starszych wersjach systemu Windows są roznoszone jako wczesne i możliwie jasne.</span><span class="sxs-lookup"><span data-stu-id="ff455-159">This change ensures compatibility errors for HTTP/2 over TLS on older Windows versions are surfaced as early and as clearly as possible.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ff455-160">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="ff455-160">Recommended action</span></span>

<span data-ttu-id="ff455-161">Upewnij się, że protokół HTTP/2 przy użyciu protokołu TLS jest wyłączony w niezgodnych wersjach systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="ff455-161">Ensure HTTP/2 over TLS is disabled on incompatible Windows versions.</span></span> <span data-ttu-id="ff455-162">Windows 8.1 i Windows Server 2012 R2 są niezgodne, ponieważ nie mają domyślnie wymaganych szyfrów.</span><span class="sxs-lookup"><span data-stu-id="ff455-162">Windows 8.1 and Windows Server 2012 R2 are incompatible since they lack the necessary ciphers by default.</span></span> <span data-ttu-id="ff455-163">Można jednak zaktualizować ustawienia konfiguracji komputera w taki sposób, aby korzystały z szyfrów zgodnych z protokołem HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="ff455-163">However, it's possible to update the Computer Configuration settings to use HTTP/2 compatible ciphers.</span></span> <span data-ttu-id="ff455-164">Aby uzyskać więcej informacji, zobacz [mechanizmy szyfrowania TLS w Windows 8.1](/windows/win32/secauthn/tls-cipher-suites-in-windows-8-1).</span><span class="sxs-lookup"><span data-stu-id="ff455-164">For more information, see [TLS cipher suites in Windows 8.1](/windows/win32/secauthn/tls-cipher-suites-in-windows-8-1).</span></span> <span data-ttu-id="ff455-165">Po skonfigurowaniu protokołu HTTP/2 za pośrednictwem protokołu TLS w systemie Kestrel należy włączyć ustawienie przełącznika kontekstu aplikacji `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` .</span><span class="sxs-lookup"><span data-stu-id="ff455-165">Once configured, HTTP/2 over TLS on Kestrel must be enabled by setting the app context switch `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2`.</span></span> <span data-ttu-id="ff455-166">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="ff455-166">For example:</span></span>

```csharp
AppContext.SetSwitch("Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2", true);
```

<span data-ttu-id="ff455-167">Żadna podstawowa pomoc techniczna nie została zmieniona.</span><span class="sxs-lookup"><span data-stu-id="ff455-167">No underlying support has changed.</span></span> <span data-ttu-id="ff455-168">Na przykład protokół HTTP/2 za pośrednictwem protokołu TLS nigdy nie pracował w systemie Windows 8 lub Windows Server 2012.</span><span class="sxs-lookup"><span data-stu-id="ff455-168">For example, HTTP/2 over TLS has never worked on Windows 8 or Windows Server 2012.</span></span> <span data-ttu-id="ff455-169">Ta zmiana modyfikuje sposób wyświetlania błędów w tych nieobsługiwanych scenariuszach.</span><span class="sxs-lookup"><span data-stu-id="ff455-169">This change modifies how errors in these unsupported scenarios are presented.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ff455-170">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="ff455-170">Affected APIs</span></span>

<span data-ttu-id="ff455-171">Brak</span><span class="sxs-lookup"><span data-stu-id="ff455-171">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
