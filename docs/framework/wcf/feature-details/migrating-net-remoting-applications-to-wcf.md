---
title: Migrowanie aplikacji usług zdalnych platformy .NET do programu WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 2cfaebd064d10e5b331412d177929ecb20117a07
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248217"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a><span data-ttu-id="53bc6-102">Migrowanie aplikacji usług zdalnych platformy .NET do programu WCF</span><span class="sxs-lookup"><span data-stu-id="53bc6-102">Migrating .NET Remoting Applications to WCF</span></span>

<span data-ttu-id="53bc6-103">**Ten temat dotyczy starszej technologii, która jest zachowywana w celu zapewnienia zgodności z poprzednimi wersjami z istniejącymi aplikacjami i nie jest zalecana w przypadku nowych rozwiązań programistycznych. Aplikacje rozproszone powinny być teraz opracowywane przy użyciu programu WCF.**</span><span class="sxs-lookup"><span data-stu-id="53bc6-103">**This topic is specific to a legacy technology that is retained for backward compatibility with existing applications and is not recommended for new development. Distributed applications should now be developed using WCF.**</span></span>  
  
 <span data-ttu-id="53bc6-104">Istnieją dwa sposoby wykorzystania programu WCF z istniejącymi aplikacjami zdalnymi platformy .NET: integrację i migrację.</span><span class="sxs-lookup"><span data-stu-id="53bc6-104">There are two ways to take advantage of WCF with existing .NET Remoting applications: integration and migration.</span></span> <span data-ttu-id="53bc6-105">Funkcja integracji umożliwia udostępnianie tych samych obiektów firmowych w przypadku komunikacji zdalnej na platformie .NET 2,0 i WCF, co pozwala uwidocznić te same obiekty biznesowe w obu technologiach jednocześnie bez konieczności modyfikowania istniejącego kodu 2,0 komunikacji zdalnej dla platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="53bc6-105">Integration allows you to have .NET Remoting 2.0 and WCF running side by side, letting you expose the same business objects over both technologies simultaneously without having to modify your existing .NET Remoting 2.0 code.</span></span> <span data-ttu-id="53bc6-106">Integracja wymaga systemu na .NET Framework 2,0 lub nowszej.</span><span class="sxs-lookup"><span data-stu-id="53bc6-106">Integration requires that you are running on .NET Framework 2.0 or greater.</span></span> <span data-ttu-id="53bc6-107">Jeśli chcesz korzystać z funkcji WCF i nie potrzebujesz zgodności sieci z usługami zdalnymi 2,0, możesz migrować całą usługę do platformy WCF.</span><span class="sxs-lookup"><span data-stu-id="53bc6-107">If you want to take advantage of WCF features and do not need wire compatibility with Remoting 2.0 systems, you can migrate your entire service to WCF.</span></span> <span data-ttu-id="53bc6-108">Migracja z usług zdalnej platformy .NET 2,0 do WCF wymaga wprowadzenia zmian w interfejsie zdalnego obiektu i jego ustawieniach konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="53bc6-108">Migration from .NET Remoting 2.0 to WCF requires changes to the remote object's interface and its configuration settings.</span></span> <span data-ttu-id="53bc6-109">Oba te tematy zostały omówione w temacie [od usług zdalnych do Windows Communication Foundation](/previous-versions/aa730857(v=vs.80)).</span><span class="sxs-lookup"><span data-stu-id="53bc6-109">Both of these topics are covered in [From Remoting to the Windows Communication Foundation](/previous-versions/aa730857(v=vs.80)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53bc6-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="53bc6-110">See also</span></span>

- [<span data-ttu-id="53bc6-111">Omówienie pojęć</span><span class="sxs-lookup"><span data-stu-id="53bc6-111">Conceptual Overview</span></span>](../conceptual-overview.md)
