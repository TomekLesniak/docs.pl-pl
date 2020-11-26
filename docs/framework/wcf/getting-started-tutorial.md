---
title: 'Samouczek: wprowadzenie do aplikacji Windows Communication Foundation'
description: Te samouczki zawierają wprowadzenie do tworzenia aplikacji WCF.
ms.date: 01/25/2019
helpviewer_keywords:
- WCF [WCF], get started
- Windows Communication Foundation [WCF], get started
- get started [WCF]
ms.assetid: df939177-73cb-4440-bd95-092a421516a1
ms.openlocfilehash: 620a83260f01e27a19b19227165695a621c88e5e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238239"
---
# <a name="tutorial-get-started-with-windows-communication-foundation-applications"></a><span data-ttu-id="bd58f-103">Samouczek: wprowadzenie do aplikacji Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="bd58f-103">Tutorial: Get started with Windows Communication Foundation applications</span></span>

<span data-ttu-id="bd58f-104">Poniższa seria samouczków wprowadza do środowiska programistycznego Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="bd58f-104">The following series of tutorials introduce you to the Windows Communication Foundation (WCF) programming experience.</span></span> <span data-ttu-id="bd58f-105">Praca nad tymi samouczkami zapewnia wprowadzenie do wprowadzenia kroków wymaganych do utworzenia aplikacji WCF.</span><span class="sxs-lookup"><span data-stu-id="bd58f-105">Working through these tutorials in order will give you an introductory understanding of the steps required to create WCF applications.</span></span> <span data-ttu-id="bd58f-106">Po zakończeniu będziesz mieć uruchomioną usługę WCF i klienta WCF, który wywoła usługę.</span><span class="sxs-lookup"><span data-stu-id="bd58f-106">After you finish, you'll have a running WCF service and a WCF client that calls the service.</span></span>

<span data-ttu-id="bd58f-107">W samouczku założono, że używasz programu Visual Studio jako środowiska deweloperskiego.</span><span class="sxs-lookup"><span data-stu-id="bd58f-107">The tutorial assumes you're using Visual Studio as the development environment.</span></span> <span data-ttu-id="bd58f-108">Jeśli używasz innego środowiska programistycznego, zignoruj instrukcje dotyczące programu Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bd58f-108">If you're using another development environment, ignore the Visual Studio-specific instructions.</span></span>

<span data-ttu-id="bd58f-109">Aby zapoznać się z przykładowymi aplikacjami WCF, które można pobrać i uruchomić, zobacz [Windows Communication Foundation Samples](samples/index.md).</span><span class="sxs-lookup"><span data-stu-id="bd58f-109">For sample WCF applications that you can download and run, see [Windows Communication Foundation samples](samples/index.md).</span></span> <span data-ttu-id="bd58f-110">Aby zapoznać się z wprowadzeniem do przykładów, zobacz [wprowadzenie](samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="bd58f-110">For an introduction to the samples, see [Getting started sample](samples/getting-started-sample.md).</span></span>

<span data-ttu-id="bd58f-111">Aby uzyskać bardziej szczegółowe informacje na temat tworzenia usług i klientów, zobacz [podstawowe programowanie WCF](basic-wcf-programming.md).</span><span class="sxs-lookup"><span data-stu-id="bd58f-111">For more in-depth information about creating services and clients, see [Basic WCF programming](basic-wcf-programming.md).</span></span>

## <a name="wcf-tutorials"></a><span data-ttu-id="bd58f-112">Samouczki WCF</span><span class="sxs-lookup"><span data-stu-id="bd58f-112">WCF tutorials</span></span>

<span data-ttu-id="bd58f-113">Pierwsze trzy samouczki opisują sposób definiowania kontraktu usługi WCF, sposobu jego wdrożenia oraz sposobu hostowania go.</span><span class="sxs-lookup"><span data-stu-id="bd58f-113">The first three tutorials describe how to define a WCF service contract, how to implement it, and how to host it.</span></span> <span data-ttu-id="bd58f-114">Utworzona usługa jest samodzielna w aplikacji konsolowej.</span><span class="sxs-lookup"><span data-stu-id="bd58f-114">The service that you create is self-hosted within a console application.</span></span> <span data-ttu-id="bd58f-115">Możesz również hostować usługi w usłudze Microsoft Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="bd58f-115">You can also host services under Microsoft Internet Information Services (IIS).</span></span> <span data-ttu-id="bd58f-116">Aby uzyskać więcej informacji, zobacz [jak: Hostowanie usługi WCF w programie IIS](feature-details/how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="bd58f-116">For more information, see [How to: Host a WCF Service in IIS](feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span> <span data-ttu-id="bd58f-117">Chociaż używasz kodu do skonfigurowania usługi w samouczku, możesz również [skonfigurować usługi w pliku konfiguracji](configuring-services-using-configuration-files.md).</span><span class="sxs-lookup"><span data-stu-id="bd58f-117">Although you use code to configure the service in the tutorial, you can also [configure services within a configuration file](configuring-services-using-configuration-files.md).</span></span>

- [<span data-ttu-id="bd58f-118">Samouczek: Definiowanie kontraktu usługi</span><span class="sxs-lookup"><span data-stu-id="bd58f-118">Tutorial: Define a service contract</span></span>](how-to-define-a-wcf-service-contract.md)

    <span data-ttu-id="bd58f-119">Tworzysz kontrakt WCF z interfejsem zdefiniowanym przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="bd58f-119">You create a WCF contract with a user-defined interface.</span></span> <span data-ttu-id="bd58f-120">Ten kontrakt definiuje funkcje, które uwidacznia usługa.</span><span class="sxs-lookup"><span data-stu-id="bd58f-120">This contract defines the functionality that the service exposes.</span></span>

- [<span data-ttu-id="bd58f-121">Samouczek: Implementowanie kontraktu usługi</span><span class="sxs-lookup"><span data-stu-id="bd58f-121">Tutorial: Implement a service contract</span></span>](how-to-implement-a-wcf-contract.md)

    <span data-ttu-id="bd58f-122">Po zdefiniowaniu kontraktu należy go zaimplementować z klasą usługi.</span><span class="sxs-lookup"><span data-stu-id="bd58f-122">After you define a contract, you must implement it with a service class.</span></span>

- [<span data-ttu-id="bd58f-123">Samouczek: Hostowanie i uruchamianie podstawowej usługi</span><span class="sxs-lookup"><span data-stu-id="bd58f-123">Tutorial: Host and run a basic service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)

    <span data-ttu-id="bd58f-124">Skonfiguruj punkt końcowy usługi i hostuje usługę w aplikacji konsolowej.</span><span class="sxs-lookup"><span data-stu-id="bd58f-124">Configure an endpoint for the service and host the service in a console application.</span></span> <span data-ttu-id="bd58f-125">Aby usługa stała się aktywna, należy ją skonfigurować i hostować w środowisku wykonawczym.</span><span class="sxs-lookup"><span data-stu-id="bd58f-125">For a service to become active, you must configure it and host it within a run-time environment.</span></span> <span data-ttu-id="bd58f-126">To środowisko uruchomieniowe tworzy usługę i kontroluje jej kontekst i okres istnienia.</span><span class="sxs-lookup"><span data-stu-id="bd58f-126">This run-time environment creates the service and controls its context and lifetime.</span></span>

<span data-ttu-id="bd58f-127">W następnych dwóch samouczkach opisano sposób tworzenia, konfigurowania i używania aplikacji klienckiej w celu wywołania operacji udostępnianych przez usługę.</span><span class="sxs-lookup"><span data-stu-id="bd58f-127">The next two tutorials describe how to create, configure, and use a client application to call the operations the service exposes.</span></span> <span data-ttu-id="bd58f-128">Usługi publikują metadane, które definiują informacje wymagane przez aplikację kliencką do komunikacji z usługą.</span><span class="sxs-lookup"><span data-stu-id="bd58f-128">Services publish metadata that define the information a client application needs to communicate with the service.</span></span> <span data-ttu-id="bd58f-129">Program Visual Studio automatyzuje proces uzyskiwania dostępu do tych metadanych i używa go do konstruowania aplikacji klienckiej dla usługi.</span><span class="sxs-lookup"><span data-stu-id="bd58f-129">Visual Studio automates the process of accessing this metadata and uses it to construct the client application for the service.</span></span> <span data-ttu-id="bd58f-130">Jeśli zdecydujesz się nie używać programu Visual Studio, możesz zamiast tego użyć [Narzędzia metadanych ServiceModel (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) .</span><span class="sxs-lookup"><span data-stu-id="bd58f-130">If you decide not to use Visual Studio, you can use the [ServiceModel Metadata Utility tool (*Svcutil.exe*)](servicemodel-metadata-utility-tool-svcutil-exe.md) instead.</span></span>

- [<span data-ttu-id="bd58f-131">Samouczek: tworzenie klienta</span><span class="sxs-lookup"><span data-stu-id="bd58f-131">Tutorial: Create a client</span></span>](how-to-create-a-wcf-client.md)

    <span data-ttu-id="bd58f-132">Pobierz metadane tworzenia serwera proxy klienta WCF z usługi WCF.</span><span class="sxs-lookup"><span data-stu-id="bd58f-132">Retrieve metadata for creating a WCF client proxy from a WCF service.</span></span> <span data-ttu-id="bd58f-133">Metadane są pobierane za pomocą programu Visual Studio w celu dodania odwołania do usługi lub narzędzia do obsługi metadanych ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="bd58f-133">You retrieve metadata by using Visual Studio to add a service reference or you can use the ServiceModel Metadata Utility tool.</span></span> <span data-ttu-id="bd58f-134">Należy określić punkt końcowy, którego klient używa w celu uzyskania dostępu do usługi.</span><span class="sxs-lookup"><span data-stu-id="bd58f-134">You specify the endpoint that the client uses to access the service.</span></span>

- [<span data-ttu-id="bd58f-135">Samouczek: korzystanie z klienta</span><span class="sxs-lookup"><span data-stu-id="bd58f-135">Tutorial: Use a client</span></span>](how-to-use-a-wcf-client.md)

    <span data-ttu-id="bd58f-136">Użyj serwera proxy klienta WCF do wywołania operacji usługi.</span><span class="sxs-lookup"><span data-stu-id="bd58f-136">Use the WCF client proxy to call the service operations.</span></span>

## <a name="reference"></a><span data-ttu-id="bd58f-137">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="bd58f-137">Reference</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>

## <a name="see-also"></a><span data-ttu-id="bd58f-138">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bd58f-138">See also</span></span>

- [<span data-ttu-id="bd58f-139">Omówienie pojęć</span><span class="sxs-lookup"><span data-stu-id="bd58f-139">Conceptual overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="bd58f-140">Przewodnik po dokumentacji</span><span class="sxs-lookup"><span data-stu-id="bd58f-140">Guide to the documentation</span></span>](guide-to-the-documentation.md)
- [<span data-ttu-id="bd58f-141">Co to jest Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="bd58f-141">What is Windows Communication Foundation</span></span>](whats-wcf.md)
- [<span data-ttu-id="bd58f-142">Szczegóły funkcji WCF</span><span class="sxs-lookup"><span data-stu-id="bd58f-142">WCF feature details</span></span>](feature-details/index.md)
- [<span data-ttu-id="bd58f-143">Podstawowy cykl życia programowania</span><span class="sxs-lookup"><span data-stu-id="bd58f-143">Basic programming lifecycle</span></span>](basic-programming-lifecycle.md)
- [<span data-ttu-id="bd58f-144">Kompilowanie klientów</span><span class="sxs-lookup"><span data-stu-id="bd58f-144">Building clients</span></span>](building-clients.md)
- [<span data-ttu-id="bd58f-145">Podstawowe programowanie WCF</span><span class="sxs-lookup"><span data-stu-id="bd58f-145">Basic WCF programming</span></span>](basic-wcf-programming.md)
- [<span data-ttu-id="bd58f-146">Instrukcje: tworzenie kontraktu dupleksowego</span><span class="sxs-lookup"><span data-stu-id="bd58f-146">How to: Create a duplex contract</span></span>](feature-details/how-to-create-a-duplex-contract.md)
- [<span data-ttu-id="bd58f-147">Instrukcje: uzyskiwanie dostępu do usług za pomocą kontraktu dupleksowego</span><span class="sxs-lookup"><span data-stu-id="bd58f-147">How to: Access services with a duplex contract</span></span>](feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="bd58f-148">Narzędzie do przesyłania metadanych modelu ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="bd58f-148">ServiceModel Metadata Utility tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="bd58f-149">Instrukcje: używanie Svcutil.exe do pobierania dokumentów metadanych</span><span class="sxs-lookup"><span data-stu-id="bd58f-149">How to: Use Svcutil.exe to download metadata documents</span></span>](feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
- [<span data-ttu-id="bd58f-150">Instrukcje: Publikowanie metadanych dla usługi za pomocą pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="bd58f-150">How to: Publish metadata for a service using a configuration file</span></span>](feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="bd58f-151">Konfigurowanie usług i klientów za pomocą powiązań</span><span class="sxs-lookup"><span data-stu-id="bd58f-151">Using bindings to configure services and clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="bd58f-152">Wprowadzenie — przykład</span><span class="sxs-lookup"><span data-stu-id="bd58f-152">Getting started sample</span></span>](samples/getting-started-sample.md)
- [<span data-ttu-id="bd58f-153">Przykłady Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="bd58f-153">Windows Communication Foundation samples</span></span>](samples/index.md)
- [<span data-ttu-id="bd58f-154">Host samodzielny</span><span class="sxs-lookup"><span data-stu-id="bd58f-154">Self-Host</span></span>](samples/self-host.md)
