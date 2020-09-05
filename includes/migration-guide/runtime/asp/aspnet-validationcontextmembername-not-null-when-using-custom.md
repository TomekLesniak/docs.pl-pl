---
ms.openlocfilehash: 904a6abee2b4b2cf2f5727fb70e286c8a1a592c4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497279"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a><span data-ttu-id="c6af4-101">ASP.NET ValidationContext. MemberName nie ma wartości NULL w przypadku używania niestandardowych elementów DataAnnotation. ValidationAttribute</span><span class="sxs-lookup"><span data-stu-id="c6af4-101">ASP.NET ValidationContext.MemberName is not NULL when using custom DataAnnotations.ValidationAttribute</span></span>

#### <a name="details"></a><span data-ttu-id="c6af4-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="c6af4-102">Details</span></span>

<span data-ttu-id="c6af4-103">W .NET Framework 4.7.2 i starszych wersjach, w przypadku użycia niestandardowej <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> Właściwość zwraca `null` .</span><span class="sxs-lookup"><span data-stu-id="c6af4-103">In .NET Framework 4.7.2 and earlier versions, when using a custom <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>, the <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> property returns `null`.</span></span> <span data-ttu-id="c6af4-104">W wersji .NET Framework 4,8 wcześniejszej niż aktualizacja 2019 października zwróci nazwę elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="c6af4-104">In .NET Framework 4.8 version prior to the October 2019 update, it returns the member name.</span></span> <span data-ttu-id="c6af4-105">Począwszy od [.NET Framework października 2019 wersji zapoznawczej jakości](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) dla .NET Framework 4,8, domyślnie zwraca wartość `null` , ale można zrezygnować z zwracania nazwy elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="c6af4-105">Starting with [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) for .NET Framework 4.8, it returns `null` by default, but you can opt in to return the member name instead.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c6af4-106">Sugestia</span><span class="sxs-lookup"><span data-stu-id="c6af4-106">Suggestion</span></span>

<span data-ttu-id="c6af4-107">Dodaj następujące ustawienie do pliku *web.config* , aby Właściwość zwracała nazwę elementu członkowskiego w [.NET Framework października 2019 Preview zestawienia jakości](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) dla .NET Framework 4,8 i nowszych wersji:</span><span class="sxs-lookup"><span data-stu-id="c6af4-107">Add the following setting to your *web.config* file for the property to return the member name in [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) for .NET Framework 4.8 and later versions:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre><span data-ttu-id="c6af4-108">W wersji .NET Framework 4,8 wcześniejszej niż aktualizacja 2019 października, dodanie do pliku *web.config* przywraca poprzednie zachowanie i zwraca wartość właściwości `null` .</span><span class="sxs-lookup"><span data-stu-id="c6af4-108">In .NET Framework 4.8 version prior to the October 2019 update,  adding this to your *web.config* file restores the previous behavior and the property returns `null`.</span></span>

| <span data-ttu-id="c6af4-109">Nazwa</span><span class="sxs-lookup"><span data-stu-id="c6af4-109">Name</span></span>    | <span data-ttu-id="c6af4-110">Wartość</span><span class="sxs-lookup"><span data-stu-id="c6af4-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c6af4-111">Zakres</span><span class="sxs-lookup"><span data-stu-id="c6af4-111">Scope</span></span>   |<span data-ttu-id="c6af4-112">Nieznane</span><span class="sxs-lookup"><span data-stu-id="c6af4-112">Unknown</span></span>|
|<span data-ttu-id="c6af4-113">Wersja</span><span class="sxs-lookup"><span data-stu-id="c6af4-113">Version</span></span>|<span data-ttu-id="c6af4-114">4,8</span><span class="sxs-lookup"><span data-stu-id="c6af4-114">4.8</span></span>|
|<span data-ttu-id="c6af4-115">Typ</span><span class="sxs-lookup"><span data-stu-id="c6af4-115">Type</span></span>|<span data-ttu-id="c6af4-116">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="c6af4-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c6af4-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="c6af4-117">Affected APIs</span></span>

- <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.ComponentModel.DataAnnotations.ValidationContext.MemberName`

-->
