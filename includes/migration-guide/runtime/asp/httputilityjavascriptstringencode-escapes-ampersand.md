---
ms.openlocfilehash: b648aee35ff44730f545f0fa06f4e0a86615dece
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606263"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="66c5d-101">HttpUtility. JavaScriptStringEncode — ucieczki</span><span class="sxs-lookup"><span data-stu-id="66c5d-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

#### <a name="details"></a><span data-ttu-id="66c5d-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="66c5d-102">Details</span></span>

<span data-ttu-id="66c5d-103">Począwszy od .NET Framework 4,5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> wyprowadza znak handlowego "i" ( &amp; ).</span><span class="sxs-lookup"><span data-stu-id="66c5d-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> escapes the ampersand (&amp;) character.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="66c5d-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="66c5d-104">Suggestion</span></span>

<span data-ttu-id="66c5d-105">Jeśli aplikacja zależy od poprzedniego zachowania tej metody, można dodać ustawienie ASPNET: JavaScriptDoNotEncodeAmpersand do [elementu appSettings ASP.NET](/previous-versions/aspnet/hh975440(v=vs.120)) w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="66c5d-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>

| <span data-ttu-id="66c5d-106">Nazwa</span><span class="sxs-lookup"><span data-stu-id="66c5d-106">Name</span></span>    | <span data-ttu-id="66c5d-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="66c5d-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="66c5d-108">Zakres</span><span class="sxs-lookup"><span data-stu-id="66c5d-108">Scope</span></span>   |<span data-ttu-id="66c5d-109">Mały</span><span class="sxs-lookup"><span data-stu-id="66c5d-109">Minor</span></span>|
|<span data-ttu-id="66c5d-110">Wersja</span><span class="sxs-lookup"><span data-stu-id="66c5d-110">Version</span></span>|<span data-ttu-id="66c5d-111">4.5</span><span class="sxs-lookup"><span data-stu-id="66c5d-111">4.5</span></span>|
|<span data-ttu-id="66c5d-112">Typ</span><span class="sxs-lookup"><span data-stu-id="66c5d-112">Type</span></span>|<span data-ttu-id="66c5d-113">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="66c5d-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="66c5d-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="66c5d-114">Affected APIs</span></span>

- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String)`
- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)`

-->
