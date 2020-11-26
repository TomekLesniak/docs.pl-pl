---
title: Modele transakcji
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: ce7eb74a3e06df8db2e6d8261faca16650e4e4f1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242269"
---
# <a name="transaction-models"></a><span data-ttu-id="53ef0-102">Modele transakcji</span><span class="sxs-lookup"><span data-stu-id="53ef0-102">Transaction Models</span></span>

<span data-ttu-id="53ef0-103">W tym temacie opisano relację między modelami programowania transakcji i składnikami infrastruktury dostarczanymi przez firmę Microsoft.</span><span class="sxs-lookup"><span data-stu-id="53ef0-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="53ef0-104">W przypadku korzystania z transakcji w programie Windows Communication Foundation (WCF) ważne jest, aby zrozumieć, że nie są wybierane między różnymi modelami transakcyjnymi, ale raczej działają na różnych warstwach zintegrowanego i spójnego modelu.</span><span class="sxs-lookup"><span data-stu-id="53ef0-104">When using transactions in Windows Communication Foundation (WCF), it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="53ef0-105">W poniższych sekcjach opisano trzy podstawowe składniki transakcji.</span><span class="sxs-lookup"><span data-stu-id="53ef0-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="53ef0-106">Windows Communication Foundation transakcji</span><span class="sxs-lookup"><span data-stu-id="53ef0-106">Windows Communication Foundation Transactions</span></span>  

 <span data-ttu-id="53ef0-107">Obsługa transakcji w programie WCF umożliwia zapisywanie usług transakcyjnych.</span><span class="sxs-lookup"><span data-stu-id="53ef0-107">The transaction support in WCF allows you write transactional services.</span></span> <span data-ttu-id="53ef0-108">Ponadto dzięki obsłudze protokołu WS-AtomicTransaction (WS-AT) aplikacje mogą przepływać transakcje do usług sieci Web zbudowanych przy użyciu technologii WCF i innych firm.</span><span class="sxs-lookup"><span data-stu-id="53ef0-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either WCF or third-party technology.</span></span>  
  
 <span data-ttu-id="53ef0-109">W usłudze lub aplikacji WCF funkcje transakcji WCF zapewniają atrybuty i konfigurację, aby deklaratywnie określić, jak i kiedy infrastruktura ma tworzyć, przepływać i synchronizować transakcje.</span><span class="sxs-lookup"><span data-stu-id="53ef0-109">In a WCF service or application, WCF transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="53ef0-110">Transakcje system. Transactions</span><span class="sxs-lookup"><span data-stu-id="53ef0-110">System.Transactions Transactions</span></span>  

 <span data-ttu-id="53ef0-111"><xref:System.Transactions>Przestrzeń nazw zapewnia jawny model programowania oparty na <xref:System.Transactions.Transaction> klasie, a także niejawny model programowania korzystający z <xref:System.Transactions.TransactionScope> klasy, w której infrastruktura automatycznie zarządza transakcjami.</span><span class="sxs-lookup"><span data-stu-id="53ef0-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 <span data-ttu-id="53ef0-112">Aby uzyskać więcej informacji na temat tworzenia transakcyjnej aplikacji przy użyciu tych dwóch modeli, zobacz [pisanie aplikacji transakcyjnej](https://go.microsoft.com/fwlink/?LinkId=94947).</span><span class="sxs-lookup"><span data-stu-id="53ef0-112">For more information about how to create a transactional application using these two models, see [Writing a Transactional Application](https://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="53ef0-113">W usłudze lub aplikacji WCF <xref:System.Transactions> oferuje model programowania służący do tworzenia transakcji w aplikacji klienckiej i jawnego działania z transakcją, jeśli jest to wymagane w ramach usługi.</span><span class="sxs-lookup"><span data-stu-id="53ef0-113">In a WCF service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="53ef0-114">Transakcje usługi MSDTC</span><span class="sxs-lookup"><span data-stu-id="53ef0-114">MSDTC Transactions</span></span>  

 <span data-ttu-id="53ef0-115">Microsoft Distributed Transaction Coordinator (MSDTC) to Menedżer transakcji, który zapewnia obsługę transakcji rozproszonych.</span><span class="sxs-lookup"><span data-stu-id="53ef0-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="53ef0-116">Aby uzyskać więcej informacji, zobacz [Dokumentacja programisty usługi DTC](/previous-versions/windows/desktop/ms686108(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="53ef0-116">For more information, see the [DTC Programmer's Reference](/previous-versions/windows/desktop/ms686108(v=vs.85)).</span></span>  
  
 <span data-ttu-id="53ef0-117">W usłudze lub aplikacji WCF usługa MSDTC udostępnia infrastrukturę do koordynacji transakcji utworzonych w ramach klienta lub usługi.</span><span class="sxs-lookup"><span data-stu-id="53ef0-117">In a WCF service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
