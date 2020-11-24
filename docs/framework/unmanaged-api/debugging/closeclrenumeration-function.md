---
title: CloseCLREnumeration — Funkcja
ms.date: 03/30/2017
api_name:
- CloseCLREnumeration
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type:
- apiref
ms.openlocfilehash: 575e194cf952f02a3fe4fce9e955e45e1bc3653d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673916"
---
# <a name="closeclrenumeration-function"></a>CloseCLREnumeration — Funkcja

Zamyka wszystkie prawidłowe zdarzenia uruchamiania środowiska uruchomieniowego języka wspólnego (CLR), które znajdują się w tablicy dojść zwracanych przez [funkcję EnumerateCLRs —](enumerateclrs-function.md), i zwalnia pamięć dla tablic uchwytów i ścieżek ciągów.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a>Parametry  

 `pHandleArray`  
 podczas Wskaźnik do tablicy dojść do zdarzeń zwróconych z [funkcji EnumerateCLRs —](enumerateclrs-function.md).  
  
 `pStringArray`  
 podczas Wskaźnik do tablicy ścieżek ciągów CLR zwracanych z [funkcji EnumerateCLRs —](enumerateclrs-function.md).  
  
 `dwArrayLength`  
 podczas Wartość DWORD, która zawiera rozmiar (długość) `pHandleArray` lub `pStringArray` (jest taka sama).  
  
## <a name="return-value"></a>Wartość zwracana  

 S_OK  
 Uchwyty otwarte przez [funkcję EnumerateCLRs —](enumerateclrs-function.md) są zamknięte, a pamięć przydzieloną dla dojścia i tablic ciągów jest zwalniana.  
  
 E_INVALIDARG  
 Długość `pHandleArray` nie pasuje do długości, która została przeniesiona `dwArrayLength` .  
  
 E_FAIL (lub inne kody powrotne E_)  
 Funkcja nie może zwolnić pamięci dla `pHandleArray` i `pStringArray` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** dbgshim. h  
  
 **Biblioteka:** dbgshim.dll  
  
 **.NET Framework wersje:** 3,5 SP1
