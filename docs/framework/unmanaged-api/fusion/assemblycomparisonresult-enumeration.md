---
title: AssemblyComparisonResult — Wyliczenie
ms.date: 03/30/2017
api_name:
- AssemblyComparisonResult
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- AssemblyComparisonResult
helpviewer_keywords:
- AssemblyComparisonResult enumeration [.NET Framework fusion]
ms.assetid: bd042f89-10b1-40ca-946e-46da082f5263
topic_type:
- apiref
ms.openlocfilehash: cde25a9507006c89ef6490c13ae82033f04c2931
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731036"
---
# <a name="assemblycomparisonresult-enumeration"></a>AssemblyComparisonResult — Wyliczenie

Określa równoważność dwóch tożsamości zestawów określonych przez funkcję [CompareAssemblyIdentity —](compareassemblyidentity-function.md) .  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum _tagAssemblyComparisonResult {  
    ACR_Unknown,
    ACR_EquivalentFullMatch,  
    ACR_EquivalentWeakNamed,  
    ACR_EquivalentFXUnified,  
    ACR_EquivalentUnified,
    ACR_NonEquivalentVersion,  
    ACR_NonEquivalent,
    ACR_EquivalentPartialMatch,  
    ACR_EquivalentPartialWeakNamed,
    ACR_EquivalentPartialUnified,  
    ACR_EquivalentPartialFXUnified,  
    ACR_NonEquivalentPartialVersion
} AssemblyComparisonResult;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Nazwa elementu członkowskiego|Opis|  
|-----------------|-----------------|  
|`ACR_EquivalentFullMatch`|Wskazuje, że wszystkie pola zestawu w porównaniu są zgodne.|  
|`ACR_EquivalentFXUnified`|Wskazuje, że zestawy są uważane za równoważne w oparciu o wersję środowiska uruchomieniowego języka wspólnego (CLR), w .NET Framework w wersji 2,0.|  
|`ACR_EquivalentPartialFXUnified`|Wskazuje częściowe dopasowanie zestawów na podstawie niezjednoczenia środowiska CLR numerów wersji zestawu w .NET Framework 2,0.|  
|`ACR_EquivalentPartialMatch`|Wskazuje częściowe dopasowanie zestawów.|  
|`ACR_EquivalentPartialUnified`|Wskazuje częściowe dopasowanie zestawów w oparciu o starszej zjednoczenia numerów wersji.|  
|`ACR_EquivalentPartialWeakNamed`|Wskazuje częściowe dopasowanie zestawów po prostu nazwanych.|  
|`ACR_EquivalentUnified`|Wskazuje, że zestawy są uważane za równoważne w oparciu o niezjednoczenie kodów wersji w starszych wersjach .NET Framework.|  
|`ACR_EquivalentWeakNamed`|Wskazuje zgodność między dwoma po prostu zestawami, których numery wersji zostały zignorowane.|  
|`ACR_NonEquivalent`|Wskazuje, że nie wystąpiły żadne dopasowanie między dwoma zestawami.|  
|`ACR_NonEquivalentPartialVersion`|Wskazuje, że dwa zestawy są zgodne z wyjątkiem numerów wersji, które pasują tylko częściowo.|  
|`ACR_NonEquivalentVersion`|Wskazuje, że dwa zestawy są zgodne z wyjątkiem numerów wersji, które nie pasują do siebie.|  
|`ACR_Unknown`|Wskazuje, że przyczyna nierównoważności jest nieznana.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [CompareAssemblyIdentity — Funkcja](compareassemblyidentity-function.md)
- [Wyliczenia łączenia](fusion-enumerations.md)
