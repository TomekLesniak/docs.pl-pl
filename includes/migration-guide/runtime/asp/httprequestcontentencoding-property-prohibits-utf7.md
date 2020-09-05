---
ms.openlocfilehash: cf34c5df1badcfd86d8a07bafdf1b759234712e0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497214"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="0908a-101">Właściwość HttpRequest. ContentEncoding zabrania UTF7</span><span class="sxs-lookup"><span data-stu-id="0908a-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

#### <a name="details"></a><span data-ttu-id="0908a-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="0908a-102">Details</span></span>

<span data-ttu-id="0908a-103">Począwszy od .NET Framework 4,5, kodowanie UTF-7 jest zabronione w <xref:System.Web.HttpRequest?displayProperty=fullName> treści "s".</span><span class="sxs-lookup"><span data-stu-id="0908a-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=fullName>s' bodies.</span></span> <span data-ttu-id="0908a-104">Dane dla aplikacji, które zależą od danych przychodzących w formacie UTF-7, nie będą poprawnie dekodowane w niektórych przypadkach.</span><span class="sxs-lookup"><span data-stu-id="0908a-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0908a-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="0908a-105">Suggestion</span></span>

<span data-ttu-id="0908a-106">W idealnym przypadku aplikacje należy zaktualizować tak, aby nie korzystały z kodowania UTF-7 w <xref:System.Web.HttpRequest?displayProperty=fullName> s.</span><span class="sxs-lookup"><span data-stu-id="0908a-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=fullName>s.</span></span> <span data-ttu-id="0908a-107">Alternatywnie można przywrócić starsze zachowanie przy użyciu <code>aspnet:AllowUtf7RequestContentEncoding</code> atrybutu [AppSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="0908a-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>

| <span data-ttu-id="0908a-108">Nazwa</span><span class="sxs-lookup"><span data-stu-id="0908a-108">Name</span></span>    | <span data-ttu-id="0908a-109">Wartość</span><span class="sxs-lookup"><span data-stu-id="0908a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0908a-110">Zakres</span><span class="sxs-lookup"><span data-stu-id="0908a-110">Scope</span></span>   |<span data-ttu-id="0908a-111">Edge</span><span class="sxs-lookup"><span data-stu-id="0908a-111">Edge</span></span>|
|<span data-ttu-id="0908a-112">Wersja</span><span class="sxs-lookup"><span data-stu-id="0908a-112">Version</span></span>|<span data-ttu-id="0908a-113">4.5</span><span class="sxs-lookup"><span data-stu-id="0908a-113">4.5</span></span>|
|<span data-ttu-id="0908a-114">Typ</span><span class="sxs-lookup"><span data-stu-id="0908a-114">Type</span></span>|<span data-ttu-id="0908a-115">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="0908a-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0908a-116">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="0908a-116">Affected APIs</span></span>

- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.ContentEncoding`

-->
