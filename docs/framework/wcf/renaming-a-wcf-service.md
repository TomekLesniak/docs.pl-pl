---
title: Zmienianie nazwy usługi WCF
ms.date: 03/30/2017
ms.assetid: 14235a65-b1c5-409d-b6cc-a979acd54bbd
ms.openlocfilehash: 25f9201253f02f368ccf95ddf1f7a7d78d2e1b2f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249725"
---
# <a name="renaming-a-wcf-service"></a><span data-ttu-id="4ade5-102">Zmienianie nazwy usługi WCF</span><span class="sxs-lookup"><span data-stu-id="4ade5-102">Renaming a WCF Service</span></span>

<span data-ttu-id="4ade5-103">W tym temacie opisano, jak można zmienić nazwę usługi Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4ade5-103">This topic describes how you can rename a Windows Communication Foundation (WCF) service.</span></span>  
  
## <a name="renaming-a-wcf-service"></a><span data-ttu-id="4ade5-104">Zmienianie nazwy usługi WCF</span><span class="sxs-lookup"><span data-stu-id="4ade5-104">Renaming a WCF Service</span></span>  

 <span data-ttu-id="4ade5-105">Aby zmienić nazwę usługi w szablonie Windows Communication Foundation (WCF), wykonaj następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="4ade5-105">Perform the following steps to rename a service in a Windows Communication Foundation (WCF) template,</span></span>  
  
- <span data-ttu-id="4ade5-106">Zmień nazwę klasy implementującej usługę.</span><span class="sxs-lookup"><span data-stu-id="4ade5-106">Change the name of the class that implements the service.</span></span>  
  
- <span data-ttu-id="4ade5-107">W pliku konfiguracji usługi Zmień nazwę usługi na nową wybraną nazwę, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="4ade5-107">In the configuration file of the service, change the name of the service to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="4ade5-108">Plik konfiguracji może być app.config lub web.config pliku w zależności od modelu hostingu.</span><span class="sxs-lookup"><span data-stu-id="4ade5-108">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service name="WcfService.NewName">  
      </service>  
   </services>  
</system.servicemodel>  
```  
  
- <span data-ttu-id="4ade5-109">Jeśli usługa jest hostowana w sieci, używa pliku *\* SVC* .</span><span class="sxs-lookup"><span data-stu-id="4ade5-109">If your service is webhosted, it uses an *\*.svc* file.</span></span> <span data-ttu-id="4ade5-110">Otwórz plik SVC i zmodyfikuj nazwę usługi, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="4ade5-110">Open the svc file and modify the name of your service as indicated in the following example.</span></span> <span data-ttu-id="4ade5-111">Ten krok nie jest konieczny w przypadku aplikacji samodzielnych, ponieważ nie ma pliku SVC.</span><span class="sxs-lookup"><span data-stu-id="4ade5-111">This step is not necessary for self-hosted applications, as there is no svc file.</span></span>  
  
```aspx-csharp
<%@ ServiceHost Service="WcfService.NewName">  
```  
  
## <a name="renaming-a-wcf-service-contract"></a><span data-ttu-id="4ade5-112">Zmiana nazwy kontraktu usługi WCF</span><span class="sxs-lookup"><span data-stu-id="4ade5-112">Renaming a WCF Service Contract</span></span>  
  
- <span data-ttu-id="4ade5-113">Aby zmienić nazwę kontraktu usługi, wykonaj następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="4ade5-113">Perform the following steps to rename the service contract,</span></span>  
  
- <span data-ttu-id="4ade5-114">Zmień nazwę kontraktu usługi.</span><span class="sxs-lookup"><span data-stu-id="4ade5-114">Change the name of the service contract.</span></span>  
  
- <span data-ttu-id="4ade5-115">W pliku konfiguracji usługi Zmień nazwę kontraktu usługi na nową wybraną nazwę, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="4ade5-115">In the configuration file of the service, change the name of the service contract to the new name you have chosen, as indicated in the following example.</span></span> <span data-ttu-id="4ade5-116">Plik konfiguracji może być app.config lub web.config pliku w zależności od modelu hostingu.</span><span class="sxs-lookup"><span data-stu-id="4ade5-116">The configuration file can be either app.config or web.config file depending on your hosting model.</span></span>  
  
```xml  
<system.servicemodel>  
   <services>  
      <service>  
         <endpoint contract="WcfService.NewContractName" />  
      </service>  
   </services>  
</system.servicemodel>  
```
