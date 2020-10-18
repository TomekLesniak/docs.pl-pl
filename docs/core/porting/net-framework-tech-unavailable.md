---
title: Technologie .NET Framework niedostępne w oprogramowaniu .NET Core i .NET 5 +
titleSuffix: ''
description: Dowiedz się więcej na temat technologii .NET Framework, które są niedostępne w oprogramowaniu .NET Core i .NET 5,0 i nowszych wersjach.
author: cartermp
ms.date: 10/13/2020
ms.openlocfilehash: 492aace9db3dc3acef18e995f10b7b5fbe251558
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161039"
---
# <a name="net-framework-technologies-unavailable-on-net-core-and-net-5"></a>Technologie .NET Framework niedostępne w oprogramowaniu .NET Core i .NET 5 +

Niektóre technologie dostępne dla bibliotek .NET Framework nie są dostępne do użytku z platformami .NET Core i .NET 5,0 i nowszymi wersjami, takimi jak domeny aplikacji, komunikacja zdalna, zabezpieczenia dostępu kodu (CAS), przezroczystość zabezpieczeń i <xref:System.EnterpriseServices?displayProperty=fullName> . Jeśli biblioteki są zależne od co najmniej jednej z tych technologii, należy rozważyć alternatywne podejścia opisane tutaj. Aby uzyskać więcej informacji na temat zgodności interfejsów API, zobacz istotne [zmiany w programie .NET](../compatibility/breaking-changes.md).

> [!TIP]
> Tylko ponieważ interfejs API lub technologia nie jest obecnie zaimplementowana, nie oznacza to, że jest celowo nieobsługiwana. Przeszukaj repozytoria usługi .NET GitHub, aby zobaczyć, czy konkretny problem występuje w drodze projektu. Jeśli nie znajdziesz takiego wskaźnika, zgłoś problem w [repozytorium dotnet/Runtime](https://github.com/dotnet/runtime/issues) , aby uzyskać szczegółowe informacje o interfejsach API i technologiach.

## <a name="application-domains"></a>Domeny aplikacji

Domeny aplikacji (AppDomains) izolują aplikacje od siebie. Domeny aplikacji wymagają obsługi środowiska uruchomieniowego i są generalnie kosztowne. Tworzenie dodatkowych domen aplikacji nie jest obsługiwane i nie ma żadnych planów, aby dodać tę możliwość w przyszłości. W przypadku izolacji kodu Użyj oddzielnych procesów lub kontenerów jako alternatywy. Aby dynamicznie ładować zestawy, użyj <xref:System.Runtime.Loader.AssemblyLoadContext> klasy.

Aby ułatwić migrację kodu z .NET Framework, program .NET 5 i uwidacznia część <xref:System.AppDomain> powierzchni interfejsu API. Niektóre z interfejsów API działają normalnie (na przykład <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType> ), niektórzy członkowie nie wykonują żadnych operacji (na przykład <xref:System.AppDomain.SetCachePath%2A> ), a niektóre z nich zgłaszają <xref:System.PlatformNotSupportedException> (na przykład <xref:System.AppDomain.CreateDomain%2A> ). Sprawdź typy, które są używane w odniesieniu do [ `System.AppDomain` źródła odwołania](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Private.CoreLib/src/System/AppDomain.cs) w [repozytorium usługi GitHub/środowiska uruchomieniowego](https://github.com/dotnet/runtime). Upewnij się, że wybrano gałąź zgodną z zaimplementowaną wersją.

## <a name="remoting"></a>Komunikacji zdalnej

Komunikacja zdalna .NET została zidentyfikowana jako problematyczna architektura. Jest on używany do komunikacji między domenami aplikacji, które nie są już obsługiwane. Ponadto komunikacja zdalna wymaga obsługi środowiska uruchomieniowego, co jest kosztowne do utrzymania. Z tego względu komunikacja zdalna platformy .NET nie jest obsługiwana w przypadku programów .NET Core i .NET 5 + i nie planuje się dodawania do niej pomocy w przyszłości.

W przypadku komunikacji między procesami należy wziąć pod uwagę mechanizmy komunikacji między procesami (IPC) jako alternatywę dla usług zdalnych, takich jak <xref:System.IO.Pipes> Klasa lub <xref:System.IO.MemoryMappedFiles.MemoryMappedFile> Klasa.

Na wielu maszynach Użyj rozwiązania sieciowego jako alternatywy. Najlepiej użyć niskiego obciążenia protokołu zwykłego tekstu, takiego jak HTTP. [Serwer sieci Web Kestrel](/aspnet/core/fundamentals/servers/kestrel), który jest serwerem sieci Web używanym przez ASP.NET Core, jest opcją. Należy również rozważyć użycie <xref:System.Net.Sockets> w przypadku scenariuszy opartych na sieci i wielu maszynach. Aby uzyskać więcej opcji, zobacz [projekty programu .NET Open Source Developer projects: Messaging](https://github.com/Microsoft/dotnet/blob/master/dotnet-developer-projects.md#messaging).

## <a name="code-access-security-cas"></a>Zabezpieczenia dostępu kodu (CAS)

Tryb piaskownicy, który opiera się na środowisku uruchomieniowym lub w strukturze, aby ograniczyć zasoby, których zarządzana aplikacja lub biblioteka jest uruchomiona, [nie jest obsługiwane w .NET Framework](../../framework/misc/code-access-security.md) i dlatego również nie jest obsługiwane w przypadku programów .NET Core i .NET 5 +. W .NET Framework jest zbyt wiele przypadków i środowisko uruchomieniowe, w którym występuje podniesienie uprawnień, aby kontynuować traktowanie urzędów certyfikacji jako granic zabezpieczeń. Ponadto urzędy certyfikacji czynią implementację bardziej skomplikowaną i często mają prawidłowy wpływ na wydajność aplikacji, które nie będą używane.

Aby uruchamiać procesy z minimalnym zestawem uprawnień, należy używać granic zabezpieczeń zapewnianych przez system operacyjny, takich jak wirtualizacja, kontenery lub konta użytkowników.

## <a name="security-transparency"></a>Przejrzystość zabezpieczeń

Podobnie jak w przypadku urzędów certyfikacji, przezroczystość zabezpieczeń oddziela kod w trybie piaskownicy od krytycznego kodu zabezpieczeń w sposób deklaratywny, ale [nie jest już obsługiwany jako granica zabezpieczeń](../../framework/misc/security-transparent-code.md). Ta funkcja jest intensywnie używana przez program Silverlight.

Aby uruchamiać procesy z najmniej zestawem uprawnień, należy używać granic zabezpieczeń udostępnianych przez system operacyjny, takich jak wirtualizacja, kontenery lub konta użytkowników.

## <a name="systementerpriseservices"></a>System. EnterpriseServices

<xref:System.EnterpriseServices?displayProperty=fullName> (COM+) nie jest obsługiwany przez programy .NET Core i .NET 5 +.

## <a name="see-also"></a>Zobacz też

- [Przegląd portów z .NET Framework do platformy .NET Core](index.md)
