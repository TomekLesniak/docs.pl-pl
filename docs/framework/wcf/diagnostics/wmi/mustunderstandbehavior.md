---
title: MustUnderstandBehavior
ms.date: 03/30/2017
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
ms.openlocfilehash: 9cac7192d5c34de55fe0bd6a4921a41387e985f8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250440"
---
# <a name="mustunderstandbehavior"></a>MustUnderstandBehavior

MustUnderstandBehavior  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa MustUnderstandBehavior nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa MustUnderstandBehavior ma następującą właściwość:  
  
### <a name="validatemustunderstand"></a>ValidateMustUnderstand  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Gdy `true` wszystkie nagłówki protokołu SOAP z `MustUnderstand` atrybutem, który nie jest obsługiwany, powodują zgłoszenie wyjątku.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Description.MustUnderstandBehavior>
