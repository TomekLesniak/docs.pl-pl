---
title: GetWin32ResBlob — Metoda
ms.date: 03/30/2017
api_name:
- IALink.GetWin32ResBlob
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetWin32ResBlob
helpviewer_keywords:
- GetWin32ResBlob method
ms.assetid: 36997e04-f9f6-4254-a041-6767ac6c51d9
topic_type:
- apiref
ms.openlocfilehash: 03f6c97b4a5bbbdc0aeaf7b3f07277e66d7d0e9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684515"
---
# <a name="getwin32resblob-method"></a>GetWin32ResBlob — Metoda

Pobiera obiekt BLOB zasobów Win32. Wywołaj tę metodę po ustawieniu opcji zestawu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetWin32ResBlob(  
    mdAssembly    AssemblyID,  
    mdToken       FileToken,  
    BOOL          fDll,  
    LPCWSTR       pszIconFile,  
    const void**  ppResBlob,  
    DWORD*        pcbResBlob  
) PURE;  
```  
  
## <a name="parameters"></a>Parametry  

 `AssemblyID`  
 Identyfikator zestawu.  
  
 `FileToken`  
 Token pliku używany do pobierania nazwy pliku do użycia podczas konstruowania zasobu wersji Win32  
  
 `fDll`  
 PRAWDA, jeśli plik jest biblioteką DLL, wartość false dla pliku EXE.  
  
 `pszIconFile`  
 Opcjonalna ikona do wstawienia do obiektu BLOB zasobu.  
  
 `ppResBlob`  
 Odbiera obiekt BLOB zasobu.  
  
 `pcbResBlob`  
 Odbiera rozmiar obiektu BLOB.  
  
## <a name="return-value"></a>Wartość zwracana  

 Zwraca S_OK, jeśli metoda zakończy się pomyślnie.  
  
## <a name="requirements"></a>Wymagania  

 Wymaga Alink. h  
  
## <a name="see-also"></a>Zobacz także

- [IALink — Interfejs](ialink-interface.md)
- [IALink2 — Interfejs](ialink2-interface.md)
- [ALink — interfejs API](index.md)
