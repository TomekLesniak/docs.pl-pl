---
title: AssemblyOptions — Wyliczenie
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
ms.openlocfilehash: 352e1acd1fdd8297754e18b2e8c6448ea723a557
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717034"
---
# <a name="assemblyoptions-enumeration"></a>AssemblyOptions — Wyliczenie

Wylicza opcje zestawu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a>Pola  
  
|Pole|Opis|  
|-----------|-----------------|  
|optAssemTitle|String — reprezentuje tytuł zestawu.|  
|optAssemDescription|Ciąg — zawiera opis zestawu.|  
|optAssemConfig|String — zawiera konfigurację zestawu.|  
|optAssemOS|Zakodowany ciąg jako: "dwOSPlatformId. dwOSMajorVersion. dwOSMinorVersion".|  
|optAssemProcessor|ULONG|  
|optAssemLocale|Ciąg — zawiera ustawienia regionalne zestawu.|  
|optAssemVersion|Zakodowany ciąg jako: "główna. pomocnicza. kompilacja. poprawka".|  
|optAssemCompany|Ciąg — zawiera firmę.|  
|optAssemProduct|String — zawiera nazwę produktu.|  
|optAssemProductVersion|Ciąg (znany również jako InformationalVersion).|  
|optAssemCopyright|Ciąg — zawiera informacje o prawach autorskich.|  
|optAssemTrademark|Ciąg — zawiera informacje o znakach towarowych.|  
|optAssemKeyFile|Ciąg (nazwa pliku).|  
|optAssemKeyName|Ciąg (nazwa klucza).|  
|optAssemAlgID|ULONG|  
|optAssemFlags|ULONG|  
|optAssemHalfSign|Bool (znany również jako DelaySign).|  
|optAssemFileVersion|Zakodowana ciągowo jako "główna. pomocnicza. kompilacja. poprawka" — taka sama jak ProductVersion.|  
|optAssemSatelliteVer|Kodowanie ciągu jako "główna. pomocnicza. kompilacja. poprawka".|  
|optLastAssemOption|Licznik liczby elementów.|  
  
## <a name="requirements"></a>Wymagania  

 **Nagłówek:** Alink. h  
  
 **Biblioteka**: alink.dll  
  
## <a name="see-also"></a>Zobacz także

- [Al.exe (Konsolidator zestawu)](../../tools/al-exe-assembly-linker.md)
