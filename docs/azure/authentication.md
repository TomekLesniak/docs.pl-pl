---
title: Informacje o uwierzytelnianiu w bibliotekach platformy Azure dla platformy .NET
description: Wyjaśnia różne sposoby uwierzytelniania przy użyciu zestawu Azure SDK dla platformy .NET.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: bc2fce919d88a528f21df9f561cbe33e1119762a
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811382"
---
# <a name="authenticate-with-the-azure-sdk-for-net"></a><span data-ttu-id="41c77-103">Uwierzytelnianie za pomocą zestawu Azure SDK dla platformy .NET</span><span class="sxs-lookup"><span data-stu-id="41c77-103">Authenticate with the Azure SDK for .NET</span></span>

## <a name="recommended-azureidentity"></a><span data-ttu-id="41c77-104">Zalecane: Azure. Identity</span><span class="sxs-lookup"><span data-stu-id="41c77-104">Recommended: Azure.Identity</span></span>

<span data-ttu-id="41c77-105">Najnowsze pakiety w zestawie Azure SDK dla platformy .NET używają wspólnego pakietu uwierzytelniania do uwierzytelniania `Azure.Identity` .</span><span class="sxs-lookup"><span data-stu-id="41c77-105">The latest packages in the Azure SDK for .NET use a common authentication package to authenticate, `Azure.Identity`.</span></span> <span data-ttu-id="41c77-106">Użycie `Azure.Identity` jest zalecane w porównaniu z innymi mechanizmami uwierzytelniania opisanymi w dalszej części tego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="41c77-106">Using `Azure.Identity` is recommended over other authentication mechanisms described later in this document.</span></span> <span data-ttu-id="41c77-107">Pakiety obsługujące poświadczenia udostępniane przez `Azure.Identity` program są oparte na systemie `Azure.Core` i mają identyfikatory pakietów rozpoczynające się od *platformy Azure*.</span><span class="sxs-lookup"><span data-stu-id="41c77-107">Packages supporting the credentials provided by `Azure.Identity` are built on top of `Azure.Core` and have package identifiers starting with *Azure*.</span></span> <span data-ttu-id="41c77-108">[Lista pakietów zawiera](packages.md) spis pakietów używanych przez program `Azure.Core` .</span><span class="sxs-lookup"><span data-stu-id="41c77-108">[See the package list](packages.md) for an inventory of packages that use `Azure.Core`.</span></span>

<span data-ttu-id="41c77-109">Aby uzyskać pełne instrukcje dotyczące korzystania `Azure.Identity` z programu w projekcie, zapoznaj się z dokumentacją [klienta tożsamości platformy Azure dla platformy .NET](/dotnet/api/overview/azure/identity-readme).</span><span class="sxs-lookup"><span data-stu-id="41c77-109">For complete instructions on using `Azure.Identity` in your project, see the documentation for [Azure Identity client for .NET](/dotnet/api/overview/azure/identity-readme).</span></span>

> [!TIP]
> <span data-ttu-id="41c77-110">Przykłady dotyczące korzystania z usługi Azure Identity do zarządzania zasobami platformy Azure i uzyskiwania do nich dostępu można znaleźć w temacie [tożsamość platformy Azure, zarządzanie zasobami i przykład magazynu](/samples/dotnet/samples/azure-identity-resource-management-storage/) .</span><span class="sxs-lookup"><span data-stu-id="41c77-110">See the [Azure Identity, Resource Management, and Storage sample](/samples/dotnet/samples/azure-identity-resource-management-storage/) for examples of using Azure Identity to manage and access Azure resources.</span></span>

<span data-ttu-id="41c77-111">Aby uwierzytelnić się w bibliotekach, które nie obsługują platformy Azure. tożsamość, zobacz pozostała część tego tematu.</span><span class="sxs-lookup"><span data-stu-id="41c77-111">To authenticate with libraries that don't support Azure.Identity, see the rest of this topic.</span></span>

## <a name="access-azure-resources"></a><span data-ttu-id="41c77-112">Dostęp do zasobów platformy Azure</span><span class="sxs-lookup"><span data-stu-id="41c77-112">Access Azure resources</span></span>

<span data-ttu-id="41c77-113">Aby można było korzystać z zasobów platformy Azure, takich jak pobieranie klucza tajnego z Key Vault lub przechowywanie obiektu BLOB w magazynie, wiele bibliotek usług platformy Azure wymaga parametrów połączenia lub kluczy do uwierzytelnienia.</span><span class="sxs-lookup"><span data-stu-id="41c77-113">To interact with Azure resources, such as retrieving a secret from Key Vault or storing a blob in Storage, many Azure service libraries require a connection string or keys for authentication.</span></span> <span data-ttu-id="41c77-114">Na przykład SQL Database używa [standardowych parametrów połączenia SQL](https://docs.microsoft.com/azure/azure-sql/database/connect-query-dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="41c77-114">For example, SQL Database uses a [standard SQL connection string](https://docs.microsoft.com/azure/azure-sql/database/connect-query-dotnet-core).</span></span> <span data-ttu-id="41c77-115">Parametry połączenia usługi są używane w innych usługach platformy Azure, takich jak [CosmosDB](/azure/cosmos-db/), [pamięć podręczna platformy Azure dla Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache)i [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues).</span><span class="sxs-lookup"><span data-stu-id="41c77-115">Service connection strings are used in other Azure services like [CosmosDB](/azure/cosmos-db/), [Azure Cache for Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache), and [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues).</span></span> <span data-ttu-id="41c77-116">Te ciągi można pobrać przy użyciu Azure Portal, interfejsu wiersza polecenia lub programu PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41c77-116">You can get those strings using the Azure portal, CLI, or PowerShell.</span></span> <span data-ttu-id="41c77-117">Za pomocą bibliotek zarządzania platformy Azure dla platformy .NET można także wysyłać zapytania do zasobów w celu tworzenia parametrów połączenia w kodzie.</span><span class="sxs-lookup"><span data-stu-id="41c77-117">You can also use the Azure management libraries for .NET to query resources to build connection strings in your code.</span></span>

<span data-ttu-id="41c77-118">Metody używania parametrów połączenia różnią się w zależności od produktu.</span><span class="sxs-lookup"><span data-stu-id="41c77-118">The methods for using a connection string vary by product.</span></span> <span data-ttu-id="41c77-119">[Zapoznaj się z dokumentacją dotyczącą produktu platformy Azure](/azure/?product=featured).</span><span class="sxs-lookup"><span data-stu-id="41c77-119">[Refer to the documentation for your Azure product](/azure/?product=featured).</span></span>

## <a name="manage-azure-resources"></a><span data-ttu-id="41c77-120">Zarządzanie zasobami platformy Azure</span><span class="sxs-lookup"><span data-stu-id="41c77-120">Manage Azure resources</span></span>

[!include[Create service principal](includes/create-sp.md)]

<span data-ttu-id="41c77-121">Po utworzeniu jednostki usługi dostępne są dwie opcje uwierzytelniania dla jednostki usługi w celu utworzenia zasobów i zarządzania nimi.</span><span class="sxs-lookup"><span data-stu-id="41c77-121">Now that the service principal is created, two options are available to authenticate to the service principal to create and manage resources.</span></span>

<span data-ttu-id="41c77-122">W przypadku obu opcji należy dodać następujące pakiety NuGet do projektu.</span><span class="sxs-lookup"><span data-stu-id="41c77-122">For both options you will need to add the following NuGet packages to your project.</span></span>

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a><span data-ttu-id="41c77-123">Uwierzytelnianie przy użyciu poświadczeń tokenu</span><span class="sxs-lookup"><span data-stu-id="41c77-123">Authenticate with token credentials</span></span>

<span data-ttu-id="41c77-124">Pierwsza metoda polega na utworzeniu obiektu poświadczeń tokenu w kodzie.</span><span class="sxs-lookup"><span data-stu-id="41c77-124">The first method is to build the token credential object in code.</span></span> <span data-ttu-id="41c77-125">Poświadczenia powinny być bezpiecznie przechowywane w pliku konfiguracyjnym, rejestrze lub w magazynie kluczy platformy Azure.</span><span class="sxs-lookup"><span data-stu-id="41c77-125">You should store the credentials securely in a configuration file, the registry, or Azure KeyVault.</span></span>

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
        clientSecret,
        tenantId,
        AzureEnvironment.AzureGlobalCloud);
```

<span data-ttu-id="41c77-126">Podczas tworzenia nazwy głównej usługi Użyj wartości *clientId*, *clientSecret*i *TENANTID* z danych wyjściowych JSON.</span><span class="sxs-lookup"><span data-stu-id="41c77-126">Use the *clientId*, *clientSecret*, and *tenantId* values from the JSON output when you created the service principal.</span></span>

<span data-ttu-id="41c77-127">Następnie Utwórz obiekt punktu wejścia, `Azure` Aby rozpocząć pracę z interfejsem API:</span><span class="sxs-lookup"><span data-stu-id="41c77-127">Then create the entry point `Azure` object to start working with the API:</span></span>

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

<span data-ttu-id="41c77-128">Zaleca się jawne dostarczenie identyfikatora *subskrypcji* z danych wyjściowych JSON do `Azure` obiektu:</span><span class="sxs-lookup"><span data-stu-id="41c77-128">It is recommended that you explicitly provide the *subscriptionId* from the JSON output to the `Azure` object:</span></span>

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithSubscription(subscriptionId);
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a><span data-ttu-id="41c77-129">Uwierzytelnianie oparte na plikach</span><span class="sxs-lookup"><span data-stu-id="41c77-129">File-based authentication</span></span>

<span data-ttu-id="41c77-130">Uwierzytelnianie oparte na plikach umożliwia umieszczenie poświadczeń jednostki usługi w zwykłym pliku tekstowym i zabezpieczenie go w systemie plików.</span><span class="sxs-lookup"><span data-stu-id="41c77-130">File-based authentication allows you to put the service principal credentials in a plain text file and secure it within the file system.</span></span>

[!include[File-based authentication](includes/file-based-auth.md)]

<span data-ttu-id="41c77-131">Odczytaj zawartość pliku i Utwórz obiekt punktu wejścia, `Azure` Aby rozpocząć pracę z interfejsem API:</span><span class="sxs-lookup"><span data-stu-id="41c77-131">Read the contents of the file and create the entry point `Azure` object to start working with the API:</span></span>

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
