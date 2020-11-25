---
title: 'Nieprzerwana zmiana: oprogramowanie pośredniczące: oprogramowanie pośredniczące programu obsługi wyjątków zgłasza oryginalny wyjątek, jeśli nie znaleziono procedury obsługi'
description: 'Dowiedz się więcej o istotnej zmianie w ASP.NET Core 5,0 zatytułowanym oprogramowanie pośredniczące: oprogramowanie pośredniczące programu obsługi wyjątków zgłasza oryginalny wyjątek, jeśli nie znaleziono procedury obsługi'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 8801d3e6950d66fd9f24e051fd8729c50eb0b282
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761656"
---
# <a name="middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found"></a><span data-ttu-id="0f741-103">Oprogramowanie pośredniczące: oprogramowanie pośredniczące obsługi wyjątków zgłasza oryginalny wyjątek, jeśli nie znaleziono procedury obsługi</span><span class="sxs-lookup"><span data-stu-id="0f741-103">Middleware: Exception Handler Middleware throws original exception if handler not found</span></span>

<span data-ttu-id="0f741-104">Przed ASP.NET Core 5,0, [oprogramowanie pośredniczące obsługi wyjątków](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) wykonuje skonfigurowany program obsługi wyjątków, gdy wystąpił wyjątek.</span><span class="sxs-lookup"><span data-stu-id="0f741-104">Before ASP.NET Core 5.0, the [Exception Handler Middleware](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) executes the configured exception handler when an exception has occurred.</span></span> <span data-ttu-id="0f741-105">Jeśli program obsługi wyjątków skonfigurowany za pośrednictwem <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath> nie zostanie znaleziony, zostanie wygenerowana odpowiedź HTTP 404.</span><span class="sxs-lookup"><span data-stu-id="0f741-105">If the exception handler, configured via <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath>, can't be found, an HTTP 404 response is produced.</span></span> <span data-ttu-id="0f741-106">Odpowiedź jest myląca w ten sposób:</span><span class="sxs-lookup"><span data-stu-id="0f741-106">The response is misleading in that it:</span></span>

* <span data-ttu-id="0f741-107">Prawdopodobnie jest to błąd użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0f741-107">Seems to be a user error.</span></span>
* <span data-ttu-id="0f741-108">Zasłania fakt, że na serwerze wystąpił wyjątek.</span><span class="sxs-lookup"><span data-stu-id="0f741-108">Obscures the fact that an exception occurred on the server.</span></span>

<span data-ttu-id="0f741-109">Aby rozwiązać błąd mylący w ASP.NET Core 5,0, `ExceptionHandlerMiddleware` zgłasza oryginalny wyjątek, jeśli nie można odnaleźć programu obsługi wyjątków.</span><span class="sxs-lookup"><span data-stu-id="0f741-109">To address the misleading error in ASP.NET Core 5.0, the `ExceptionHandlerMiddleware` throws the original exception if the exception handler can't be found.</span></span> <span data-ttu-id="0f741-110">W związku z tym serwer jest generowany odpowiedzi HTTP 500.</span><span class="sxs-lookup"><span data-stu-id="0f741-110">As a result, an HTTP 500 response is produced by the server.</span></span> <span data-ttu-id="0f741-111">Odpowiedź będzie łatwiejsza do sprawdzenia w dziennikach serwera podczas debugowania błędu, który wystąpił.</span><span class="sxs-lookup"><span data-stu-id="0f741-111">The response will be easier to examine in the server logs when debugging the error that occurred.</span></span>

<span data-ttu-id="0f741-112">Aby zapoznać się z omówieniem, zobacz sekcję dotyczącą usługi GitHub wydaj [/aspnetcore # 25288](https://github.com/dotnet/aspnetcore/issues/25288).</span><span class="sxs-lookup"><span data-stu-id="0f741-112">For discussion, see GitHub issue [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="0f741-113">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="0f741-113">Version introduced</span></span>

<span data-ttu-id="0f741-114">5,0 RC 1</span><span class="sxs-lookup"><span data-stu-id="0f741-114">5.0 RC 1</span></span>

## <a name="old-behavior"></a><span data-ttu-id="0f741-115">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="0f741-115">Old behavior</span></span>

<span data-ttu-id="0f741-116">Oprogramowanie pośredniczące obsługi wyjątków generuje odpowiedź HTTP 404, jeśli nie można znaleźć skonfigurowanej procedury obsługi wyjątków.</span><span class="sxs-lookup"><span data-stu-id="0f741-116">The Exception Handler Middleware produces an HTTP 404 response if the configured exception handler can't be found.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="0f741-117">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="0f741-117">New behavior</span></span>

<span data-ttu-id="0f741-118">Oprogramowanie pośredniczące obsługi wyjątków zgłasza oryginalny wyjątek, jeśli nie można odnaleźć skonfigurowanej procedury obsługi wyjątków.</span><span class="sxs-lookup"><span data-stu-id="0f741-118">The Exception Handler Middleware throws the original exception if the configured exception handler can't be found.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="0f741-119">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="0f741-119">Reason for change</span></span>

<span data-ttu-id="0f741-120">Błąd HTTP 404 nie sprawiają, że na serwerze wystąpił wyjątek.</span><span class="sxs-lookup"><span data-stu-id="0f741-120">The HTTP 404 error doesn't make it obvious that an exception occurred on the server.</span></span> <span data-ttu-id="0f741-121">Ta zmiana powoduje błąd HTTP 500, aby oczywiste, że:</span><span class="sxs-lookup"><span data-stu-id="0f741-121">This change produces an HTTP 500 error to make it obvious that:</span></span>

* <span data-ttu-id="0f741-122">Problem nie jest spowodowany błędem użytkownika.</span><span class="sxs-lookup"><span data-stu-id="0f741-122">The problem isn't caused by a user error.</span></span>
* <span data-ttu-id="0f741-123">Na serwerze wystąpił wyjątek.</span><span class="sxs-lookup"><span data-stu-id="0f741-123">An exception was encountered on the server.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="0f741-124">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="0f741-124">Recommended action</span></span>

<span data-ttu-id="0f741-125">Brak zmian interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="0f741-125">There are no API changes.</span></span> <span data-ttu-id="0f741-126">Wszystkie istniejące aplikacje będą nadal kompilowane i uruchamiane.</span><span class="sxs-lookup"><span data-stu-id="0f741-126">All existing apps will continue to compile and run.</span></span> <span data-ttu-id="0f741-127">Zgłoszony wyjątek jest obsługiwany przez serwer.</span><span class="sxs-lookup"><span data-stu-id="0f741-127">The exception thrown is handled by the server.</span></span> <span data-ttu-id="0f741-128">Na przykład wyjątek jest konwertowany na odpowiedź na błąd HTTP 500 przez [Kestrel](/aspnet/core/fundamentals/servers/kestrel) lub [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys).</span><span class="sxs-lookup"><span data-stu-id="0f741-128">For example, the exception is converted to an HTTP 500 error response by [Kestrel](/aspnet/core/fundamentals/servers/kestrel) or [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="0f741-129">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="0f741-129">Affected APIs</span></span>

<span data-ttu-id="0f741-130">Brak</span><span class="sxs-lookup"><span data-stu-id="0f741-130">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
