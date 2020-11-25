---
title: 'Istotna zmiana: HttpSys: ponowne negocjowanie certyfikatu klienta jest wyłączone domyślnie'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanej HttpSys: ponowne negocjowanie certyfikatu klienta wyłączone domyślnie'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 796989e1a21e3cb206d081e4fe8f79630121dc84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761351"
---
# <a name="httpsys-client-certificate-renegotiation-disabled-by-default"></a>HttpSys: ponowne negocjowanie certyfikatu klienta jest wyłączone domyślnie

Opcja renegocjuj połączenie i Zażądaj certyfikatu klienta została domyślnie wyłączona. Aby zapoznać się z omówieniem, zobacz temat Issue [dotnet/aspnetcore # 23181](https://github.com/dotnet/aspnetcore/issues/23181).

## <a name="version-introduced"></a>Wprowadzona wersja

ASP.NET Core 5,0

## <a name="old-behavior"></a>Stare zachowanie

Połączenie może zostać ponownie wynegocjowane w celu zażądania certyfikatu klienta.

## <a name="new-behavior"></a>Nowe zachowanie

Certyfikaty klienta można żądać tylko podczas początkowego uzgadniania połączeń. Aby uzyskać więcej informacji, zobacz żądanie ściągnięcia [dotnet/aspnetcore # 23162](https://github.com/dotnet/aspnetcore/pull/23162).

## <a name="reason-for-change"></a>Przyczyna zmiany

Ponowna negocjacja spowodowała wiele problemów z wydajnością i zakleszczeniami. Nie jest to również obsługiwane w przypadku protokołu HTTP/2. Aby uzyskać dodatkowy kontekst od momentu, gdy opcja kontrolowania tego zachowania została wprowadzona w ASP.NET Core 3,1, zobacz temat Issue [dotnet/aspnetcore # 14806](https://github.com/dotnet/aspnetcore/issues/14806).

## <a name="recommended-action"></a>Zalecana akcja

Aplikacje, które wymagają certyfikatów klienta, powinny używać *netsh.exe* , aby ustawić `clientcertnegotiation` opcję na `enabled` . Aby uzyskać więcej informacji, zobacz [polecenia netsh http](/windows-server/networking/technologies/netsh/netsh-http).

Jeśli chcesz, aby certyfikaty klienta były włączone tylko dla niektórych części aplikacji, zapoznaj się ze wskazówkami dotyczącymi [opcjonalnych certyfikatów klienta](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).

Jeśli potrzebujesz starego zachowania renegocjuj, ustaw `HttpSysOptions.ClientCertificateMethod` dla starej wartości `ClientCertificateMethod.AllowRenegotiate` . Nie jest to zalecane z powodów przedstawionych powyżej i w połączonych wskazówkach.

## <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod%2A?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate`
- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync`
- `Overload:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod`

-->
