---
title: Ustawienia konfiguracji sieci
description: Informacje o ustawieniach czasu wykonywania, które konfigurują sieć dla aplikacji .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: d43b68206cc82f4a41df02bd5998702b4f5d0590
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538136"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="fe016-103">Opcje konfiguracji czasu wykonywania dla sieci</span><span class="sxs-lookup"><span data-stu-id="fe016-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="fe016-104">Protokół HTTP/2</span><span class="sxs-lookup"><span data-stu-id="fe016-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="fe016-105">Określa, czy jest włączona obsługa protokołu HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="fe016-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="fe016-106">Jeśli pominięto to ustawienie, obsługa protokołu HTTP/2 jest wyłączona.</span><span class="sxs-lookup"><span data-stu-id="fe016-106">If you omit this setting, support for the HTTP/2 protocol is disabled.</span></span> <span data-ttu-id="fe016-107">Jest to równoznaczne z ustawieniem wartości `false` .</span><span class="sxs-lookup"><span data-stu-id="fe016-107">This is equivalent to setting the value to `false`.</span></span>

- <span data-ttu-id="fe016-108">Wprowadzone w programie .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="fe016-108">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="fe016-109">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="fe016-109">Setting name</span></span> | <span data-ttu-id="fe016-110">Wartości</span><span class="sxs-lookup"><span data-stu-id="fe016-110">Values</span></span> |
| - | - | - |
| <span data-ttu-id="fe016-111">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="fe016-111">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="fe016-112">`false` -wyłączone</span><span class="sxs-lookup"><span data-stu-id="fe016-112">`false` - disabled</span></span><br/><span data-ttu-id="fe016-113">`true` -włączone</span><span class="sxs-lookup"><span data-stu-id="fe016-113">`true` - enabled</span></span> |
| <span data-ttu-id="fe016-114">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="fe016-114">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="fe016-115">`0` -wyłączone</span><span class="sxs-lookup"><span data-stu-id="fe016-115">`0` - disabled</span></span><br/><span data-ttu-id="fe016-116">`1` -włączone</span><span class="sxs-lookup"><span data-stu-id="fe016-116">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="fe016-117">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="fe016-117">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="fe016-118">Określa, czy mają być <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> używane <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> lub starsze stosy protokołu HTTP ( <xref:System.Net.Http.WinHttpHandler> w systemach Windows i `CurlHandler` , wewnętrzna Klasa zaimplementowana w [libcurl](https://curl.haxx.se/libcurl/), w systemie Linux).</span><span class="sxs-lookup"><span data-stu-id="fe016-118">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="fe016-119">Możesz używać interfejsów API sieci wysokiego poziomu zamiast bezpośredniego tworzenia wystąpienia <xref:System.Net.Http.HttpClientHandler> klasy.</span><span class="sxs-lookup"><span data-stu-id="fe016-119">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="fe016-120">To ustawienie wpływa również na to, który stos protokołu HTTP jest używany przez interfejsy API sieci wysokiego poziomu, w tym <xref:System.Net.Http.HttpClient> i [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).</span><span class="sxs-lookup"><span data-stu-id="fe016-120">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).</span></span>

- <span data-ttu-id="fe016-121">Jeśli pominięto to ustawienie, program <xref:System.Net.Http.HttpClientHandler> używa <xref:System.Net.Http.SocketsHttpHandler> .</span><span class="sxs-lookup"><span data-stu-id="fe016-121">If you omit this setting, <xref:System.Net.Http.HttpClientHandler> uses <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="fe016-122">Jest to równoznaczne z ustawieniem wartości `true` .</span><span class="sxs-lookup"><span data-stu-id="fe016-122">This is equivalent to setting the value to `true`.</span></span>

- <span data-ttu-id="fe016-123">To ustawienie można skonfigurować programowo, wywołując <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodę.</span><span class="sxs-lookup"><span data-stu-id="fe016-123">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="fe016-124">Nazwa ustawienia</span><span class="sxs-lookup"><span data-stu-id="fe016-124">Setting name</span></span> | <span data-ttu-id="fe016-125">Wartości</span><span class="sxs-lookup"><span data-stu-id="fe016-125">Values</span></span> |
| - | - | - |
| <span data-ttu-id="fe016-126">**runtimeconfig.jsna**</span><span class="sxs-lookup"><span data-stu-id="fe016-126">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="fe016-127">`true` -umożliwia korzystanie z <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="fe016-127">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="fe016-128">`false` -umożliwia korzystanie z programu <xref:System.Net.Http.WinHttpHandler> w systemie Windows lub [libcurl](https://curl.haxx.se/libcurl/) w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="fe016-128">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="fe016-129">**Zmienna środowiskowa**</span><span class="sxs-lookup"><span data-stu-id="fe016-129">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="fe016-130">`1` -umożliwia korzystanie z <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="fe016-130">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="fe016-131">`0` -umożliwia korzystanie z programu <xref:System.Net.Http.WinHttpHandler> w systemie Windows lub [libcurl](https://curl.haxx.se/libcurl/) w systemie Linux</span><span class="sxs-lookup"><span data-stu-id="fe016-131">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="fe016-132">Począwszy od platformy .NET 5, `System.Net.Http.UseSocketsHttpHandler` ustawienie nie jest już dostępne.</span><span class="sxs-lookup"><span data-stu-id="fe016-132">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
