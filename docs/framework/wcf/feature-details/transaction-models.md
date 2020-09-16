---
title: Modele transakcji
ms.date: 03/30/2017
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
ms.openlocfilehash: 2d3d0631c47506e7bd99d90ed49a1fdc76cc7a59
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556827"
---
# <a name="transaction-models"></a>Modele transakcji
W tym temacie opisano relację między modelami programowania transakcji i składnikami infrastruktury dostarczanymi przez firmę Microsoft.  
  
 W przypadku korzystania z transakcji w programie Windows Communication Foundation (WCF) ważne jest, aby zrozumieć, że nie są wybierane między różnymi modelami transakcyjnymi, ale raczej działają na różnych warstwach zintegrowanego i spójnego modelu.  
  
 W poniższych sekcjach opisano trzy podstawowe składniki transakcji.  
  
## <a name="windows-communication-foundation-transactions"></a>Windows Communication Foundation transakcji  
 Obsługa transakcji w programie WCF umożliwia zapisywanie usług transakcyjnych. Ponadto wraz z obsługą protokołu WS-AtomicTransaction (WS-AT) aplikacje mogą przepływać transakcje do usług sieci Web zbudowanych przy użyciu technologii WCF i innych firm.  
  
 W usłudze lub aplikacji WCF funkcje transakcji WCF zapewniają atrybuty i konfigurację, aby deklaratywnie określić, jak i kiedy infrastruktura ma tworzyć, przepływać i synchronizować transakcje.  
  
## <a name="systemtransactions-transactions"></a>Transakcje system. Transactions  
 <xref:System.Transactions>Przestrzeń nazw zapewnia jawny model programowania oparty na <xref:System.Transactions.Transaction> klasie, a także niejawny model programowania korzystający z <xref:System.Transactions.TransactionScope> klasy, w której infrastruktura automatycznie zarządza transakcjami.  
  
 Aby uzyskać więcej informacji na temat tworzenia transakcyjnej aplikacji przy użyciu tych dwóch modeli, zobacz [pisanie aplikacji transakcyjnej](https://go.microsoft.com/fwlink/?LinkId=94947).  
  
 W usłudze lub aplikacji WCF <xref:System.Transactions> oferuje model programowania służący do tworzenia transakcji w aplikacji klienckiej i jawnego działania z transakcją, jeśli jest to wymagane w ramach usługi.  
  
## <a name="msdtc-transactions"></a>Transakcje usługi MSDTC  
 Microsoft Distributed Transaction Coordinator (MSDTC) to Menedżer transakcji, który zapewnia obsługę transakcji rozproszonych.  
  
 Aby uzyskać więcej informacji, zobacz [Dokumentacja programisty usługi DTC](/previous-versions/windows/desktop/ms686108(v=vs.85)).  
  
 W usłudze lub aplikacji WCF usługa MSDTC udostępnia infrastrukturę do koordynacji transakcji utworzonych w ramach klienta lub usługi.
