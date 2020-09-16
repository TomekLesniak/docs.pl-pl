---
title: <configuration>, element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 8f79981a55d0bc9b1cd522e45f5606fda102c72c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544694"
---
# <a name="configuration-element"></a><span data-ttu-id="0c1c9-102">\<configuration>, element</span><span class="sxs-lookup"><span data-stu-id="0c1c9-102">\<configuration> element</span></span>

<span data-ttu-id="0c1c9-103">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje programu .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0c1c9-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

**\<configuration>**

## <a name="syntax"></a><span data-ttu-id="0c1c9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="0c1c9-104">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="0c1c9-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="0c1c9-105">Attributes</span></span>

<span data-ttu-id="0c1c9-106">Brak</span><span class="sxs-lookup"><span data-stu-id="0c1c9-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="0c1c9-107">Element nadrzędny</span><span class="sxs-lookup"><span data-stu-id="0c1c9-107">Parent element</span></span>

<span data-ttu-id="0c1c9-108">Brak</span><span class="sxs-lookup"><span data-stu-id="0c1c9-108">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="0c1c9-109">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="0c1c9-109">Child elements</span></span>

|     | <span data-ttu-id="0c1c9-110">Opis</span><span class="sxs-lookup"><span data-stu-id="0c1c9-110">Description</span></span> |
| --- | ----------- |
| [**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) | <span data-ttu-id="0c1c9-111">Określa zasady powiązań zestawów na poziomie konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="0c1c9-111">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="0c1c9-112">**\<startup>** Schemat ustawień</span><span class="sxs-lookup"><span data-stu-id="0c1c9-112">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="0c1c9-113">Wszystkie elementy w schemacie ustawienia uruchamiania.</span><span class="sxs-lookup"><span data-stu-id="0c1c9-113">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="0c1c9-114">**\<runtime>** Schemat ustawień</span><span class="sxs-lookup"><span data-stu-id="0c1c9-114">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="0c1c9-115">Wszystkie elementy w schemacie ustawień środowiska uruchomieniowego.</span><span class="sxs-lookup"><span data-stu-id="0c1c9-115">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="0c1c9-116">[**\<system.runtime.remoting>** Schemat ustawień](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0c1c9-116">[**\<system.runtime.remoting>** Settings Schema](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="0c1c9-117">Wszystkie elementy w schemacie ustawień usług zdalnych.</span><span class="sxs-lookup"><span data-stu-id="0c1c9-117">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="0c1c9-118">**\<system.Net>** Schemat ustawień</span><span class="sxs-lookup"><span data-stu-id="0c1c9-118">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="0c1c9-119">Wszystkie elementy w schemacie ustawień sieciowych.</span><span class="sxs-lookup"><span data-stu-id="0c1c9-119">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="0c1c9-120">**\<cryptographySettings>** Schemat ustawień</span><span class="sxs-lookup"><span data-stu-id="0c1c9-120">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="0c1c9-121">Wszystkie elementy w schemacie ustawień kryptograficznych.</span><span class="sxs-lookup"><span data-stu-id="0c1c9-121">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="0c1c9-122">**\<configuration>** Schemat sekcji</span><span class="sxs-lookup"><span data-stu-id="0c1c9-122">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="0c1c9-123">Wszystkie elementy w schemacie ustawień sekcji konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="0c1c9-123">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="0c1c9-124">Schemat ustawień śledzenia i debugowania</span><span class="sxs-lookup"><span data-stu-id="0c1c9-124">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="0c1c9-125">Wszystkie elementy w schemacie ustawienia śledzenia i debugowania.</span><span class="sxs-lookup"><span data-stu-id="0c1c9-125">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="0c1c9-126">[Schemat ustawień konfiguracji ASP.NET](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0c1c9-126">[ASP.NET Configuration Settings Schema](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="0c1c9-127">Wszystkie elementy w schemacie konfiguracji ASP.NET, w tym elementy służące do konfigurowania witryn i aplikacji sieci Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0c1c9-127">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="0c1c9-128">Używane w plikach *Web.config* .</span><span class="sxs-lookup"><span data-stu-id="0c1c9-128">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="0c1c9-129">[**\<webServices>** Schemat ustawień](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="0c1c9-129">[**\<webServices>** Settings Schema](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="0c1c9-130">Wszystkie elementy w schemacie ustawień usług sieci Web.</span><span class="sxs-lookup"><span data-stu-id="0c1c9-130">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="0c1c9-131">Schemat ustawień sieci Web</span><span class="sxs-lookup"><span data-stu-id="0c1c9-131">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="0c1c9-132">Wszystkie elementy w schemacie ustawień sieci Web, w tym elementy służące do konfigurowania sposobu działania programu ASP.NET z aplikacją hosta, taką jak usługi IIS.</span><span class="sxs-lookup"><span data-stu-id="0c1c9-132">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="0c1c9-133">Używane w plikach *aspnet.config* .</span><span class="sxs-lookup"><span data-stu-id="0c1c9-133">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="0c1c9-134">Uwagi</span><span class="sxs-lookup"><span data-stu-id="0c1c9-134">Remarks</span></span>

<span data-ttu-id="0c1c9-135">Każdy plik konfiguracji musi zawierać dokładnie jeden **\<configuration>** element.</span><span class="sxs-lookup"><span data-stu-id="0c1c9-135">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="0c1c9-136">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0c1c9-136">See also</span></span>

- [<span data-ttu-id="0c1c9-137">Schemat pliku konfiguracji dla .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0c1c9-137">Configuration file schema for the .NET Framework</span></span>](index.md)
