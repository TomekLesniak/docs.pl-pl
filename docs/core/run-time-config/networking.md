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
# <a name="run-time-configuration-options-for-networking"></a>Opcje konfiguracji czasu wykonywania dla sieci

## <a name="http2-protocol"></a>Protokół HTTP/2

- Określa, czy jest włączona obsługa protokołu HTTP/2.

- Jeśli pominięto to ustawienie, obsługa protokołu HTTP/2 jest wyłączona. Jest to równoznaczne z ustawieniem wartości `false` .

- Wprowadzone w programie .NET Core 3,0.

| | Nazwa ustawienia | Wartości |
| - | - | - |
| **runtimeconfig.jsna** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false` -wyłączone<br/>`true` -włączone |
| **Zmienna środowiskowa** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0` -wyłączone<br/>`1` -włączone |

## <a name="usesocketshttphandler"></a>UseSocketsHttpHandler

- Określa, czy mają być <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> używane <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> lub starsze stosy protokołu HTTP ( <xref:System.Net.Http.WinHttpHandler> w systemach Windows i `CurlHandler` , wewnętrzna Klasa zaimplementowana w [libcurl](https://curl.haxx.se/libcurl/), w systemie Linux).

  > [!NOTE]
  > Możesz używać interfejsów API sieci wysokiego poziomu zamiast bezpośredniego tworzenia wystąpienia <xref:System.Net.Http.HttpClientHandler> klasy. To ustawienie wpływa również na to, który stos protokołu HTTP jest używany przez interfejsy API sieci wysokiego poziomu, w tym <xref:System.Net.Http.HttpClient> i [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).

- Jeśli pominięto to ustawienie, program <xref:System.Net.Http.HttpClientHandler> używa <xref:System.Net.Http.SocketsHttpHandler> . Jest to równoznaczne z ustawieniem wartości `true` .

- To ustawienie można skonfigurować programowo, wywołując <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> metodę.

| | Nazwa ustawienia | Wartości |
| - | - | - |
| **runtimeconfig.jsna** | `System.Net.Http.UseSocketsHttpHandler` | `true` -umożliwia korzystanie z <xref:System.Net.Http.SocketsHttpHandler><br/>`false` -umożliwia korzystanie z programu <xref:System.Net.Http.WinHttpHandler> w systemie Windows lub [libcurl](https://curl.haxx.se/libcurl/) w systemie Linux |
| **Zmienna środowiskowa** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1` -umożliwia korzystanie z <xref:System.Net.Http.SocketsHttpHandler><br/>`0` -umożliwia korzystanie z programu <xref:System.Net.Http.WinHttpHandler> w systemie Windows lub [libcurl](https://curl.haxx.se/libcurl/) w systemie Linux |

> [!NOTE]
> Począwszy od platformy .NET 5, `System.Net.Http.UseSocketsHttpHandler` ustawienie nie jest już dostępne.
