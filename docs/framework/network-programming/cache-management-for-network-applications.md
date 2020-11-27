---
title: Zarządzanie pamięcią podręczną dla aplikacji sieciowych
ms.date: 03/30/2017
helpviewer_keywords:
- cache [.NET Framework], network applications
- network resources, caching
- Internet, caching
ms.assetid: fc258a40-f370-434f-ae09-4a8cb11ddaeb
ms.openlocfilehash: 81f0eaa33b185c6bfbc8758e73a68a6bfc248872
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96287569"
---
# <a name="cache-management-for-network-applications"></a>Zarządzanie pamięcią podręczną dla aplikacji sieciowych

Ten temat i powiązane z nim tematy zawierają opis buforowania zasobów uzyskanych przy użyciu <xref:System.Net.WebClient> <xref:System.Net.WebRequest> klas,, <xref:System.Net.HttpWebRequest> i <xref:System.Net.FtpWebRequest> .  
  
 Pamięć podręczna zapewnia tymczasowy magazyn zasobów, które zostały zlecone przez aplikację. Jeśli aplikacja żąda tego samego zasobu więcej niż jeden raz, można zwrócić zasób z pamięci podręcznej, unikając ponownego zażądania od serwera. Buforowanie może zwiększyć wydajność aplikacji przez skrócenie czasu wymaganego do uzyskania żądanego zasobu. Buforowanie może również zmniejszyć ruch sieciowy, zmniejszając liczbę podróży do serwera. Buforowanie zwiększa wydajność, ale zwiększa ryzyko, że zasób zwrócony do aplikacji jest nieodświeżony, co oznacza, że nie jest on identyczny z zasobem, który został wysłany przez serwer, Jeśli buforowanie nie było używane.  
  
 Buforowanie może umożliwić nieautoryzowanym użytkownikom lub procesom odczytywanie poufnych danych. Uwierzytelniona odpowiedź w pamięci podręcznej może być pobierana z pamięci podręcznej bez dodatkowej autoryzacji. Jeśli buforowanie jest włączone, Zmień na <xref:System.Net.WebRequest.CachePolicy%2A> <xref:System.Net.Cache.RequestCacheLevel.BypassCache> lub, <xref:System.Net.Cache.RequestCacheLevel.NoCacheNoStore> Aby wyłączyć buforowanie dla tego żądania.  
  
 Ze względu na kwestie bezpieczeństwa buforowanie **nie** jest zalecane w przypadku scenariuszy warstwy środkowej.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Zasady pamięci podręcznej](cache-policy.md)  
 Wyjaśnia, co to są zasady pamięci podręcznej i jak je definiować.  
  
 [Zasady pamięci podręcznej oparte na lokalizacji](location-based-cache-policies.md)  
 Definiuje każdy typ zasad pamięci podręcznej opartych na lokalizacji dostępnych dla zasobów protokołu HTTP i https.  
  
 [Zasady pamięci podręcznej oparte na czasie](time-based-cache-policies.md)  
 Opisuje kryteria, których można użyć do dostosowania zasad pamięci podręcznej opartej na czasie.  
  
 [Konfigurowanie pamięci podręcznej w aplikacjach sieciowych](configuring-caching-in-network-applications.md)  
 Opisuje sposób programistycznego tworzenia zasad pamięci podręcznej i żądań korzystających z buforowania.  
  
## <a name="reference"></a>Dokumentacja  

 <xref:System.Net.Cache>  
 Definiuje typy i wyliczenia używane do definiowania zasad pamięci podręcznej dla zasobów uzyskanych przy użyciu <xref:System.Net.WebRequest> <xref:System.Net.HttpWebRequest> klas, i <xref:System.Net.FtpWebRequest> .
