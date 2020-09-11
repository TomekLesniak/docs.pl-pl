---
ms.openlocfilehash: 26e521a86b504824f035ad5d40e4a04d2ea26abc
ms.sourcegitcommit: 6d4ee46871deb9ea1e45bb5f3784474e240bbc26
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/11/2020
ms.locfileid: "90022973"
---
### <a name="middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found"></a><span data-ttu-id="cc359-101">Oprogramowanie pośredniczące: oprogramowanie pośredniczące obsługi wyjątków zgłasza oryginalny wyjątek, jeśli nie znaleziono procedury obsługi</span><span class="sxs-lookup"><span data-stu-id="cc359-101">Middleware: Exception Handler Middleware throws original exception if handler not found</span></span>

<span data-ttu-id="cc359-102">Przed ASP.NET Core 5,0, [oprogramowanie pośredniczące obsługi wyjątków](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) wykonuje skonfigurowany program obsługi wyjątków, gdy wystąpił wyjątek.</span><span class="sxs-lookup"><span data-stu-id="cc359-102">Before ASP.NET Core 5.0, the [Exception Handler Middleware](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) executes the configured exception handler when an exception has occurred.</span></span> <span data-ttu-id="cc359-103">Jeśli program obsługi wyjątków skonfigurowany za pośrednictwem <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath> nie zostanie znaleziony, zostanie wygenerowana odpowiedź HTTP 404.</span><span class="sxs-lookup"><span data-stu-id="cc359-103">If the exception handler, configured via <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath>, can't be found, an HTTP 404 response is produced.</span></span> <span data-ttu-id="cc359-104">Odpowiedź jest myląca w ten sposób:</span><span class="sxs-lookup"><span data-stu-id="cc359-104">The response is misleading in that it:</span></span>

* <span data-ttu-id="cc359-105">Prawdopodobnie jest to błąd użytkownika.</span><span class="sxs-lookup"><span data-stu-id="cc359-105">Seems to be a user error.</span></span>
* <span data-ttu-id="cc359-106">Zasłania fakt, że na serwerze wystąpił wyjątek.</span><span class="sxs-lookup"><span data-stu-id="cc359-106">Obscures the fact that an exception occurred on the server.</span></span>

<span data-ttu-id="cc359-107">Aby rozwiązać błąd mylący w ASP.NET Core 5,0, `ExceptionHandlerMiddleware` zgłasza oryginalny wyjątek, jeśli nie można odnaleźć programu obsługi wyjątków.</span><span class="sxs-lookup"><span data-stu-id="cc359-107">To address the misleading error in ASP.NET Core 5.0, the `ExceptionHandlerMiddleware` throws the original exception if the exception handler can't be found.</span></span> <span data-ttu-id="cc359-108">W związku z tym serwer jest generowany odpowiedzi HTTP 500.</span><span class="sxs-lookup"><span data-stu-id="cc359-108">As a result, an HTTP 500 response is produced by the server.</span></span> <span data-ttu-id="cc359-109">Odpowiedź będzie łatwiejsza do sprawdzenia w dziennikach serwera podczas debugowania błędu, który wystąpił.</span><span class="sxs-lookup"><span data-stu-id="cc359-109">The response will be easier to examine in the server logs when debugging the error that occurred.</span></span>

<span data-ttu-id="cc359-110">Aby zapoznać się z omówieniem, zobacz sekcję dotyczącą usługi GitHub wydaj [/aspnetcore # 25288](https://github.com/dotnet/aspnetcore/issues/25288).</span><span class="sxs-lookup"><span data-stu-id="cc359-110">For discussion, see GitHub issue [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cc359-111">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="cc359-111">Version introduced</span></span>

<span data-ttu-id="cc359-112">5,0 RC 1</span><span class="sxs-lookup"><span data-stu-id="cc359-112">5.0 RC 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="cc359-113">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="cc359-113">Old behavior</span></span>

<span data-ttu-id="cc359-114">Oprogramowanie pośredniczące obsługi wyjątków generuje odpowiedź HTTP 404, jeśli nie można znaleźć skonfigurowanej procedury obsługi wyjątków.</span><span class="sxs-lookup"><span data-stu-id="cc359-114">The Exception Handler Middleware produces an HTTP 404 response if the configured exception handler can't be found.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="cc359-115">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="cc359-115">New behavior</span></span>

<span data-ttu-id="cc359-116">Oprogramowanie pośredniczące obsługi wyjątków zgłasza oryginalny wyjątek, jeśli nie można odnaleźć skonfigurowanej procedury obsługi wyjątków.</span><span class="sxs-lookup"><span data-stu-id="cc359-116">The Exception Handler Middleware throws the original exception if the configured exception handler can't be found.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="cc359-117">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="cc359-117">Reason for change</span></span>

<span data-ttu-id="cc359-118">Błąd HTTP 404 nie sprawiają, że na serwerze wystąpił wyjątek.</span><span class="sxs-lookup"><span data-stu-id="cc359-118">The HTTP 404 error doesn't make it obvious that an exception occurred on the server.</span></span> <span data-ttu-id="cc359-119">Ta zmiana powoduje błąd HTTP 500, aby oczywiste, że:</span><span class="sxs-lookup"><span data-stu-id="cc359-119">This change produces an HTTP 500 error to make it obvious that:</span></span>

* <span data-ttu-id="cc359-120">Problem nie jest spowodowany błędem użytkownika.</span><span class="sxs-lookup"><span data-stu-id="cc359-120">The problem isn't caused by a user error.</span></span>
* <span data-ttu-id="cc359-121">Na serwerze wystąpił wyjątek.</span><span class="sxs-lookup"><span data-stu-id="cc359-121">An exception was encountered on the server.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cc359-122">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="cc359-122">Recommended action</span></span>

<span data-ttu-id="cc359-123">Brak zmian interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="cc359-123">There are no API changes.</span></span> <span data-ttu-id="cc359-124">Wszystkie istniejące aplikacje będą nadal kompilowane i uruchamiane.</span><span class="sxs-lookup"><span data-stu-id="cc359-124">All existing apps will continue to compile and run.</span></span> <span data-ttu-id="cc359-125">Zgłoszony wyjątek jest obsługiwany przez serwer.</span><span class="sxs-lookup"><span data-stu-id="cc359-125">The exception thrown is handled by the server.</span></span> <span data-ttu-id="cc359-126">Na przykład wyjątek jest konwertowany na odpowiedź na błąd HTTP 500 przez [Kestrel](/aspnet/core/fundamentals/servers/kestrel) lub [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys).</span><span class="sxs-lookup"><span data-stu-id="cc359-126">For example, the exception is converted to an HTTP 500 error response by [Kestrel](/aspnet/core/fundamentals/servers/kestrel) or [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys).</span></span>

#### <a name="category"></a><span data-ttu-id="cc359-127">Kategoria</span><span class="sxs-lookup"><span data-stu-id="cc359-127">Category</span></span>

<span data-ttu-id="cc359-128">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cc359-128">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cc359-129">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="cc359-129">Affected APIs</span></span>

<span data-ttu-id="cc359-130">Brak</span><span class="sxs-lookup"><span data-stu-id="cc359-130">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
