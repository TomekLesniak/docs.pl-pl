---
ms.openlocfilehash: 0c3876d30a80501a89f3a37ce24e2f71122c1b44
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497209"
---
### <a name="systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a><span data-ttu-id="d2502-101">Obiekt System. ServiceModel. Web. WebServiceHost nie dodaje już domyślnego punktu końcowego</span><span class="sxs-lookup"><span data-stu-id="d2502-101">System.ServiceModel.Web.WebServiceHost object no longer adds a default endpoint</span></span>

#### <a name="details"></a><span data-ttu-id="d2502-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="d2502-102">Details</span></span>

<span data-ttu-id="d2502-103"><xref:System.ServiceModel.Web.WebServiceHost>Obiekt nie dodaje już domyślnego punktu końcowego, jeśli jawny punkt końcowy został dodany przez kod aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d2502-103">The <xref:System.ServiceModel.Web.WebServiceHost> object no longer adds a default endpoint if an explicit endpoint has been added by application code.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d2502-104">Sugestia</span><span class="sxs-lookup"><span data-stu-id="d2502-104">Suggestion</span></span>

<span data-ttu-id="d2502-105">Jeśli użytkownicy będą mogli połączyć się z domyślnym punktem końcowym, a inne jawne punkty końcowe zostały dodane do <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName> , domyślne punkty końcowe należy również dodać jawnie (przy użyciu <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName> ).</span><span class="sxs-lookup"><span data-stu-id="d2502-105">If users will expect to be able to connect to a default endpoint and other explicit endpoints have been added to the <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName>, default endpoints should also be added explicitly (using <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName>).</span></span>

| <span data-ttu-id="d2502-106">Nazwa</span><span class="sxs-lookup"><span data-stu-id="d2502-106">Name</span></span>    | <span data-ttu-id="d2502-107">Wartość</span><span class="sxs-lookup"><span data-stu-id="d2502-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d2502-108">Zakres</span><span class="sxs-lookup"><span data-stu-id="d2502-108">Scope</span></span>   |<span data-ttu-id="d2502-109">Mały</span><span class="sxs-lookup"><span data-stu-id="d2502-109">Minor</span></span>|
|<span data-ttu-id="d2502-110">Wersja</span><span class="sxs-lookup"><span data-stu-id="d2502-110">Version</span></span>|<span data-ttu-id="d2502-111">4.5</span><span class="sxs-lookup"><span data-stu-id="d2502-111">4.5</span></span>|
|<span data-ttu-id="d2502-112">Typ</span><span class="sxs-lookup"><span data-stu-id="d2502-112">Type</span></span>|<span data-ttu-id="d2502-113">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="d2502-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="d2502-114">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="d2502-114">Affected APIs</span></span>

- <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.ServiceModel.Description.ServiceEndpoint)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String)`
- `M:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri)`
- `M:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String,System.Uri)`
- `M:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)`
- `M:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)`
- `M:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.ServiceModel.Description.ServiceEndpoint)`
- `M:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String)`
- `M:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri)`
- `M:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String,System.Uri)`
- `M:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)`

-->
