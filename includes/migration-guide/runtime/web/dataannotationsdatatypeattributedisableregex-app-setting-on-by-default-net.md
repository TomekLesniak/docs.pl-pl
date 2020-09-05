---
ms.openlocfilehash: 0d38e2177377e7e9ea911071eb65aa13aa1f5900
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496675"
---
### <a name="dataannotationsdatatypeattributedisableregex-app-setting-is-on-by-default-in-net-framework-472"></a><span data-ttu-id="4bd63-101">ustawienie aplikacji "DataAnnotations: DataTypeAttribute: disableRegEx" jest domyślnie włączone w .NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="4bd63-101">"dataAnnotations:dataTypeAttribute:disableRegEx" app setting is on by default in .NET Framework 4.7.2</span></span>

#### <a name="details"></a><span data-ttu-id="4bd63-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="4bd63-102">Details</span></span>

<span data-ttu-id="4bd63-103">W .NET Framework 4.6.1 wprowadzono ustawienie aplikacji ( <code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code> ), które umożliwia użytkownikom wyłączenie używania wyrażeń regularnych w atrybutach typu danych (takich jak <xref:System.ComponentModel.DataAnnotations.EmailAddressAttribute?displayProperty=nameWithType> , <xref:System.ComponentModel.DataAnnotations.UrlAttribute?displayProperty=nameWithType> , i <xref:System.ComponentModel.DataAnnotations.PhoneAttribute?displayProperty=nameWithType> ).</span><span class="sxs-lookup"><span data-stu-id="4bd63-103">In .NET Framework 4.6.1, an app setting (<code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code>) was introduced that allows users to disable the use of regular expressions in data type attributes (such as <xref:System.ComponentModel.DataAnnotations.EmailAddressAttribute?displayProperty=nameWithType>, <xref:System.ComponentModel.DataAnnotations.UrlAttribute?displayProperty=nameWithType>, and <xref:System.ComponentModel.DataAnnotations.PhoneAttribute?displayProperty=nameWithType>).</span></span> <span data-ttu-id="4bd63-104">Dzięki temu można zmniejszyć luki w zabezpieczeniach, takie jak uniknięcie ataku typu "odmowa usługi" przy użyciu określonych wyrażeń regularnych.</span><span class="sxs-lookup"><span data-stu-id="4bd63-104">This helps to reduce security vulnerability such as avoiding the possibility of a Denial of Service attack using specific regular expressions.</span></span><br/><span data-ttu-id="4bd63-105">W .NET Framework 4.6.1 to ustawienie aplikacji wyłączające użycie wyrażenia regularnego zostało domyślnie ustawione na wartość <code>false</code> .</span><span class="sxs-lookup"><span data-stu-id="4bd63-105">In .NET Framework 4.6.1, this app setting to disable RegEx usage was set to <code>false</code> by default.</span></span> <span data-ttu-id="4bd63-106">Począwszy od .NET Framework 4.7.2, ten przełącznik konfiguracji jest domyślnie ustawiany, <code>true</code> Aby dodatkowo ograniczyć bezpieczną lukę w zabezpieczeniach aplikacji sieci Web przeznaczonych .NET Framework 4.7.2 i powyżej.</span><span class="sxs-lookup"><span data-stu-id="4bd63-106">Starting with .NET Framework 4.7.2, this config switch is set to <code>true</code> by default to further reduce secure vulnerability for web applications that target .NET Framework 4.7.2 and above.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4bd63-107">Sugestia</span><span class="sxs-lookup"><span data-stu-id="4bd63-107">Suggestion</span></span>

<span data-ttu-id="4bd63-108">Jeśli okaże się, że wyrażenia regularne w aplikacji sieci Web nie działają po uaktualnieniu do .NET Framework 4.7.2, można zaktualizować wartość <code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code> Ustawienia, aby <code>false</code> przywrócić poprzednie zachowanie.</span><span class="sxs-lookup"><span data-stu-id="4bd63-108">If you find that regular expressions in your web application do not work after upgrading to .NET Framework 4.7.2, you can update the value of the <code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code> setting to <code>false</code> to revert to the previous behavior.</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot; value=&quot;false&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="4bd63-109">Nazwa</span><span class="sxs-lookup"><span data-stu-id="4bd63-109">Name</span></span>    | <span data-ttu-id="4bd63-110">Wartość</span><span class="sxs-lookup"><span data-stu-id="4bd63-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4bd63-111">Zakres</span><span class="sxs-lookup"><span data-stu-id="4bd63-111">Scope</span></span>   |<span data-ttu-id="4bd63-112">Mały</span><span class="sxs-lookup"><span data-stu-id="4bd63-112">Minor</span></span>|
|<span data-ttu-id="4bd63-113">Wersja</span><span class="sxs-lookup"><span data-stu-id="4bd63-113">Version</span></span>|<span data-ttu-id="4bd63-114">4.7.2</span><span class="sxs-lookup"><span data-stu-id="4bd63-114">4.7.2</span></span>|
|<span data-ttu-id="4bd63-115">Typ</span><span class="sxs-lookup"><span data-stu-id="4bd63-115">Type</span></span>|<span data-ttu-id="4bd63-116">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="4bd63-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="4bd63-117">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="4bd63-117">Affected APIs</span></span>

<span data-ttu-id="4bd63-118">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="4bd63-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
