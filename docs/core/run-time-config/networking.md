---
title: Ustawienia konfiguracji sieci
description: Informacje o ustawieniach czasu wykonywania, które konfigurują sieć dla aplikacji .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bda608e83bb1b093d7d9b860de9607f6734720aa
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188305"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="818a4-103">Opcje konfiguracji czasu wykonywania dla sieci</span><span class="sxs-lookup"><span data-stu-id="818a4-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="818a4-104">Protokół HTTP/2</span><span class="sxs-lookup"><span data-stu-id="818a4-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="818a4-105">Określa, czy jest włączona obsługa protokołu HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="818a4-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="818a4-106">Wprowadzone w programie .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="818a4-106">Introduced in .NET Core 3.0.</span></span>

- <span data-ttu-id="818a4-107">Tylko .NET Core 3,0: Jeśli pominięto to ustawienie, obsługa protokołu HTTP/2 jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="818a4-107">.NET Core 3.0 only: If you omit this setting, support for the HTTP/2 protocol is disabled.</span></span> <span data-ttu-id="818a4-108">Jest to równoznaczne z ustawieniem wartości `false` .</span><span class="sxs-lookup"><span data-stu-id="818a4-108">This is equivalent to setting the value to `false`.</span></span>

- <span data-ttu-id="818a4-109">.NET Core 3,1 i .NET 5 +: Jeśli pominięto to ustawienie, obsługa protokołu HTTP/2 jest włączona.</span><span class="sxs-lookup"><span data-stu-id="818a4-109">.NET Core 3.1 and .NET 5+: If you omit this setting, support for the HTTP/2 protocol is enabled.</span></span> <span data-ttu-id="818a4-110">Jest to równoznaczne z ustawieniem wartości `true` .</span><span class="sxs-lookup"><span data-stu-id="818a4-110">This is equivalent to setting the value to `true`.</span></span>

| | <span data-ttu-id="818a4-111">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="818a4-111">Setting name</span></span> | <span data-ttu-id="818a4-112">Wartości</span><span class="sxs-lookup"><span data-stu-id="818a4-112">Values</span></span> |
| - | - | - |
| <span data-ttu-id="818a4-113">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="818a4-113">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="818a4-114">`false` -wyłączone</span><span class="sxs-lookup"><span data-stu-id="818a4-114">`false` - disabled</span></span><br/><span data-ttu-id="818a4-115">`true` -włączone</span><span class="sxs-lookup"><span data-stu-id="818a4-115">`true` - enabled</span></span> |
| <span data-ttu-id="818a4-116">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="818a4-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="818a4-117">`0` -wyłączone</span><span class="sxs-lookup"><span data-stu-id="818a4-117">`0` - disabled</span></span><br/><span data-ttu-id="818a4-118">`1` -włączone</span><span class="sxs-lookup"><span data-stu-id="818a4-118">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="818a4-119">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="818a4-119">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="818a4-120">Określa, czy mają być <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> używane <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> lub starsze stosy protokołu HTTP ( <xref:System.Net.Http.WinHttpHandler> w systemach Windows i `CurlHandler` , wewnętrzna Klasa zaimplementowana w [libcurl](https://curl.haxx.se/libcurl/), w systemie Linux).</span><span class="sxs-lookup"><span data-stu-id="818a4-120">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="818a4-121">Możesz używać interfejsów API sieci wysokiego poziomu zamiast bezpośredniego tworzenia wystąpienia <xref:System.Net.Http.HttpClientHandler> klasy.</span><span class="sxs-lookup"><span data-stu-id="818a4-121">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="818a4-122">To ustawienie wpływa również na to, który stos protokołu HTTP jest używany przez interfejsy API sieci wysokiego poziomu, w tym <xref:System.Net.Http.HttpClient> i [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).</span><span class="sxs-lookup"><span data-stu-id="818a4-122">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).</span></span>

- <span data-ttu-id="818a4-123">Jeśli pominięto to ustawienie, program <xref:System.Net.Http.HttpClientHandler> używa <xref:System.Net.Http.SocketsHttpHandler> .</span><span class="sxs-lookup"><span data-stu-id="818a4-123">If you omit this setting, <xref:System.Net.Http.HttpClientHandler> uses <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="818a4-124">Jest to równoznaczne z ustawieniem wartości `true` .</span><span class="sxs-lookup"><span data-stu-id="818a4-124">This is equivalent to setting the value to `true`.</span></span>

- <span data-ttu-id="818a4-125">To ustawienie można skonfigurować programowo, wywołując <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodę.</span><span class="sxs-lookup"><span data-stu-id="818a4-125">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="818a4-126">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="818a4-126">Setting name</span></span> | <span data-ttu-id="818a4-127">Wartości</span><span class="sxs-lookup"><span data-stu-id="818a4-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="818a4-128">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="818a4-128">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="818a4-129">`true` -umożliwia korzystanie z <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="818a4-129">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="818a4-130">`false` -umożliwia korzystanie z programu <xref:System.Net.Http.WinHttpHandler> w systemie Windows lub [libcurl](https://curl.haxx.se/libcurl/) w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="818a4-130">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="818a4-131">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="818a4-131">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="818a4-132">`1` -umożliwia korzystanie z <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="818a4-132">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="818a4-133">`0` -umożliwia korzystanie z programu <xref:System.Net.Http.WinHttpHandler> w systemie Windows lub [libcurl](https://curl.haxx.se/libcurl/) w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="818a4-133">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="818a4-134">Począwszy od platformy .NET 5, `System.Net.Http.UseSocketsHttpHandler` ustawienie nie jest już dostępne.</span><span class="sxs-lookup"><span data-stu-id="818a4-134">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>

## <a name="latin1-headers-net-core-31-only"></a><span data-ttu-id="818a4-135">Nagłówki Latin1 (tylko program .NET Core 3,1)</span><span class="sxs-lookup"><span data-stu-id="818a4-135">Latin1 headers (.NET Core 3.1 only)</span></span>

- <span data-ttu-id="818a4-136">Ten przełącznik umożliwia złagodzeniu wymagań dotyczących walidacji nagłówka HTTP, co umożliwia <xref:System.Net.Http.SocketsHttpHandler> wysyłanie znaków zakodowanych ISO-8859-1 (Latin-1) w nagłówkach.</span><span class="sxs-lookup"><span data-stu-id="818a4-136">This switch allows relaxing the HTTP header validation, enabling <xref:System.Net.Http.SocketsHttpHandler> to send ISO-8859-1 (Latin-1) encoded characters in headers.</span></span>

- <span data-ttu-id="818a4-137">Jeśli pominięto to ustawienie, próba wysłania znaku innego niż ASCII spowoduje <xref:System.Net.Http.HttpRequestException> .</span><span class="sxs-lookup"><span data-stu-id="818a4-137">If you omit this setting, an attempt to send a non-ASCII character will result in <xref:System.Net.Http.HttpRequestException>.</span></span> <span data-ttu-id="818a4-138">Jest to równoznaczne z ustawieniem wartości `false` .</span><span class="sxs-lookup"><span data-stu-id="818a4-138">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="818a4-139">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="818a4-139">Setting name</span></span> | <span data-ttu-id="818a4-140">Wartości</span><span class="sxs-lookup"><span data-stu-id="818a4-140">Values</span></span> |
| - | - | - |
| <span data-ttu-id="818a4-141">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="818a4-141">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.AllowLatin1Headers` | <span data-ttu-id="818a4-142">`false` -wyłączone</span><span class="sxs-lookup"><span data-stu-id="818a4-142">`false` - disabled</span></span><br/><span data-ttu-id="818a4-143">`true` -włączone</span><span class="sxs-lookup"><span data-stu-id="818a4-143">`true` - enabled</span></span> |
| <span data-ttu-id="818a4-144">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="818a4-144">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_ALLOWLATIN1HEADERS` | <span data-ttu-id="818a4-145">`0` -wyłączone</span><span class="sxs-lookup"><span data-stu-id="818a4-145">`0` - disabled</span></span><br/><span data-ttu-id="818a4-146">`1` -włączone</span><span class="sxs-lookup"><span data-stu-id="818a4-146">`1` - enabled</span></span> |

> [!NOTE]
> <span data-ttu-id="818a4-147">Ta opcja jest dostępna tylko w programie .NET Core 3,1, ponieważ wersja 3.1.9, a nie w poprzedniej lub nowszej wersji.</span><span class="sxs-lookup"><span data-stu-id="818a4-147">This option is only available in .NET Core 3.1 since version 3.1.9, and not in previous or later versions.</span></span> <span data-ttu-id="818a4-148">W programie .NET 5 zalecamy korzystanie z programu <xref:System.Net.Http.SocketsHttpHandler.RequestHeaderEncodingSelector> .</span><span class="sxs-lookup"><span data-stu-id="818a4-148">In .NET 5 we recommend using <xref:System.Net.Http.SocketsHttpHandler.RequestHeaderEncodingSelector>.</span></span>
