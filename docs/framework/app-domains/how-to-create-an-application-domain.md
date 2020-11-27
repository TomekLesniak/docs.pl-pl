---
title: 'Instrukcje: Tworzenie domeny aplikacji'
description: Zapoznaj się z tematem jak utworzyć domenę aplikacji w programie .NET. Możesz utworzyć domenę aplikacji, aby załadować zestawy do zarządzania osobiście, lub utwórz je do wykonania kodu.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, creating
ms.assetid: ba1fa43e-49f5-47d9-bd7f-3024af16f4ba
ms.openlocfilehash: fb022511ee395a9312e4dbaf7c0beee03c9b4569
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96264091"
---
# <a name="how-to-create-an-application-domain"></a><span data-ttu-id="507f7-104">Instrukcje: Tworzenie domeny aplikacji</span><span class="sxs-lookup"><span data-stu-id="507f7-104">How to: Create an Application Domain</span></span>

<span data-ttu-id="507f7-105">Host środowiska uruchomieniowego języka wspólnego automatycznie tworzy domeny aplikacji, gdy są potrzebne.</span><span class="sxs-lookup"><span data-stu-id="507f7-105">A common language runtime host creates application domains automatically when they are needed.</span></span> <span data-ttu-id="507f7-106">Można jednak tworzyć własne domeny aplikacji i ładować je do tych zestawów, które mają być zarządzane osobiście.</span><span class="sxs-lookup"><span data-stu-id="507f7-106">However, you can create your own application domains and load into them those assemblies that you want to manage personally.</span></span> <span data-ttu-id="507f7-107">Możesz również utworzyć domeny aplikacji, z których wykonywany jest kod.</span><span class="sxs-lookup"><span data-stu-id="507f7-107">You can also create application domains from which you execute code.</span></span>  
  
 <span data-ttu-id="507f7-108">Tworzysz nową domenę aplikacji przy użyciu jednej **z przeciążonych** metod w <xref:System.AppDomain?displayProperty=nameWithType> klasie.</span><span class="sxs-lookup"><span data-stu-id="507f7-108">You create a new application domain using one of the overloaded **CreateDomain** methods in the <xref:System.AppDomain?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="507f7-109">Możesz nadać domenie aplikacji nazwę i odwołać się do niej przy użyciu tej nazwy.</span><span class="sxs-lookup"><span data-stu-id="507f7-109">You can give the application domain a name and reference it by that name.</span></span>  
  
 <span data-ttu-id="507f7-110">Poniższy przykład tworzy nową domenę aplikacji, przypisuje jej nazwę `MyDomain` , a następnie drukuje nazwę domeny hosta i nowo utworzoną domenę podrzędnej aplikacji do konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="507f7-110">The following example creates a new application domain, assigns it the name `MyDomain`, and then prints the name of the host domain and the newly created child application domain to the console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="507f7-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="507f7-111">Example</span></span>  

 [!code-cpp[ADCreateDomain#2](../../../samples/snippets/cpp/VS_Snippets_CLR/ADCreateDomain/CPP/source2.cpp#2)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="507f7-112">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="507f7-112">See also</span></span>

- [<span data-ttu-id="507f7-113">Programowanie przy użyciu domen aplikacji</span><span class="sxs-lookup"><span data-stu-id="507f7-113">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="507f7-114">Używanie domeny aplikacji</span><span class="sxs-lookup"><span data-stu-id="507f7-114">Using Application Domains</span></span>](use.md)
