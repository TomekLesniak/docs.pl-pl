---
title: Rozszerzanie systemu metadanych
ms.date: 03/30/2017
helpviewer_keywords:
- extending metadata [WCF]
ms.assetid: 8c6b3b00-61b8-4589-8fa5-546cc33719bf
ms.openlocfilehash: 7113120a3cde6b4e6a7eb1d329da625e25996952
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272986"
---
# <a name="extending-the-metadata-system"></a><span data-ttu-id="51739-102">Rozszerzanie systemu metadanych</span><span class="sxs-lookup"><span data-stu-id="51739-102">Extending the Metadata System</span></span>

<span data-ttu-id="51739-103">System metadanych programu Windows Communication Foundation (WCF) to grupa klas i interfejsów, które reprezentują metadane wymagane do implementowania aplikacji opartych na usługach.</span><span class="sxs-lookup"><span data-stu-id="51739-103">The Windows Communication Foundation (WCF) metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="51739-104">Modyfikuj lub rozszerzaj klasy albo Implementuj i Konfiguruj interfejsy, aby wyeksportować i zaimportować niestandardowe metadane, takie jak rozszerzenia Web Services Description Language (WSDL) lub niestandardowe potwierdzenia WS-PolicyAttachments.</span><span class="sxs-lookup"><span data-stu-id="51739-104">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51739-105">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="51739-105">In This Section</span></span>  

 [<span data-ttu-id="51739-106">Eksportowanie niestandardowych metadanych na potrzeby rozszerzenia programu WCF</span><span class="sxs-lookup"><span data-stu-id="51739-106">Exporting Custom Metadata for a WCF Extension</span></span>](exporting-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="51739-107">Opisuje sposób wdrażania i używania <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interfejsu do osadzania niestandardowych potwierdzeń zasad w dokumentach WSDL.</span><span class="sxs-lookup"><span data-stu-id="51739-107">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyExportExtension?displayProperty=nameWithType> interface to embed custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="51739-108">Importowanie niestandardowych metadanych dla rozszerzenia WCF</span><span class="sxs-lookup"><span data-stu-id="51739-108">Importing Custom Metadata for a WCF Extension</span></span>](importing-custom-metadata-for-a-wcf-extension.md)  
 <span data-ttu-id="51739-109">Opisuje sposób wdrażania i używania <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interfejsu w celu odczytu i reagowania na niestandardowe potwierdzenia zasad w dokumentach WSDL.</span><span class="sxs-lookup"><span data-stu-id="51739-109">Describes how to implement and use the <xref:System.ServiceModel.Description.IPolicyImportExtension?displayProperty=nameWithType> interface to read and respond to custom policy assertions in WSDL documents.</span></span>  
  
 [<span data-ttu-id="51739-110">Publikowanie i pobieranie metadanych za pośrednictwem powiązania niestandardowego</span><span class="sxs-lookup"><span data-stu-id="51739-110">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 <span data-ttu-id="51739-111">Opisuje sposób wymiany metadanych za pośrednictwem powiązań niestandardowych.</span><span class="sxs-lookup"><span data-stu-id="51739-111">Describes how to exchange metadata over custom bindings.</span></span>
