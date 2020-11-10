---
title: ASP.NET Core istotne zmiany
titleSuffix: ''
description: Wyświetla listę istotnych zmian w ASP.NET Core.
ms.date: 11/03/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: 6e8e35d01ea7ff91c45bf1febd822e8497b608f0
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440490"
---
# <a name="aspnet-core-breaking-changes"></a><span data-ttu-id="b882d-103">ASP.NET Core istotne zmiany</span><span class="sxs-lookup"><span data-stu-id="b882d-103">ASP.NET Core breaking changes</span></span>

<span data-ttu-id="b882d-104">ASP.NET Core udostępnia funkcje deweloperskie aplikacji sieci Web używane przez platformę .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b882d-104">ASP.NET Core provides the web app development features used by .NET Core.</span></span>

<span data-ttu-id="b882d-105">Wybierz jedno z poniższych linków, aby uzyskać istotne zmiany w określonej wersji:</span><span class="sxs-lookup"><span data-stu-id="b882d-105">Select one of the following links for breaking changes in a specific version:</span></span>

* [<span data-ttu-id="b882d-106">ASP.NET Core 5,0</span><span class="sxs-lookup"><span data-stu-id="b882d-106">ASP.NET Core 5.0</span></span>](#aspnet-core-50)
* [<span data-ttu-id="b882d-107">ASP.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="b882d-107">ASP.NET Core 3.1</span></span>](#aspnet-core-31)
* [<span data-ttu-id="b882d-108">ASP.NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="b882d-108">ASP.NET Core 3.0</span></span>](#aspnet-core-30)

<span data-ttu-id="b882d-109">Następujące istotne zmiany w ASP.NET Core 3,0, 3,1 i 5,0 są udokumentowane na tej stronie:</span><span class="sxs-lookup"><span data-stu-id="b882d-109">The following breaking changes in ASP.NET Core 3.0, 3.1, and 5.0 are documented on this page:</span></span>

- [<span data-ttu-id="b882d-110">Usunięto przestarzałe interfejsy API "antysfałszowane", "CORS, Diagnostics, MVC i Routing"</span><span class="sxs-lookup"><span data-stu-id="b882d-110">Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed</span></span>](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [<span data-ttu-id="b882d-111">Uwierzytelnianie: AzureAD. UI i AzureADB2C. interfejs API i pakiety oznaczone jako przestarzałe</span><span class="sxs-lookup"><span data-stu-id="b882d-111">Authentication: AzureAD.UI and AzureADB2C.UI APIs and packages marked obsolete</span></span>](#authentication-azureadui-and-azureadb2cui-apis-and-packages-marked-obsolete)
- [<span data-ttu-id="b882d-112">Uwierzytelnianie: Google + zaniechana</span><span class="sxs-lookup"><span data-stu-id="b882d-112">Authentication: Google+ deprecation</span></span>](#authentication-google-deprecated-and-replaced)
- [<span data-ttu-id="b882d-113">Uwierzytelnianie: Właściwość HttpContext. Authentication została usunięta</span><span class="sxs-lookup"><span data-stu-id="b882d-113">Authentication: HttpContext.Authentication property removed</span></span>](#authentication-httpcontextauthentication-property-removed)
- [<span data-ttu-id="b882d-114">Uwierzytelnianie: Newtonsoft.Jstypów zamieniono</span><span class="sxs-lookup"><span data-stu-id="b882d-114">Authentication: Newtonsoft.Json types replaced</span></span>](#authentication-newtonsoftjson-types-replaced)
- [<span data-ttu-id="b882d-115">Uwierzytelnianie: OAuthHandler ExchangeCodeAsync zmieniono sygnaturę</span><span class="sxs-lookup"><span data-stu-id="b882d-115">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [<span data-ttu-id="b882d-116">Autoryzacja: Przeciążenie metody addauthorization przeniesiono do innego zestawu</span><span class="sxs-lookup"><span data-stu-id="b882d-116">Authorization: AddAuthorization overload moved to different assembly</span></span>](#authorization-addauthorization-overload-moved-to-different-assembly)
- [<span data-ttu-id="b882d-117">Autoryzacja: Usunięto IAllowAnonymous z AuthorizationFilterContext. filters</span><span class="sxs-lookup"><span data-stu-id="b882d-117">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [<span data-ttu-id="b882d-118">Autoryzacja: implementacje IAuthorizationPolicyProvider wymagają nowej metody</span><span class="sxs-lookup"><span data-stu-id="b882d-118">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [<span data-ttu-id="b882d-119">Autoryzacja: zasób w routingu punktu końcowego jest obiektem HttpContext</span><span class="sxs-lookup"><span data-stu-id="b882d-119">Authorization: Resource in endpoint routing is HttpContext</span></span>](#authorization-resource-in-endpoint-routing-is-httpcontext)
- [<span data-ttu-id="b882d-120">Azure: Usunięto wstępnie ustalone pakiety integracji platformy Azure</span><span class="sxs-lookup"><span data-stu-id="b882d-120">Azure: Microsoft-prefixed Azure integration packages removed</span></span>](#azure-microsoft-prefixed-azure-integration-packages-removed)
- [<span data-ttu-id="b882d-121">Metody serializacji BinaryFormatter są przestarzałe i zabronione w aplikacjach ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b882d-121">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps)
- [<span data-ttu-id="b882d-122">Blazor: nieznaczące odstępy są obcinane ze składników w czasie kompilacji</span><span class="sxs-lookup"><span data-stu-id="b882d-122">Blazor: Insignificant whitespace trimmed from components at compile time</span></span>](#blazor-insignificant-whitespace-trimmed-from-components-at-compile-time)
- [<span data-ttu-id="b882d-123">Blazor: typy JSObjectReference i JSInProcessObjectReference zmieniły się na Internal</span><span class="sxs-lookup"><span data-stu-id="b882d-123">Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal</span></span>](#blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal)
- [<span data-ttu-id="b882d-124">Blazor: funkcja ProtectedBrowserStorage została przeniesiona do platformy udostępnionej</span><span class="sxs-lookup"><span data-stu-id="b882d-124">Blazor: ProtectedBrowserStorage feature moved to shared framework</span></span>](#blazor-protectedbrowserstorage-feature-moved-to-shared-framework)
- [<span data-ttu-id="b882d-125">Blazor: RenderTreeFrame pola publiczne ReadOnly mają właściwości</span><span class="sxs-lookup"><span data-stu-id="b882d-125">Blazor: RenderTreeFrame readonly public fields have become properties</span></span>](#blazor-rendertreeframe-readonly-public-fields-have-become-properties)
- [<span data-ttu-id="b882d-126">Blazor: zmieniono platformę docelową pakietów NuGet</span><span class="sxs-lookup"><span data-stu-id="b882d-126">Blazor: Target framework of NuGet packages changed</span></span>](#blazor-target-framework-of-nuget-packages-changed)
- [<span data-ttu-id="b882d-127">Blazor: Zaktualizowano obsługę przeglądarki</span><span class="sxs-lookup"><span data-stu-id="b882d-127">Blazor: Updated browser support</span></span>](#blazor-updated-browser-support)
- [<span data-ttu-id="b882d-128">Blazor: Zaktualizowano logikę walidacji dla statycznych zasobów sieci Web</span><span class="sxs-lookup"><span data-stu-id="b882d-128">Blazor: Updated validation logic for static web assets</span></span>](#blazor-updated-validation-logic-for-static-web-assets)
- [<span data-ttu-id="b882d-129">Buforowanie: Usunięto Właściwość CompactOnMemoryPressure</span><span class="sxs-lookup"><span data-stu-id="b882d-129">Caching: CompactOnMemoryPressure property removed</span></span>](#caching-compactonmemorypressure-property-removed)
- [<span data-ttu-id="b882d-130">Buforowanie: Microsoft. Extensions. buforowanie. SqlServer używa nowego pakietu SqlClient</span><span class="sxs-lookup"><span data-stu-id="b882d-130">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [<span data-ttu-id="b882d-131">Buforowanie: typy ResponseCaching "pubternal" zostały zmienione na wewnętrzne</span><span class="sxs-lookup"><span data-stu-id="b882d-131">Caching: ResponseCaching "pubternal" types changed to internal</span></span>](#caching-responsecaching-pubternal-types-changed-to-internal)
- [<span data-ttu-id="b882d-132">Ochrona danych: dataprotection. obiekty blob używają nowych interfejsów API usługi Azure Storage</span><span class="sxs-lookup"><span data-stu-id="b882d-132">Data Protection: DataProtection.Blobs uses new Azure Storage APIs</span></span>](#data-protection-dataprotectionblobs-uses-new-azure-storage-apis)
- [<span data-ttu-id="b882d-133">Rozszerzenia: zmiany odwołania do pakietów wpływające na niektóre pakiety NuGet</span><span class="sxs-lookup"><span data-stu-id="b882d-133">Extensions: Package reference changes affecting some NuGet packages</span></span>](#extensions-package-reference-changes-affecting-some-nuget-packages)
- [<span data-ttu-id="b882d-134">Hosting: AspNetCoreModule V1 został usunięty z pakietu hostingu systemu Windows</span><span class="sxs-lookup"><span data-stu-id="b882d-134">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [<span data-ttu-id="b882d-135">Hosting: Host ogólny ogranicza iniekcję konstruktora startowego</span><span class="sxs-lookup"><span data-stu-id="b882d-135">Hosting: Generic host restricts Startup constructor injection</span></span>](#hosting-generic-host-restricts-startup-constructor-injection)
- [<span data-ttu-id="b882d-136">Hosting: włączono przekierowywanie protokołu HTTPS dla aplikacji pozaprocesowych usług IIS</span><span class="sxs-lookup"><span data-stu-id="b882d-136">Hosting: HTTPS redirection enabled for IIS out-of-process apps</span></span>](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [<span data-ttu-id="b882d-137">Hosting: zamieniono typy IHostingEnvironment i IApplicationLifetime</span><span class="sxs-lookup"><span data-stu-id="b882d-137">Hosting: IHostingEnvironment and IApplicationLifetime types replaced</span></span>](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="b882d-138">Hosting: ObjectPoolProvider usunięte z zależności WebHostBuilder</span><span class="sxs-lookup"><span data-stu-id="b882d-138">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [<span data-ttu-id="b882d-139">HTTP: Kestrel i IIS BadHttpRequestException typy oznaczone jako przestarzałe i zastąpione</span><span class="sxs-lookup"><span data-stu-id="b882d-139">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>](#http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="b882d-140">HTTP: zmiana SameSite w przeglądarce wpływa na uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="b882d-140">HTTP: Browser SameSite changes impact authentication</span></span>](#http-browser-samesite-changes-impact-authentication)
- [<span data-ttu-id="b882d-141">HTTP: Usunięto rozszerzalność DefaultHttpContext</span><span class="sxs-lookup"><span data-stu-id="b882d-141">HTTP: DefaultHttpContext extensibility removed</span></span>](#http-defaulthttpcontext-extensibility-removed)
- [<span data-ttu-id="b882d-142">HTTP: pola HeaderNames zostały zmienione na statyczny tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="b882d-142">HTTP: HeaderNames fields changed to static readonly</span></span>](#http-headernames-constants-changed-to-static-readonly)
- [<span data-ttu-id="b882d-143">HTTP: wystąpienia HttpClient utworzone przez kody stanu liczby całkowitej dziennika IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="b882d-143">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>](#http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes)
- [<span data-ttu-id="b882d-144">HTTP: zmiany infrastruktury treści odpowiedzi</span><span class="sxs-lookup"><span data-stu-id="b882d-144">HTTP: Response body infrastructure changes</span></span>](#http-response-body-infrastructure-changes)
- [<span data-ttu-id="b882d-145">HTTP: zmieniono domyślne wartości SameSite w pliku cookie</span><span class="sxs-lookup"><span data-stu-id="b882d-145">HTTP: Some cookie SameSite default values changed</span></span>](#http-some-cookie-samesite-defaults-changed-to-none)
- [<span data-ttu-id="b882d-146">HTTP: synchroniczne operacje we/wy są wyłączone domyślnie</span><span class="sxs-lookup"><span data-stu-id="b882d-146">HTTP: Synchronous IO disabled by default</span></span>](#http-synchronous-io-disabled-in-all-servers)
- [<span data-ttu-id="b882d-147">HttpSys: ponowne negocjowanie certyfikatu klienta jest wyłączone domyślnie</span><span class="sxs-lookup"><span data-stu-id="b882d-147">HttpSys: Client certificate renegotiation disabled by default</span></span>](#httpsys-client-certificate-renegotiation-disabled-by-default)
- [<span data-ttu-id="b882d-148">Tożsamość: Usunięto Przeciążenie metody AddDefaultUI</span><span class="sxs-lookup"><span data-stu-id="b882d-148">Identity: AddDefaultUI method overload removed</span></span>](#identity-adddefaultui-method-overload-removed)
- [<span data-ttu-id="b882d-149">Tożsamość: zmiana wersji ładowania początkowego interfejsu użytkownika</span><span class="sxs-lookup"><span data-stu-id="b882d-149">Identity: UI Bootstrap version change</span></span>](#identity-default-bootstrap-version-of-ui-changed)
- [<span data-ttu-id="b882d-150">Tożsamość: SignInAsync zgłasza wyjątek dla nieuwierzytelnionej tożsamości</span><span class="sxs-lookup"><span data-stu-id="b882d-150">Identity: SignInAsync throws exception for unauthenticated identity</span></span>](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [<span data-ttu-id="b882d-151">Tożsamość: Konstruktor SignInManager akceptuje nowy parametr</span><span class="sxs-lookup"><span data-stu-id="b882d-151">Identity: SignInManager constructor accepts new parameter</span></span>](#identity-signinmanager-constructor-accepts-new-parameter)
- [<span data-ttu-id="b882d-152">Tożsamość: interfejs użytkownika używa funkcji statyczne zasoby sieci Web</span><span class="sxs-lookup"><span data-stu-id="b882d-152">Identity: UI uses static web assets feature</span></span>](#identity-ui-uses-static-web-assets-feature)
- [<span data-ttu-id="b882d-153">IIS: UrlRewrite ciągi zapytania oprogramowania pośredniczącego są zachowywane</span><span class="sxs-lookup"><span data-stu-id="b882d-153">IIS: UrlRewrite middleware query strings are preserved</span></span>](#iis-urlrewrite-middleware-query-strings-are-preserved)
- [<span data-ttu-id="b882d-154">Kestrel: domyślnie wykryto zmiany konfiguracji w czasie wykonywania</span><span class="sxs-lookup"><span data-stu-id="b882d-154">Kestrel: Configuration changes at run time detected by default</span></span>](#kestrel-configuration-changes-at-run-time-detected-by-default)
- [<span data-ttu-id="b882d-155">Kestrel: Usunięto karty połączeń</span><span class="sxs-lookup"><span data-stu-id="b882d-155">Kestrel: Connection adapters removed</span></span>](#kestrel-connection-adapters-removed)
- [<span data-ttu-id="b882d-156">Kestrel: zmieniono domyślne wersje protokołu TLS</span><span class="sxs-lookup"><span data-stu-id="b882d-156">Kestrel: Default supported TLS protocol versions changed</span></span>](#kestrel-default-supported-tls-protocol-versions-changed)
- [<span data-ttu-id="b882d-157">Kestrel: Usunięto pusty zestaw HTTPS</span><span class="sxs-lookup"><span data-stu-id="b882d-157">Kestrel: Empty HTTPS assembly removed</span></span>](#kestrel-empty-https-assembly-removed)
- [<span data-ttu-id="b882d-158">Kestrel: protokół HTTP/2 został wyłączony przy użyciu protokołu TLS dla niezgodnych wersji systemu Windows</span><span class="sxs-lookup"><span data-stu-id="b882d-158">Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions</span></span>](#kestrel-http2-disabled-over-tls-on-incompatible-windows-versions)
- [<span data-ttu-id="b882d-159">Kestrel: transport Libuv oznaczony jako przestarzały</span><span class="sxs-lookup"><span data-stu-id="b882d-159">Kestrel: Libuv transport marked as obsolete</span></span>](#kestrel-libuv-transport-marked-as-obsolete)
- [<span data-ttu-id="b882d-160">Kestrel: przeniesiono nagłówki przyczepki do nowej kolekcji</span><span class="sxs-lookup"><span data-stu-id="b882d-160">Kestrel: Request trailer headers moved to new collection</span></span>](#kestrel-request-trailer-headers-moved-to-new-collection)
- [<span data-ttu-id="b882d-161">Kestrel: transportowe zmiany warstwy abstrakcji</span><span class="sxs-lookup"><span data-stu-id="b882d-161">Kestrel: Transport abstraction layer changes</span></span>](#kestrel-transport-abstractions-removed-and-made-public)
- [<span data-ttu-id="b882d-162">Lokalizacja: interfejsy API oznaczone jako przestarzałe</span><span class="sxs-lookup"><span data-stu-id="b882d-162">Localization: APIs marked obsolete</span></span>](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [<span data-ttu-id="b882d-163">Lokalizacja: Usunięto interfejsy API "Pubternal"</span><span class="sxs-lookup"><span data-stu-id="b882d-163">Localization: "Pubternal" APIs removed</span></span>](#localization-pubternal-apis-removed)
- [<span data-ttu-id="b882d-164">Lokalizacja: przestarzały Konstruktor został usunięty z oprogramowania pośredniczącego w lokalizacji żądania</span><span class="sxs-lookup"><span data-stu-id="b882d-164">Localization: Obsolete constructor removed in request localization middleware</span></span>](#localization-obsolete-constructor-removed-in-request-localization-middleware)
- [<span data-ttu-id="b882d-165">Lokalizacja: Usunięto klasę ResourceManagerWithCultureStringLocalizer i element członkowski interfejsu WithCulture</span><span class="sxs-lookup"><span data-stu-id="b882d-165">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>](#localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed)
- [<span data-ttu-id="b882d-166">Rejestrowanie: Klasa DebugLogger wykonana wewnętrznie</span><span class="sxs-lookup"><span data-stu-id="b882d-166">Logging: DebugLogger class made internal</span></span>](#logging-debuglogger-class-made-internal)
- [<span data-ttu-id="b882d-167">Oprogramowanie pośredniczące: Strona błędu bazy danych oznaczona jako przestarzała</span><span class="sxs-lookup"><span data-stu-id="b882d-167">Middleware: Database error page marked as obsolete</span></span>](#middleware-database-error-page-marked-as-obsolete)
- [<span data-ttu-id="b882d-168">Oprogramowanie pośredniczące: oprogramowanie pośredniczące obsługi wyjątków zgłasza oryginalny wyjątek, jeśli nie znaleziono procedury obsługi</span><span class="sxs-lookup"><span data-stu-id="b882d-168">Middleware: Exception Handler Middleware throws original exception if handler not found</span></span>](#middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found)
- [<span data-ttu-id="b882d-169">MVC: Usunięto sufiks asynchroniczny akcji kontrolera</span><span class="sxs-lookup"><span data-stu-id="b882d-169">MVC: Controller action Async suffix removed</span></span>](#mvc-async-suffix-trimmed-from-controller-action-names)
- [<span data-ttu-id="b882d-170">MVC: JsonResult przeniesiony do Microsoft. AspNetCore. MVC. Core</span><span class="sxs-lookup"><span data-stu-id="b882d-170">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [<span data-ttu-id="b882d-171">MVC: ObjectModelValidator wywołuje nowe Przeciążenie ValidationVisitor. Validate</span><span class="sxs-lookup"><span data-stu-id="b882d-171">MVC: ObjectModelValidator calls a new overload of ValidationVisitor.Validate</span></span>](#mvc-objectmodelvalidator-calls-a-new-overload-of-validationvisitorvalidate)
- [<span data-ttu-id="b882d-172">MVC: Narzędzie wstępnej kompilacji zostało zaniechane</span><span class="sxs-lookup"><span data-stu-id="b882d-172">MVC: Precompilation tool deprecated</span></span>](#mvc-precompilation-tool-deprecated)
- [<span data-ttu-id="b882d-173">MVC: zmieniono typy na wewnętrzne</span><span class="sxs-lookup"><span data-stu-id="b882d-173">MVC: Types changed to internal</span></span>](#mvc-pubternal-types-changed-to-internal)
- [<span data-ttu-id="b882d-174">MVC: Usunięto podkładkę zgodności z interfejsem API sieci Web</span><span class="sxs-lookup"><span data-stu-id="b882d-174">MVC: Web API compatibility shim removed</span></span>](#mvc-web-api-compatibility-shim-removed)
- [<span data-ttu-id="b882d-175">Razor: Usunięto interfejs API RazorTemplateEngine</span><span class="sxs-lookup"><span data-stu-id="b882d-175">Razor: RazorTemplateEngine API removed</span></span>](#razor-razortemplateengine-api-removed)
- [<span data-ttu-id="b882d-176">Razor: Kompilacja środowiska uruchomieniowego została przeniesiona do pakietu</span><span class="sxs-lookup"><span data-stu-id="b882d-176">Razor: Runtime compilation moved to a package</span></span>](#razor-runtime-compilation-moved-to-a-package)
- [<span data-ttu-id="b882d-177">Zabezpieczenia: kodowanie nazwy pliku cookie zostało usunięte</span><span class="sxs-lookup"><span data-stu-id="b882d-177">Security: Cookie name encoding removed</span></span>](#security-cookie-name-encoding-removed)
- [<span data-ttu-id="b882d-178">Bezpieczeństwo: Zaktualizowano wersje pakietów NuGet IdentityModel</span><span class="sxs-lookup"><span data-stu-id="b882d-178">Security: IdentityModel NuGet package versions updated</span></span>](#security-identitymodel-nuget-package-versions-updated)
- [<span data-ttu-id="b882d-179">Stan sesji: Usunięto przestarzałe interfejsy API</span><span class="sxs-lookup"><span data-stu-id="b882d-179">Session state: Obsolete APIs removed</span></span>](#session-state-obsolete-apis-removed)
- [<span data-ttu-id="b882d-180">Współdzielona struktura: usuwanie zestawu z Microsoft. AspNetCore. App</span><span class="sxs-lookup"><span data-stu-id="b882d-180">Shared framework: Assembly removal from Microsoft.AspNetCore.App</span></span>](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [<span data-ttu-id="b882d-181">Współdzielona struktura: Microsoft. AspNetCore. All usunięte</span><span class="sxs-lookup"><span data-stu-id="b882d-181">Shared framework: Microsoft.AspNetCore.All removed</span></span>](#shared-framework-removed-microsoftaspnetcoreall)
- [<span data-ttu-id="b882d-182">Sygnalizujący: HandshakeProtocol. SuccessHandshakeData został zastąpiony</span><span class="sxs-lookup"><span data-stu-id="b882d-182">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [<span data-ttu-id="b882d-183">Sygnalizacja: Usunięto metody HubConnection</span><span class="sxs-lookup"><span data-stu-id="b882d-183">SignalR: HubConnection methods removed</span></span>](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [<span data-ttu-id="b882d-184">Sygnalizacja: zmieniono konstruktory HubConnectionContext</span><span class="sxs-lookup"><span data-stu-id="b882d-184">SignalR: HubConnectionContext constructors changed</span></span>](#signalr-hubconnectioncontext-constructors-changed)
- [<span data-ttu-id="b882d-185">Sygnalizacja: zmiana nazwy pakietu klienta języka JavaScript</span><span class="sxs-lookup"><span data-stu-id="b882d-185">SignalR: JavaScript client package name change</span></span>](#signalr-javascript-client-package-name-changed)
- [<span data-ttu-id="b882d-186">Sygnalizacja: przeniesiono protokół MessagePack Hub do pakietu MessagePack 2. x</span><span class="sxs-lookup"><span data-stu-id="b882d-186">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>](#signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package)
- [<span data-ttu-id="b882d-187">Sygnalizacja: Zmieniono typ opcji protokołu MessagePack Hub</span><span class="sxs-lookup"><span data-stu-id="b882d-187">SignalR: MessagePack Hub Protocol options type changed</span></span>](#signalr-messagepack-hub-protocol-options-type-changed)
- [<span data-ttu-id="b882d-188">Sygnalizujący: przestarzałe interfejsy API</span><span class="sxs-lookup"><span data-stu-id="b882d-188">SignalR: Obsolete APIs</span></span>](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [<span data-ttu-id="b882d-189">Sygnalizacja: Usunięto metody UseSignalR i UseConnections</span><span class="sxs-lookup"><span data-stu-id="b882d-189">SignalR: UseSignalR and UseConnections methods removed</span></span>](#signalr-usesignalr-and-useconnections-methods-removed)
- [<span data-ttu-id="b882d-190">Aplikacji jednostronicowych: SpaServices i NodeServices domyślna zmiana ustawień rejestru</span><span class="sxs-lookup"><span data-stu-id="b882d-190">SPAs: SpaServices and NodeServices console logger fallback default change</span></span>](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [<span data-ttu-id="b882d-191">Aplikacji jednostronicowych: SpaServices i NodeServices oznaczone jako przestarzałe</span><span class="sxs-lookup"><span data-stu-id="b882d-191">SPAs: SpaServices and NodeServices marked obsolete</span></span>](#spas-spaservices-and-nodeservices-marked-obsolete)
- [<span data-ttu-id="b882d-192">Pliki statyczne: typ zawartości CSV został zmieniony na zgodny ze standardami</span><span class="sxs-lookup"><span data-stu-id="b882d-192">Static files: CSV content type changed to standards-compliant</span></span>](#static-files-csv-content-type-changed-to-standards-compliant)
- [<span data-ttu-id="b882d-193">Interfejsy API System. Security. Cryptography nie są obsługiwane w zestawie webassembly Blazor</span><span class="sxs-lookup"><span data-stu-id="b882d-193">System.Security.Cryptography APIs not supported on Blazor WebAssembly</span></span>](#systemsecuritycryptography-apis-not-supported-on-blazor-webassembly)
- [<span data-ttu-id="b882d-194">Platforma docelowa: nie .NET Framework obsługiwana</span><span class="sxs-lookup"><span data-stu-id="b882d-194">Target framework: .NET Framework not supported</span></span>](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-50"></a><span data-ttu-id="b882d-195">ASP.NET Core 5,0</span><span class="sxs-lookup"><span data-stu-id="b882d-195">ASP.NET Core 5.0</span></span>

[!INCLUDE[Authentication: AzureAD.UI and AzureADB2C.UI APIs and packages marked obsolete](~/includes/core-changes/aspnetcore/5.0/authentication-aad-packages-obsolete.md)]

***

[!INCLUDE[Authorization: Resource in endpoint routing is HttpContext](~/includes/core-changes/aspnetcore/5.0/authorization-resource-in-endpoint-routing.md)]

<span data-ttu-id="b882d-196">\*\*_</span><span class="sxs-lookup"><span data-stu-id="b882d-196">\*\*_</span></span>

[!INCLUDE[Azure: Microsoft-prefixed Azure integration packages removed](~/includes/core-changes/aspnetcore/5.0/azure-integration-packages-removed.md)]

_*_

[!INCLUDE[Serialization: BinaryFormatter serialization obsolete](~/includes/core-changes/corefx/5.0/binaryformatter-serialization-obsolete.md)]

_*_

[!INCLUDE[Blazor: Insignificant whitespace trimmed from components at compile time](~/includes/core-changes/aspnetcore/5.0/blazor-components-trim-insignificant-whitespace.md)]

_*_

[!INCLUDE[Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal](~/includes/core-changes/aspnetcore/5.0/blazor-jsobjectreference-to-internal.md)]

_*_

[!INCLUDE[Blazor: ProtectedBrowserStorage feature moved to shared framework](~/includes/core-changes/aspnetcore/5.0/blazor-protectedbrowserstorage-moved.md)]

_*_

[!INCLUDE[Blazor: RenderTreeFrame readonly public fields have become properties](~/includes/core-changes/aspnetcore/5.0/blazor-rendertreeframe-fields-become-properties.md)]

_*_

[!INCLUDE[Blazor: Target framework of NuGet packages changed](~/includes/core-changes/aspnetcore/5.0/blazor-packages-target-framework-changed.md)]

_*_

[!INCLUDE[Blazor: Updated browser support](~/includes/core-changes/aspnetcore/5.0/blazor-browser-support-updated.md)]

_*_

[!INCLUDE[Blazor: Static web assets validation logic updated](~/includes/core-changes/aspnetcore/5.0/blazor-static-web-assets-validation-logic-updated.md)]

_*_

[!INCLUDE[Extensions: Package reference changes](~/includes/core-changes/aspnetcore/5.0/extensions-package-reference-changes.md)]

_*_

[!INCLUDE[HTTP: HttpClient instances created by IHttpClientFactory log integer status codes](~/includes/core-changes/aspnetcore/5.0/http-httpclient-instances-log-integer-status-codes.md)]

_*_

[!INCLUDE[HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced](~/includes/core-changes/aspnetcore/5.0/http-badhttprequestexception-obsolete.md)]

_*_

[!INCLUDE[HttpSys: Client certificate renegotiation disabled by default](~/includes/core-changes/aspnetcore/5.0/httpsys-client-certificate-renegotiation-disabled-by-default.md)]

_*_

[!INCLUDE[IIS: UrlRewrite middleware query strings are preserved](~/includes/core-changes/aspnetcore/5.0/iis-urlrewrite-middleware-query-strings-are-preserved.md)]

_*_

[!INCLUDE[Kestrel: Configuration changes at run time detected by default](~/includes/core-changes/aspnetcore/5.0/kestrel-configuration-changes-at-run-time-detected-by-default.md)]

_*_
[!INCLUDE[Kestrel: Default supported TLS protocol versions changed](~/includes/core-changes/aspnetcore/5.0/kestrel-default-supported-tls-protocol-versions-changed.md)]

_*_

[!INCLUDE[Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions](~/includes/core-changes/aspnetcore/5.0/kestrel-disables-http2-over-tls.md)]

_*_

[!INCLUDE[Kestrel: Libuv transport marked as obsolete](~/includes/core-changes/aspnetcore/5.0/kestrel-libuv-transport-obsolete.md)]

_*_

[!INCLUDE[Localization: "Pubternal" APIs removed](~/includes/core-changes/aspnetcore/5.0/localization-pubternal-apis-removed.md)]

_*_

[!INCLUDE[Localization: Obsolete constructor removed in request localization middleware](~/includes/core-changes/aspnetcore/5.0/localization-requestlocalizationmiddleware-constructor-removed.md)]

_*_

[!INCLUDE[Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed](~/includes/core-changes/aspnetcore/5.0/localization-members-removed.md)]

_*_

[!INCLUDE[Middleware: Database error page marked as obsolete](~/includes/core-changes/aspnetcore/5.0/middleware-database-error-page-obsolete.md)]

_*_

[!INCLUDE[Middleware: Exception Handler Middleware throws original exception if handler not found](~/includes/core-changes/aspnetcore/5.0/middleware-exception-handler-throws-original-exception.md)]

_*_

[!INCLUDE[MVC: ObjectModelValidator calls a new overload of ValidationVisitor.Validate](~/includes/core-changes/aspnetcore/5.0/mvc-objectmodelvalidator-calls-new-overload.md)]

_*_

[!INCLUDE[Security: Cookie name encoding removed](~/includes/core-changes/aspnetcore/5.0/security-cookie-name-encoding-removed.md)]

_*_

[!INCLUDE[Security: IdentityModel NuGet package versions updated](~/includes/core-changes/aspnetcore/5.0/security-identitymodel-nuget-package-versions-updated.md)]

_*_

[!INCLUDE[SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-package.md)]

_*_

[!INCLUDE[SignalR: MessagePack Hub Protocol options type changed](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-hub-protocol-options-changed.md)]

_*_

[!INCLUDE[SignalR: UseSignalR and UseConnections methods removed](~/includes/core-changes/aspnetcore/5.0/signalr-usesignalr-useconnections-removed.md)]

_*_

[!INCLUDE[Cryptography APIs not supported on Blazor WebAssembly](~/includes/core-changes/cryptography/5.0/cryptography-apis-not-supported-on-blazor-webassembly.md)]

_*_

[!INCLUDE[Static files: CSV content type changed to standards-compliant](~/includes/core-changes/aspnetcore/5.0/static-files-csv-content-type-changed.md)]

_*_

## <a name="aspnet-core-31"></a><span data-ttu-id="b882d-197">ASP.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="b882d-197">ASP.NET Core 3.1</span></span>

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

_*_

## <a name="aspnet-core-30"></a><span data-ttu-id="b882d-198">ASP.NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="b882d-198">ASP.NET Core 3.0</span></span>

[!INCLUDE[Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed](~/includes/core-changes/aspnetcore/3.0/obsolete-apis-removed.md)]

_*_

[!INCLUDE[Authentication: Google+ deprecation](~/includes/core-changes/aspnetcore/3.0/authn-google-plus-authn-changes.md)]

_*_

[!INCLUDE[Authentication: HttpContext.Authentication property removed](~/includes/core-changes/aspnetcore/3.0/authn-httpcontext-property-removed.md)]

_*_

[!INCLUDE[Authentication: Newtonsoft.Json types replaced](~/includes/core-changes/aspnetcore/3.0/authn-apis-json-types.md)]

_*_

[!INCLUDE[Authentication: OAuthHandler ExchangeCodeAsync signature changed](~/includes/core-changes/aspnetcore/3.0/authn-exchangecodeasync-signature-change.md)]

_*_

[!INCLUDE[Authorization: AddAuthorization overload assembly change](~/includes/core-changes/aspnetcore/3.0/authz-assembly-change.md)]

_*_

[!INCLUDE[Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters](~/includes/core-changes/aspnetcore/3.0/authz-iallowanonymous-removed-from-collection.md)]

_*_

[!INCLUDE[Authorization: IAuthorizationPolicyProvider implementations require new method](~/includes/core-changes/aspnetcore/3.0/authz-iauthzpolicyprovider-new-method.md)]

_*_

[!INCLUDE[Caching: CompactOnMemoryPressure property removed](~/includes/core-changes/aspnetcore/3.0/caching-memory-property-removed.md)]

_*_

[!INCLUDE[Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package](~/includes/core-changes/aspnetcore/3.0/caching-new-sqlclient-package.md)]

_*_

[!INCLUDE[Caching: ResponseCaching types changed to internal](~/includes/core-changes/aspnetcore/3.0/caching-response-pubternal-to-internal.md)]

_*_

[!INCLUDE[Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs](~/includes/core-changes/aspnetcore/3.0/dataprotection-azstorage-using-azstorage-apis.md)]

_*_

[!INCLUDE[Hosting: ANCM version 1 removed from hosting bundle](~/includes/core-changes/aspnetcore/3.0/hosting-ancmv1-hosting-bundle-removal.md)]

_*_

[!INCLUDE[Hosting: Generic host restriction on Startup constructor injection](~/includes/core-changes/aspnetcore/3.0/hosting-generic-host-startup-ctor-restriction.md)]

_*_

[!INCLUDE[Hosting: HTTPS redirection enabled for IIS OutOfProcess](~/includes/core-changes/aspnetcore/3.0/hosting-https-redirection-iis-outofprocess.md)]

_*_

[!INCLUDE[Hosting: IHostingEnvironment and IApplicationLifetime types replaced](~/includes/core-changes/aspnetcore/3.0/hosting-ihostingenv-iapplifetime-types-replaced.md)]

_*_

[!INCLUDE[Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies](~/includes/core-changes/aspnetcore/3.0/hosting-objectpoolprovider-webhostbuilder-dependencies.md)]

_*_

[!INCLUDE[HTTP: DefaultHttpContext extensibility removed](~/includes/core-changes/aspnetcore/3.0/http-defaulthttpcontext-extensibility-removed.md)]

_*_

[!INCLUDE[HTTP: HeaderNames fields changed to static readonly](~/includes/core-changes/aspnetcore/3.0/http-headernames-constants-staticreadonly.md)]

_*_

[!INCLUDE[HTTP: Response body infrastructure changes](~/includes/core-changes/aspnetcore/3.0/http-response-body-changes.md)]

_*_

[!INCLUDE[HTTP: Some cookie SameSite default values changed](~/includes/core-changes/aspnetcore/3.0/http-cookie-samesite-defaults-change.md)]

_*_

[!INCLUDE[HTTP: Synchronous IO disabled by default](~/includes/core-changes/aspnetcore/3.0/http-synchronous-io-disabled.md)]

_*_

[!INCLUDE[Identity: AddDefaultUI method overload removed](~/includes/core-changes/aspnetcore/3.0/identity-ui-adddefaultui-overload-removed.md)]

_*_

[!INCLUDE[Identity: UI Bootstrap version change](~/includes/core-changes/aspnetcore/3.0/identity-ui-bootstrap-version.md)]

_*_

[!INCLUDE[Identity: SignInAsync throws exception for unauthenticated identity](~/includes/core-changes/aspnetcore/3.0/identity-signinasync-throws-exception.md)]

_*_

[!INCLUDE[Identity: SignInManager constructor accepts new parameter](~/includes/core-changes/aspnetcore/3.0/identity-signinmanager-ctor-parameter.md)]

_*_

[!INCLUDE[Identity: UI uses static web assets feature](~/includes/core-changes/aspnetcore/3.0/identity-ui-static-web-assets.md)]

_*_

[!INCLUDE[Kestrel: Connection adapters removed](~/includes/core-changes/aspnetcore/3.0/kestrel-connection-adapters-removed.md)]

_*_

[!INCLUDE[Kestrel: Empty HTTPS assembly removed](~/includes/core-changes/aspnetcore/3.0/kestrel-empty-assembly-removed.md)]

_*_

[!INCLUDE[Kestrel: Request trailer headers moved to new collection](~/includes/core-changes/aspnetcore/3.0/kestrel-request-trailer-headers.md)]

_*_

[!INCLUDE[Kestrel: Transport abstraction layer changes](~/includes/core-changes/aspnetcore/3.0/kestrel-transport-abstractions.md)]

_*_

[!INCLUDE[Localization: APIs marked obsolete](~/includes/core-changes/aspnetcore/3.0/localization-apis-marked-obsolete.md)]

_*_

[!INCLUDE[Logging: DebugLogger class made internal](~/includes/core-changes/aspnetcore/3.0/logging-debuglogger-to-internal.md)]

_*_

[!INCLUDE[MVC: Controller action Async suffix removed](~/includes/core-changes/aspnetcore/3.0/mvc-action-async-suffix-trimmed.md)]

_*_

[!INCLUDE[MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core](~/includes/core-changes/aspnetcore/3.0/mvc-jsonresult-moved.md)]

_*_

[!INCLUDE[MVC: Precompilation tool deprecated](~/includes/core-changes/aspnetcore/3.0/mvc-precompilation-tool-deprecated.md)]

_*_

[!INCLUDE[MVC: Types changed to internal](~/includes/core-changes/aspnetcore/3.0/mvc-pubternal-to-internal.md)]

_*_

[!INCLUDE[MVC: Web API compatibility shim removed](~/includes/core-changes/aspnetcore/3.0/mvc-webapi-compat-shim-removed.md)]

_*_

[!INCLUDE[Razor: RazorTemplatEengine API removed](~/includes/core-changes/aspnetcore/3.0/razor-razortemplateengine-api-removed.md)]

_*_

[!INCLUDE[Razor: Runtime compilation moved to a package](~/includes/core-changes/aspnetcore/3.0/razor-runtime-compilation-package.md)]

_*_

[!INCLUDE[Session state: Obsolete APIs removed](~/includes/core-changes/aspnetcore/3.0/session-obsolete-apis-removed.md)]

_*_

[!INCLUDE[Shared framework: Assembly removal from Microsoft.AspNetCore.App](~/includes/core-changes/aspnetcore/3.0/sharedfx-app-shared-framework-assemblies.md)]

_*_

[!INCLUDE[Shared framework: Microsoft.AspNetCore.All removed](~/includes/core-changes/aspnetcore/3.0/sharedfx-all-framework-removed.md)]

_*_

[!INCLUDE[SignalR: HandshakeProtocol.SuccessHandshakeData replaced](~/includes/core-changes/aspnetcore/3.0/signalr-successhandshakedata-replaced.md)]

_*_

[!INCLUDE[SignalR: HubConnection methods removed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnection-methods-removed.md)]

_*_

[!INCLUDE[SignalR: HubConnectionContext constructors changed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnectioncontext-ctors.md)]

_*_

[!INCLUDE[SignalR: JavaScript client package name change](~/includes/core-changes/aspnetcore/3.0/signalr-js-client-package-name.md)]

_*_

[!INCLUDE[SignalR: Obsolete APIs](~/includes/core-changes/aspnetcore/3.0/signalr-obsolete-apis.md)]

_*_

[!INCLUDE[SPAs: SpaServices and NodeServices marked obsolete](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-obsolete.md)]

_*_

[!INCLUDE[SPAs: SpaServices and NodeServices console logger fallback default change](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-fallback.md)]

_*_

[!INCLUDE[Target framework: .NET Framework not supported](~/includes/core-changes/aspnetcore/3.0/targetfx-netfx-tfm-support.md)]

<span data-ttu-id="b882d-199">_\*\*</span><span class="sxs-lookup"><span data-stu-id="b882d-199">_\*\*</span></span>
