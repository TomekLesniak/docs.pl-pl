---
title: ICorRuntimeHost — Interfejs
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost
helpviewer_keywords:
- ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type:
- apiref
ms.openlocfilehash: 9fcb5e189af9f72de7635aad550a5e8ab5522dbd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720623"
---
# <a name="icorruntimehost-interface"></a><span data-ttu-id="a4e88-102">ICorRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a4e88-102">ICorRuntimeHost Interface</span></span>

<span data-ttu-id="a4e88-103">Zapewnia metody, które umożliwiają hostowi uruchamianie i zatrzymywanie jawnie środowiska uruchomieniowego języka wspólnego (CLR), w celu utworzenia i skonfigurowania domen aplikacji, uzyskania dostępu do domeny domyślnej i wyliczenia wszystkich domen uruchomionych w procesie.</span><span class="sxs-lookup"><span data-stu-id="a4e88-103">Provides methods that enable the host to start and stop the common language runtime (CLR) explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>  
  
 <span data-ttu-id="a4e88-104">W .NET Framework w wersji 2,0 ten interfejs został zastąpiony przez [ICLRRuntimeHost](iclrruntimehost-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a4e88-104">In the .NET Framework version 2.0, this interface is superceded by [ICLRRuntimeHost](iclrruntimehost-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4e88-105">Metody</span><span class="sxs-lookup"><span data-stu-id="a4e88-105">Methods</span></span>  
  
|<span data-ttu-id="a4e88-106">Metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-106">Method</span></span>|<span data-ttu-id="a4e88-107">Opis</span><span class="sxs-lookup"><span data-stu-id="a4e88-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4e88-108">CloseEnum — Metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-108">CloseEnum Method</span></span>](icorruntimehost-closeenum-method.md)|<span data-ttu-id="a4e88-109">Resetuje moduł wyliczający domeny z powrotem do początku listy domen.</span><span class="sxs-lookup"><span data-stu-id="a4e88-109">Resets a domain enumerator back to the beginning of the domain list.</span></span>|  
|[<span data-ttu-id="a4e88-110">CreateDomain, metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-110">CreateDomain Method</span></span>](icorruntimehost-createdomain-method.md)|<span data-ttu-id="a4e88-111">Tworzy domenę aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a4e88-111">Creates an application domain.</span></span> <span data-ttu-id="a4e88-112">Obiekt wywołujący otrzymuje wskaźnik interfejsu typu <xref:System._AppDomain> do wystąpienia typu <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a4e88-112">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>|  
|[<span data-ttu-id="a4e88-113">CreateDomainEx, metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-113">CreateDomainEx Method</span></span>](icorruntimehost-createdomainex-method.md)|<span data-ttu-id="a4e88-114">Tworzy domenę aplikacji.</span><span class="sxs-lookup"><span data-stu-id="a4e88-114">Creates an application domain.</span></span> <span data-ttu-id="a4e88-115">Ta metoda umożliwia obiektowi wywołującemu przekazanie wystąpienia IAppDomainSetup — w celu skonfigurowania dodatkowych funkcji zwracanego <xref:System._AppDomain> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="a4e88-115">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>|  
|[<span data-ttu-id="a4e88-116">CreateDomainSetup, metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-116">CreateDomainSetup Method</span></span>](icorruntimehost-createdomainsetup-method.md)|<span data-ttu-id="a4e88-117">Pobiera wskaźnik interfejsu typu `IAppDomainSetup` do <xref:System.AppDomainSetup> wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="a4e88-117">Gets an interface pointer of type `IAppDomainSetup` to an <xref:System.AppDomainSetup> instance.</span></span> <span data-ttu-id="a4e88-118">`IAppDomainSetup` zapewnia metody konfigurowania aspektów domeny aplikacji przed jej utworzeniem.</span><span class="sxs-lookup"><span data-stu-id="a4e88-118">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>|  
|[<span data-ttu-id="a4e88-119">CreateEvidence, metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-119">CreateEvidence Method</span></span>](icorruntimehost-createevidence-method.md)|<span data-ttu-id="a4e88-120">Pobiera wskaźnik interfejsu typu <xref:System.Security.Principal.IIdentity> , który umożliwia hostowi tworzenie dowodu bezpieczeństwa do przekazania do elementu [ondomain](icorruntimehost-createdomain-method.md) lub [CreateDomainEx —](icorruntimehost-createdomainex-method.md).</span><span class="sxs-lookup"><span data-stu-id="a4e88-120">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity>, which allows the host to create security evidence to pass to [CreateDomain](icorruntimehost-createdomain-method.md) or [CreateDomainEx](icorruntimehost-createdomainex-method.md).</span></span>|  
|[<span data-ttu-id="a4e88-121">CreateLogicalThreadState, metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-121">CreateLogicalThreadState Method</span></span>](icorruntimehost-createlogicalthreadstate-method.md)|<span data-ttu-id="a4e88-122">Nie używaj.</span><span class="sxs-lookup"><span data-stu-id="a4e88-122">Do not use.</span></span>|  
|[<span data-ttu-id="a4e88-123">CurrentDomain, metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-123">CurrentDomain Method</span></span>](icorruntimehost-currentdomain-method.md)|<span data-ttu-id="a4e88-124">Pobiera wskaźnik interfejsu typu <xref:System._AppDomain> , który reprezentuje domenę załadowana w bieżącym wątku.</span><span class="sxs-lookup"><span data-stu-id="a4e88-124">Gets an interface pointer of type <xref:System._AppDomain> that represents the domain loaded on the current thread.</span></span>|  
|[<span data-ttu-id="a4e88-125">DeleteLogicalThreadState, metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-125">DeleteLogicalThreadState Method</span></span>](icorruntimehost-deletelogicalthreadstate-method.md)|<span data-ttu-id="a4e88-126">Nie używaj.</span><span class="sxs-lookup"><span data-stu-id="a4e88-126">Do not use.</span></span>|  
|[<span data-ttu-id="a4e88-127">EnumDomains, metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-127">EnumDomains Method</span></span>](icorruntimehost-enumdomains-method.md)|<span data-ttu-id="a4e88-128">Pobiera moduł wyliczający dla domen w bieżącym procesie.</span><span class="sxs-lookup"><span data-stu-id="a4e88-128">Gets an enumerator for the domains in the current process.</span></span>|  
|[<span data-ttu-id="a4e88-129">GetConfiguration — Metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-129">GetConfiguration Method</span></span>](icorruntimehost-getconfiguration-method.md)|<span data-ttu-id="a4e88-130">Pobiera obiekt, który umożliwia hostowi określenie konfiguracji wywołania zwrotnego środowiska CLR.</span><span class="sxs-lookup"><span data-stu-id="a4e88-130">Gets an object that allows the host to specify the callback configuration of the CLR.</span></span>|  
|[<span data-ttu-id="a4e88-131">GetDefaultDomain, metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-131">GetDefaultDomain Method</span></span>](icorruntimehost-getdefaultdomain-method.md)|<span data-ttu-id="a4e88-132">Pobiera wskaźnik interfejsu typu <xref:System._AppDomain> , który reprezentuje domenę domyślną dla bieżącego procesu.</span><span class="sxs-lookup"><span data-stu-id="a4e88-132">Gets an interface pointer of type <xref:System._AppDomain> that represents the default domain for the current process.</span></span>|  
|[<span data-ttu-id="a4e88-133">LocksHeldByLogicalThread, metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-133">LocksHeldByLogicalThread Method</span></span>](icorruntimehost-locksheldbylogicalthread-method.md)|<span data-ttu-id="a4e88-134">Nie używaj.</span><span class="sxs-lookup"><span data-stu-id="a4e88-134">Do not use.</span></span>|  
|[<span data-ttu-id="a4e88-135">MapFile, metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-135">MapFile Method</span></span>](icorruntimehost-mapfile-method.md)|<span data-ttu-id="a4e88-136">Mapuje określony plik do pamięci.</span><span class="sxs-lookup"><span data-stu-id="a4e88-136">Maps the specified file into memory.</span></span> <span data-ttu-id="a4e88-137">Ta metoda jest przestarzała.</span><span class="sxs-lookup"><span data-stu-id="a4e88-137">This method is obsolete.</span></span>|  
|[<span data-ttu-id="a4e88-138">NextDomain, metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-138">NextDomain Method</span></span>](icorruntimehost-nextdomain-method.md)|<span data-ttu-id="a4e88-139">Pobiera wskaźnik interfejsu do następnej domeny w wyliczeniu.</span><span class="sxs-lookup"><span data-stu-id="a4e88-139">Gets an interface pointer to the next domain in the enumeration.</span></span>|  
|[<span data-ttu-id="a4e88-140">Start — Metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-140">Start Method</span></span>](icorruntimehost-start-method.md)|<span data-ttu-id="a4e88-141">Uruchamia środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="a4e88-141">Starts the CLR.</span></span>|  
|[<span data-ttu-id="a4e88-142">Stop — Metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-142">Stop Method</span></span>](icorruntimehost-stop-method.md)|<span data-ttu-id="a4e88-143">Kończy wykonywanie kodu w środowisku uruchomieniowym dla bieżącego procesu.</span><span class="sxs-lookup"><span data-stu-id="a4e88-143">Stops the execution of code in the runtime for the current process.</span></span>|  
|[<span data-ttu-id="a4e88-144">SwitchInLogicalThreadState, metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-144">SwitchInLogicalThreadState Method</span></span>](icorruntimehost-switchinlogicalthreadstate-method.md)|<span data-ttu-id="a4e88-145">Nie używaj.</span><span class="sxs-lookup"><span data-stu-id="a4e88-145">Do not use.</span></span>|  
|[<span data-ttu-id="a4e88-146">SwitchOutLogicalThreadState, metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-146">SwitchOutLogicalThreadState Method</span></span>](icorruntimehost-switchoutlogicalthreadstate-method.md)|<span data-ttu-id="a4e88-147">Nie używaj.</span><span class="sxs-lookup"><span data-stu-id="a4e88-147">Do not use.</span></span>|  
|[<span data-ttu-id="a4e88-148">UnloadDomain, metoda</span><span class="sxs-lookup"><span data-stu-id="a4e88-148">UnloadDomain Method</span></span>](icorruntimehost-unloaddomain-method.md)|<span data-ttu-id="a4e88-149">Zwalnia określoną domenę aplikacji z bieżącego procesu.</span><span class="sxs-lookup"><span data-stu-id="a4e88-149">Unloads the specified application domain from the current process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a4e88-150">Wymagania</span><span class="sxs-lookup"><span data-stu-id="a4e88-150">Requirements</span></span>  

 <span data-ttu-id="a4e88-151">**Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4e88-151">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4e88-152">**Nagłówek:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a4e88-152">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a4e88-153">**Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a4e88-153">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4e88-154">**.NET Framework wersje:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="a4e88-154">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4e88-155">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a4e88-155">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="a4e88-156">Hosting</span><span class="sxs-lookup"><span data-stu-id="a4e88-156">Hosting</span></span>](index.md)
- [<span data-ttu-id="a4e88-157">ICLRRuntimeHost — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a4e88-157">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- <span data-ttu-id="a4e88-158">[Hosty środowiska uruchomieniowego](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a4e88-158">[Runtime Hosts](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
- [<span data-ttu-id="a4e88-159">Hosting — Interfejsy</span><span class="sxs-lookup"><span data-stu-id="a4e88-159">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="a4e88-160">CorRuntimeHost — Klasa coclass</span><span class="sxs-lookup"><span data-stu-id="a4e88-160">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
