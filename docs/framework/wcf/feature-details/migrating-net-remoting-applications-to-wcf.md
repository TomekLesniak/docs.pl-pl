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
# <a name="migrating-net-remoting-applications-to-wcf"></a>Migrowanie aplikacji usług zdalnych platformy .NET do programu WCF

**Ten temat dotyczy starszej technologii, która jest zachowywana w celu zapewnienia zgodności z poprzednimi wersjami z istniejącymi aplikacjami i nie jest zalecana w przypadku nowych rozwiązań programistycznych. Aplikacje rozproszone powinny być teraz opracowywane przy użyciu programu WCF.**  
  
 Istnieją dwa sposoby wykorzystania programu WCF z istniejącymi aplikacjami zdalnymi platformy .NET: integrację i migrację. Funkcja integracji umożliwia udostępnianie tych samych obiektów firmowych w przypadku komunikacji zdalnej na platformie .NET 2,0 i WCF, co pozwala uwidocznić te same obiekty biznesowe w obu technologiach jednocześnie bez konieczności modyfikowania istniejącego kodu 2,0 komunikacji zdalnej dla platformy .NET. Integracja wymaga systemu na .NET Framework 2,0 lub nowszej. Jeśli chcesz korzystać z funkcji WCF i nie potrzebujesz zgodności sieci z usługami zdalnymi 2,0, możesz migrować całą usługę do platformy WCF. Migracja z usług zdalnej platformy .NET 2,0 do WCF wymaga wprowadzenia zmian w interfejsie zdalnego obiektu i jego ustawieniach konfiguracji. Oba te tematy zostały omówione w temacie [od usług zdalnych do Windows Communication Foundation](/previous-versions/aa730857(v=vs.80)).  
  
## <a name="see-also"></a>Zobacz też

- [Omówienie pojęć](../conceptual-overview.md)
