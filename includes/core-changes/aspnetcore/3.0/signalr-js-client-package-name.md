---
ms.openlocfilehash: f202b39f1a45f740625827be25e72df0e403d605
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901746"
---
### <a name="signalr-javascript-client-package-name-changed"></a><span data-ttu-id="fa618-101">Sygnalizacja: zmieniono nazwę pakietu klienta języka JavaScript</span><span class="sxs-lookup"><span data-stu-id="fa618-101">SignalR: JavaScript client package name changed</span></span>

<span data-ttu-id="fa618-102">W programie ASP.NET Core 3,0 w wersji zapoznawczej 7 nazwa pakietu klienta języka JavaScript została zmieniona z `@aspnet/signalr` na `@microsoft/signalr` .</span><span class="sxs-lookup"><span data-stu-id="fa618-102">In ASP.NET Core 3.0 Preview 7, the SignalR JavaScript client package name changed from `@aspnet/signalr` to `@microsoft/signalr`.</span></span> <span data-ttu-id="fa618-103">Zmiana nazwy odzwierciedla fakt, że sygnalizujący jest przydatny w więcej niż zaledwie ASP.NET Core aplikacji, dzięki usłudze Azure Signal Service.</span><span class="sxs-lookup"><span data-stu-id="fa618-103">The name change reflects the fact that SignalR is useful in more than just ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

<span data-ttu-id="fa618-104">Aby reagować na tę zmianę, Zmień odwołania w *package.jsw* plikach, `require` instrukcjach i `import` instrukcjach języka ECMAScript.</span><span class="sxs-lookup"><span data-stu-id="fa618-104">To react to this change, change references in your *package.json* files, `require` statements, and ECMAScript `import` statements.</span></span> <span data-ttu-id="fa618-105">W ramach tej zmiany nazwy nie zostanie zmieniony żaden interfejs API.</span><span class="sxs-lookup"><span data-stu-id="fa618-105">No API will change as part of this rename.</span></span>

<span data-ttu-id="fa618-106">Aby zapoznać się z omówieniem, zobacz [dotnet/aspnetcore # 11637](https://github.com/dotnet/aspnetcore/issues/11637).</span><span class="sxs-lookup"><span data-stu-id="fa618-106">For discussion, see [dotnet/aspnetcore#11637](https://github.com/dotnet/aspnetcore/issues/11637).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="fa618-107">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="fa618-107">Version introduced</span></span>

<span data-ttu-id="fa618-108">3,0</span><span class="sxs-lookup"><span data-stu-id="fa618-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="fa618-109">Stare zachowanie</span><span class="sxs-lookup"><span data-stu-id="fa618-109">Old behavior</span></span>

<span data-ttu-id="fa618-110">Pakiet klienta został nazwany `@aspnet/signalr` .</span><span class="sxs-lookup"><span data-stu-id="fa618-110">The client package was named `@aspnet/signalr`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="fa618-111">Nowe zachowanie</span><span class="sxs-lookup"><span data-stu-id="fa618-111">New behavior</span></span>

<span data-ttu-id="fa618-112">Pakiet klienta ma nazwę `@microsoft/signalr` .</span><span class="sxs-lookup"><span data-stu-id="fa618-112">The client package is named `@microsoft/signalr`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="fa618-113">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="fa618-113">Reason for change</span></span>

<span data-ttu-id="fa618-114">Zmiana nazwy objaśnia, że sygnalizujący jest przydatne poza ASP.NET Core aplikacjami, dzięki usłudze Azure Signal Service.</span><span class="sxs-lookup"><span data-stu-id="fa618-114">The name change clarifies that SignalR is useful beyond ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="fa618-115">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="fa618-115">Recommended action</span></span>

<span data-ttu-id="fa618-116">Przejdź do nowego pakietu `@microsoft/signalr` .</span><span class="sxs-lookup"><span data-stu-id="fa618-116">Switch to the new package `@microsoft/signalr`.</span></span>

#### <a name="category"></a><span data-ttu-id="fa618-117">Kategoria</span><span class="sxs-lookup"><span data-stu-id="fa618-117">Category</span></span>

<span data-ttu-id="fa618-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="fa618-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="fa618-119">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="fa618-119">Affected APIs</span></span>

<span data-ttu-id="fa618-120">Brak</span><span class="sxs-lookup"><span data-stu-id="fa618-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
