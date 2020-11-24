---
title: FUSION_INSTALL_REFERENCE — Struktura
ms.date: 03/30/2017
api_name:
- FUSION_INSTALL_REFERENCE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- FUSION_INSTALL_REFERENCE
helpviewer_keywords:
- FUSION_INSTALL_REFERENCE structure [.NET Framework fusion]
ms.assetid: ae181ec8-36bf-4ed1-9a02-ca27d417c80b
topic_type:
- apiref
ms.openlocfilehash: d5ff08e62b94d7f164b103ae0535bb62e4e60aea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688812"
---
# <a name="fusion_install_reference-structure"></a>FUSION_INSTALL_REFERENCE — Struktura

Reprezentuje odwołanie do zestawu, który aplikacja została zainstalowana w globalnej pamięci podręcznej zestawów.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct _FUSION_INSTALL_REFERENCE_ {  
    DWORD    cbSize,  
    DWORD    dwFlags,  
    GUID     guidScheme,  
    LPCWSTR  szIdentifier,  
    LPCWSTR  szNonCanonicalData  
} FUSION_INSTALL_REFERENCE, *LPFUSION_INSTALL_REFERENCE;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`cbSize`|Rozmiar struktury w bajtach.|  
|`dwFlags`|Zarezerwowane do użytku w przyszłości. Ta wartość musi być równa 0 (zero).|  
|`guidScheme`|Jednostka, która dodaje odwołanie. To pole może mieć jedną z następujących wartości:<br /><br /> -FUSION_REFCOUNT_MSI_GUID: zestaw odwołuje się do aplikacji, która została zainstalowana przy użyciu Instalator Windows Microsoft. `szIdentifier`Pole jest ustawione na `MSI` , a `szNonCanonicalData` pole jest ustawione na `Windows Installer` . Ten schemat jest używany dla zestawów równoległych systemu Windows.<br />-FUSION_REFCOUNT_UNINSTALL_SUBKEY_GUID: zestaw odwołuje się do aplikacji, która jest wyświetlana w interfejsie **Dodaj/Usuń programy** . `szIdentifier`Pole zawiera token, który rejestruje aplikację przy użyciu interfejsu **Dodaj/Usuń programy** .<br />-FUSION_REFCOUNT_FILEPATH_GUID: zestaw odwołuje się do aplikacji reprezentowanej przez plik w systemie plików. `szIdentifier`Pole zawiera ścieżkę do tego pliku.<br />-FUSION_REFCOUNT_OPAQUE_STRING_GUID: zestaw odwołuje się do aplikacji reprezentowanej tylko przez nieprzezroczysty ciąg. `szIdentifier`Pole zawiera ten ciąg nieprzezroczysty. Globalna pamięć podręczna zestawów nie sprawdza istnienia nieprzezroczystych odwołań po usunięciu tej wartości.<br />-FUSION_REFCOUNT_OSINSTALL_GUID: Ta wartość jest zarezerwowana.|  
|`szIdentifier`|Unikatowy ciąg identyfikujący aplikację, która zainstalowała zestaw w globalnej pamięci podręcznej zestawów. Jego wartość zależy od wartości `guidScheme` pola.|  
|`szNonCanonicalData`|Ciąg, który jest zrozumiały tylko dla jednostki, która dodaje odwołanie. Globalna pamięć podręczna zestawów przechowuje ten ciąg, ale nie używa go.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Fusion. h  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Łączenie — Struktury](fusion-structures.md)
- [Global Assembly Cache](../../app-domains/gac.md)
