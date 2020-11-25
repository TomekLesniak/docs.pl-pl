---
title: IsFrameworkAssembly — Funkcja
ms.date: 03/30/2017
api_name:
- IsFrameworkAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IsFrameworkAssembly
helpviewer_keywords:
- IsFrameworkAssembly function [.NET Framework fusion]
ms.assetid: b0c6f19b-d4fd-4971-88f0-12ffb5793da3
topic_type:
- apiref
ms.openlocfilehash: 828c7660d6c006e700302d119ce4caf7d76e5d84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728566"
---
# <a name="isframeworkassembly-function"></a>IsFrameworkAssembly — Funkcja

Pobiera wartość wskazującą, czy określony zestaw jest zarządzany.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT IsFrameworkAssembly (  
    [in]  LPCWSTR pwzAssemblyReference,  
    [out] LPBOOL  pbIsFrameworkAssembly,  
    [in]  LPWSTR  pwzFrameworkAssemblyIdentity,  
    [in]  LPDWORD pccSize  
 );  
```  
  
## <a name="parameters"></a>Parametry  

 `pwzAssemblyReference`  
 podczas Nazwa zestawu do sprawdzenia.  
  
 `pbIsFrameworkAssembly`  
 określoną Wartość logiczna wskazująca, czy zestaw jest zarządzany.  
  
 `pwzFrameworkAssemblyIdentity`  
 podczas Niekanoniczny ciąg, który zawiera unikatową tożsamość zestawu.  
  
 `pccSize`  
 podczas Rozmiar `pwzFrameworkAssemblyIdentity` .  
  
## <a name="remarks"></a>Uwagi  

 `pwzAssemblyReference`Parametr jest wskaźnikiem do ciągu znaków, który zawiera nazwę zestawu.  
  
 Jeśli ten zestaw jest częścią .NET Framework, `pbIsFrameworkAssembly` parametr będzie zawierać wartość logiczną `true` .  
  
 Jeśli nazwany zestaw nie jest częścią .NET Framework lub jeśli `pwzAssemblyReference` parametr nie ma nazwy zestawu, `pbIsFrameworkAssembly` będzie zawierać wartość logiczną `false` .  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
## <a name="see-also"></a>Zobacz także

- [Łączenie statycznych funkcji globalnych](fusion-global-static-functions.md)
