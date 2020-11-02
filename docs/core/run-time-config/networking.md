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
# <a name="run-time-configuration-options-for-networking"></a>Opcje konfiguracji czasu wykonywania dla sieci

## <a name="http2-protocol"></a>Protokół HTTP/2

- Określa, czy jest włączona obsługa protokołu HTTP/2.

- Wprowadzone w programie .NET Core 3,0.

- Tylko .NET Core 3,0: Jeśli pominięto to ustawienie, obsługa protokołu HTTP/2 jest wyłączona. Jest to równoznaczne z ustawieniem wartości `false` .

- .NET Core 3,1 i .NET 5 +: Jeśli pominięto to ustawienie, obsługa protokołu HTTP/2 jest włączona. Jest to równoznaczne z ustawieniem wartości `true` .

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

## <a name="latin1-headers-net-core-31-only"></a>Nagłówki Latin1 (tylko program .NET Core 3,1)

- Ten przełącznik umożliwia złagodzeniu wymagań dotyczących walidacji nagłówka HTTP, co umożliwia <xref:System.Net.Http.SocketsHttpHandler> wysyłanie znaków zakodowanych ISO-8859-1 (Latin-1) w nagłówkach.

- Jeśli pominięto to ustawienie, próba wysłania znaku innego niż ASCII spowoduje <xref:System.Net.Http.HttpRequestException> . Jest to równoznaczne z ustawieniem wartości `false` .

| | Nazwa ustawienia | Wartości |
| - | - | - |
| **runtimeconfig.jsna** | `System.Net.Http.SocketsHttpHandler.AllowLatin1Headers` | `false` -wyłączone<br/>`true` -włączone |
| **Zmienna środowiskowa** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_ALLOWLATIN1HEADERS` | `0` -wyłączone<br/>`1` -włączone |

> [!NOTE]
> Ta opcja jest dostępna tylko w programie .NET Core 3,1, ponieważ wersja 3.1.9, a nie w poprzedniej lub nowszej wersji. W programie .NET 5 zalecamy korzystanie z programu <xref:System.Net.Http.SocketsHttpHandler.RequestHeaderEncodingSelector> .
