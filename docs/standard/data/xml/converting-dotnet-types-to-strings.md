---
title: Konwertowanie typów .NET na ciągi
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
ms.openlocfilehash: ca35af17a402dc901c02edf94099af1377e1160f
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687622"
---
# <a name="convert-net-types-to-strings"></a>Konwertuj typy .NET na ciągi

Jeśli chcesz skonwertować typ .NET na ciąg, użyj metody **ToString** . Metoda **ToString** zwraca ciąg reprezentujący typ, który został przesłany. Poniższa tabela zawiera listę typów .NET, które zwracają ciąg w formacie, który jest mapowany na specyfikacje schematu XML (XSD).  
  
|Typ .NET|Zwrócony typ ciągu|  
|-------------------------|--------------------------|  
|Boolean|"true", "false"|  
|Single. PositiveInfinity|INF|  
|Single. NegativeInfinity|"-INF"|  
|Double. PositiveInfinity|INF|  
|Double. NegativeInfinity|"-INF"|  
|DateTime|Format to RRRR-MM-DDTgg: mm: sszzzzzz i jego podzestawy.|  
|Zakres czasu|Format to PnYnMnTnHnMnS, na przykład, `P2Y10M15DT10H30M20S` wynosi okres 2 lat, 10 miesięcy, 15 dni, 10hours, 30 minut i 20 sekund.|  
  
## <a name="see-also"></a>Zobacz także

- [Konwersja typów danych XML](conversion-of-xml-data-types.md)
- [Konwertowanie ciągów na typy danych .NET](converting-strings-to-dotnet-data-types.md)
