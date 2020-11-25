---
title: Struktura COR_PRF_ASSEMBLY_REFERENCE_INFO
ms.date: 03/30/2017
dev_langs:
- cpp
ms.assetid: c8c1d916-8d1a-4f82-8128-9fd3732383fc
ms.openlocfilehash: 7c7d447afcb5a8617aa92212f3325719d5f43bf5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718621"
---
# <a name="cor_prf_assembly_reference_info-structure"></a>Struktura COR_PRF_ASSEMBLY_REFERENCE_INFO

[Obsługiwane w .NET Framework 4.5.2 i nowszych wersjach]  
  
 Zapewnia środowisko uruchomieniowe języka wspólnego z informacjami o odwołaniu do zestawu, które należy wziąć pod uwagę podczas przeprowadzania przeszukiwania odwołań do zestawu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
typedef struct _COR_PRF_ASSEMBLY_REFERENCE_INFO {  
    void* pbPublicKeyOrToken;  
    ULONG cbPublicKeyOrToken;  
    LPCWSTR szName;  
    ASSEMBLYMETADATA* pMetaData;  
    void* pbHashValue;  
    ULONG cbHashValue;  
    DWORD dwAssemblyRefFlags;  
} COR_PRF_EX_CLAUSE_INFO;  
```  
  
## <a name="members"></a>Elementy członkowskie  
  
|Członek|Opis|  
|------------|-----------------|  
|`pbPublicKeyOrToken`|Wskaźnik do klucza publicznego lub tokenu zestawu.|  
|`cbPublicKeyOrToken`|Liczba bajtów w kluczu publicznym lub tokenie.|  
|`szName`|Nazwa zestawu, do którego istnieje odwołanie.|  
|`pMetaData`|Wskaźnik do metadanych zestawu.|  
|`pbHashValue`|Wskaźnik do binarnego dużego obiektu typu hash (BLOB).|  
|`cbHashValue`|Liczba bajtów w obiekcie BLOB mieszania.|  
|`dwAssemblyRefFlags`|Flagi zestawu.|  
  
## <a name="remarks"></a>Uwagi  

 `COR_PRF_EX_CLAUSE_INFO`Struktura jest wypełniana przez profiler, gdy deklaruje dodatkowe odwołania do zestawu, że środowisko uruchomieniowe języka wspólnego należy wziąć pod uwagę podczas przeprowadzania przeszukiwania odwołań do zestawu.  
  
 Jeśli Profiler rejestruje metodę wywołania zwrotnego [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) , środowisko uruchomieniowe przekazuje ścieżkę i nazwę zestawu, który ma być załadowany, wraz ze wskaźnikiem do obiektu interfejsu [ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md) do tej metody. Profiler może następnie wywołać metodę [ICorProfilerAssemblyReferenceProvider:: AddAssemblyReference](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md) z `COR_PRF_ASSEMBLY_REFERENCE_INFO` obiektem dla każdego zestawu docelowego, który planuje się do odwołania z zestawu określonego w [ICorProfilerCallback6:: GetAssemblyReferences](icorprofilercallback6-getassemblyreferences-method.md) wywołania zwrotnego.  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** CorProf. idl, CorProf. h  
  
 **Biblioteka:** CorGuids. lib  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Profiling — Struktury](profiling-structures.md)
- [GetAssemblyReferences, metoda](icorprofilercallback6-getassemblyreferences-method.md)
- [AddAssemblyReference, metoda](icorprofilerassemblyreferenceprovider-addassemblyreference-method.md)
