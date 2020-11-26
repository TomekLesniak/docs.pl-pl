---
title: Nazwy elementów równorzędnych i identyfikatory PNRP
ms.date: 03/30/2017
ms.assetid: afa538e8-948f-4a98-aa9f-305134004115
ms.openlocfilehash: a56200d599d417dac549af000b35024338d43796
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239227"
---
# <a name="peer-names-and-pnrp-ids"></a>Nazwy elementów równorzędnych i identyfikatory PNRP

Nazwa elementu równorzędnego reprezentuje punkt końcowy komunikacji, który może być komputerem, użytkownikiem, grupą, usługą lub wszelkimi elementami skojarzonymi z elementem równorzędnym, który można rozpoznać jako adres IPv6. Protokół rozpoznawania nazw równorzędnych (PNRP) pobiera statystycznie unikatową nazwę elementu równorzędnego dla tworzenia identyfikatora PNRP, który jest używany do identyfikowania członków w chmurze.  
  
## <a name="peer-names"></a>Nazwy elementów równorzędnych  

 Nazwy elementów równorzędnych mogą być rejestrowane jako niezabezpieczone lub zabezpieczone. Niezabezpieczone nazwy to tylko ciągi tekstowe, które podlegają fałszowaniu, ponieważ każdy może zarejestrować duplikat niezabezpieczonej nazwy. Niezabezpieczone nazwy są najlepiej używane w sieciach prywatnych lub w inny sposób chroniony. Zabezpieczone nazwy są chronione za pomocą certyfikatu i podpisu cyfrowego. Tylko oryginalny Wydawca będzie mógł udowodnić własność zabezpieczonej nazwy.  
  
 Połączenie chmury i zakresu zapewnia racjonalne bezpieczne środowisko dla elementów równorzędnych, które uczestniczą w działaniu PNRP. Jednak używanie zabezpieczonej nazwy elementu równorzędnego nie zapewnia ogólnych zabezpieczeń aplikacji sieci. Zabezpieczenia aplikacji są zależne od implementacji.  
  
 Nazwy zabezpieczonych elementów równorzędnych są rejestrowane tylko przez ich właściciela i są chronione za pomocą kryptografii klucza publicznego. Nazwa bezpiecznego elementu równorzędnego jest uważana za właściciela jednostki równorzędnej mającej odpowiedni klucz prywatny. Własność można udowodnić za pośrednictwem adresu uwierzytelnionego elementu równorzędnego (CPA), który jest podpisywany przy użyciu klucza prywatnego. Złośliwy użytkownik nie może sfałszowanić własności nazwy elementu równorzędnego bez odpowiedniego klucza prywatnego.  
  
## <a name="pnrp-ids"></a>Identyfikatory protokołu PNRP  

 ![IDENTYFIKATOR PNRP](./media/fdc9e8a0-4a1c-488d-a019-bc3a1973220c.gif "fdc9e8a0-4a1c-488d-a019-bc3a1973220c")  
  
 Identyfikatory protokołu PNRP składają się z następujących elementów:  
  
- Wysoki porządek 128 bitów, znany jako identyfikator komunikacji równorzędnej (P2P), jest skrótem nazwy elementu równorzędnego przypisanego do punktu końcowego. Nazwa elementu równorzędnego ma następujący format: *Authority. klasyfikator*. W przypadku zabezpieczonych nazw *Urząd* jest skrótem Secure Hash Algorithm 1 (SHA1) klucza publicznego nazwy elementu równorzędnego w znakach szesnastkowych. W przypadku niezabezpieczonych nazw *Urząd* jest pojedynczym znakiem "0". *Klasyfikator* jest ciągiem, który identyfikuje aplikację. Żadna nazwa elementu równorzędnego nie może być dłuższa niż 149 znaków, łącznie z `null` terminatorem.  
  
- 128 bitów niskiego rzędu są używane dla lokalizacji usługi, która jest wygenerowanej liczby, która identyfikuje różne wystąpienia tego samego identyfikatora P2P w tej samej chmurze.  
  
 Ta kombinacja identyfikatora P2P i lokalizacji usługi umożliwia rejestrację wielu identyfikatorów PNRP z jednego komputera.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Net.PeerToPeer.PeerName>
- <xref:System.Net.PeerToPeer>
