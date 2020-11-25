---
title: SetManifestFile — Metoda
ms.date: 03/30/2017
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
ms.openlocfilehash: a4518e93db887dbdc4397636479be8bf5a705c2d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733727"
---
# <a name="setmanifestfile-method"></a>SetManifestFile — Metoda

Umożliwia określenie lub zresetowanie pliku manifestu używanego przez konsolidatora podczas tworzenia zestawu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a>Parametry  

 `pszFile`  
  
 Nazwa pliku manifestu, którego zawartość jest umieszczana w obiekcie blob zasobów Win32.  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="remarks"></a>Uwagi  

 Wywołaj to przed pytaniem o Win32ResBlob. Wartość `pszFile` parametru jest nazwą pliku manifestu, którego zawartość jest odczytywana i umieszczana w zasobach Win32 o identyfikatorze RT_MANIFEST. Gdy wywoływana przy użyciu parametru o wartości NULL, każdy poprzednio odczytany manifest jest czyszczony. Umożliwia to jednemu resetowaniu stanu konsolidatora do czasu inicjacji.  
  
## <a name="requirements"></a>Wymagania  

 Wymaga aLink. h  
  
## <a name="see-also"></a>Zobacz także

- [IALink3 — Interfejs](ialink3-interface.md)
- [ALink — interfejs API](index.md)
- [IALink — Interfejs](ialink-interface.md)
- [Al.exe (Konsolidator zestawu)](../../tools/al-exe-assembly-linker.md)
