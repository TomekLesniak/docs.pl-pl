---
title: ASSEMBLYMETADATA — Struktura
ms.date: 03/30/2017
api_name:
- ASSEMBLYMETADATA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ASSEMBLYMETADATA
helpviewer_keywords:
- ASSEMBLYMETADATA structure [.NET Framework metadata]
ms.assetid: 1af98e57-9145-4d35-bb78-77d1da7c91a5
topic_type:
- apiref
ms.openlocfilehash: 8071c3f43775975de37e3255582b6fc8f13f7de3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732791"
---
# <a name="assemblymetadata-structure"></a>ASSEMBLYMETADATA — Struktura

Zawiera informacje o zestawie, do którego istnieje odwołanie, w tym jego wersji oraz o poziomie wsparcia dla ustawień regionalnych, procesorów i systemów operacyjnych.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct {  
    USHORT  usMajorVersion;  
    USHORT  usMinorVersion;  
    USHORT  usBuildNumber;  
    USHORT  usRevisionNumber;  
    LPWSTR  szLocale;  
    ULONG   cbLocale;  
    DWORD*  rdwProcessor[];  
    ULONG   ulProcessor  
    OSINFO* rOS[];  
    ULONG   ulOS;  
} ASSEMBLYMETADATA;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`usMajorVersion`|Numer wersji głównej przywoływanego zestawu. Ta wartość nie może być równa zero. Jeśli wszystkie bity `usMajorVersion` są ustawione, wersja główna nie zostanie określona.|  
|`usMinorVersion`|Pomocniczy numer wersji przywoływanego zestawu. Ta wartość nie może być równa zero. Jeśli wszystkie bity `usMinorVersion` są ustawione, nie zostanie określona wersja pomocnicza.|  
|`usBuildNumber`|Numer kompilacji przywoływanego zestawu. Ta wartość nie może być równa zero. Jeśli wszystkie bity `usBuildNumber` są ustawione, numer kompilacji nie zostanie określony.|  
|`usRevisionNumber`|Numer poprawki przywoływanego zestawu. Ta wartość nie może być równa zero. Jeśli wszystkie bity `usRevisionNumber` są ustawione, numer poprawki nie zostanie określony.|  
|`szLocale`|Lista nazw ustawień regionalnych zgodna ze specyfikacją RFC1766, oddzielona średnikami, określająca wartości lokalne obsługiwane przez przywoływany zestaw. Wartość null wskazuje niezależność ustawień regionalnych. **Uwaga:**  W .NET Framework w wersji 1,0 nie można określić więcej niż jednego ustawienia regionalnego.|  
|`cbLocale`|Rozmiar w postaci znaków dwubajtowych `szLocale` .|  
|`rdwProcessor`|Tablica identyfikatorów, zgodnie z definicją w Winnt. h, dla typów procesorów obsługiwanych przez przywoływany zestaw. Wartość NULL wskazuje niezależność procesora.|  
|`ulProcessor`|Długość `rdwProcessor` tablicy.|  
|`rOS`|Tablica wystąpień [OSINFO](osinfo-structure.md) określających systemy operacyjne, które są obsługiwane przez przywoływany zestaw. Wartość NULL wskazuje niezależność systemu operacyjnego.|  
|`ulOS`|Długość `rOS` tablicy.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Metadane — Struktury](metadata-structures.md)
- [IMetaDataAssemblyEmit — Interfejs](imetadataassemblyemit-interface.md)
- [OSINFO — Struktura](osinfo-structure.md)
