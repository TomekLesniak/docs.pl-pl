---
title: ICLRRuntimeInfo::LoadErrorString — Metoda
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
ms.openlocfilehash: 0e029aa848a6630ae00c834dd2b924dc4ebce537
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671775"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a>ICLRRuntimeInfo::LoadErrorString — Metoda

Tłumaczy wartość HRESULT na odpowiedni komunikat o błędzie dla określonej kultury.  
  
 Ta metoda zastępuje następujące funkcje:  
  
- [LoadStringRC —](loadstringrc-function.md)  
  
- [LoadStringRCEx —](loadstringrcex-function.md)  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a>Parametry  

 `iResourceID`  
 podczas WYNIK HRESULT do przetłumaczenia.  
  
 `pwzBuffer`  
 określoną Ciąg komunikatu skojarzony z podaną wartością HRESULT.  
  
 `pcchBuffer`  
 [in. out] Rozmiar, `pwzbuffer` Aby uniknąć przekroczeń buforu. Jeśli `pwzbuffer` ma wartość null, `pcchBuffer` zapewnia oczekiwany rozmiar, `pwzbuffer` który umożliwia wstępne przydzielanie.  
  
 `iLocaleID`  
 podczas Identyfikator kultury. Aby użyć domyślnej kultury, należy określić-1.  
  
## <a name="return-value"></a>Wartość zwracana  

 Ta metoda zwraca następujące określone wartości HRESULT oraz błędy HRESULT wskazujące niepowodzenie metody.  
  
|HRESULT|Opis|  
|-------------|-----------------|  
|S_OK|Metoda została ukończona pomyślnie.|  
|E_POINTER|`pcchBuffer` ma wartość null.|  
|E_INVALIDARG|`pwzBuffer` ma wartość null.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Obiekt ServiceHost. h  
  
 **Biblioteka:** Uwzględnione jako zasób w MSCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [ICLRRuntimeInfo — Interfejs](iclrruntimeinfo-interface.md)
- [Hosting — Interfejsy](hosting-interfaces.md)
- [Hosting](index.md)
