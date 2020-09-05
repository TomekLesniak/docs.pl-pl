---
ms.openlocfilehash: 12fb72d5ee9fc0d6c57899589cb2b0da7db41f4a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496296"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="ce84f-101">HttpUtility. JavaScriptStringEncode — ucieczki</span><span class="sxs-lookup"><span data-stu-id="ce84f-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

#### <a name="details"></a><span data-ttu-id="ce84f-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="ce84f-102">Details</span></span>

<span data-ttu-id="ce84f-103">Począwszy od .NET Framework 4,5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> wyprowadza znak handlowego "i" ( &amp; ).</span><span class="sxs-lookup"><span data-stu-id="ce84f-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> escapes the ampersand (&amp;) character.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ce84f-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="ce84f-104">Suggestion</span></span>

<span data-ttu-id="ce84f-105">Jeśli aplikacja zależy od poprzedniego zachowania tej metody, można dodać ustawienie ASPNET: JavaScriptDoNotEncodeAmpersand do [elementu appSettings ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="ce84f-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>

| <span data-ttu-id="ce84f-106">Nazwa</span><span class="sxs-lookup"><span data-stu-id="ce84f-106">Name</span></span>    | <span data-ttu-id="ce84f-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="ce84f-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ce84f-108">Zakres</span><span class="sxs-lookup"><span data-stu-id="ce84f-108">Scope</span></span>   |<span data-ttu-id="ce84f-109">Mały</span><span class="sxs-lookup"><span data-stu-id="ce84f-109">Minor</span></span>|
|<span data-ttu-id="ce84f-110">Wersja</span><span class="sxs-lookup"><span data-stu-id="ce84f-110">Version</span></span>|<span data-ttu-id="ce84f-111">4.5</span><span class="sxs-lookup"><span data-stu-id="ce84f-111">4.5</span></span>|
|<span data-ttu-id="ce84f-112">Typ</span><span class="sxs-lookup"><span data-stu-id="ce84f-112">Type</span></span>|<span data-ttu-id="ce84f-113">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="ce84f-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ce84f-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="ce84f-114">Affected APIs</span></span>

- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String)`
- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)`

-->
