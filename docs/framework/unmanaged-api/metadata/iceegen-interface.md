---
title: ICeeGen — Interfejs
ms.date: 03/30/2017
api_name:
- ICeeGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen
helpviewer_keywords:
- ICeeGen interface [.NET Framework metadata]
ms.assetid: 383d20b0-efe9-4e71-8fb8-1186b2e7d0c0
topic_type:
- apiref
ms.openlocfilehash: 2c180a135608350b0feec3f419be98f4f428b186
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704516"
---
# <a name="iceegen-interface"></a>ICeeGen — Interfejs

Zapewnia metody dynamicznego kompilowania kodu.  
  
 Ten interfejs jest przestarzały i nie powinien być używany.  
  
## <a name="methods"></a>Metody  
  
|Metoda|Opis|  
|------------|-----------------|  
|[AddSectionReloc, metoda](iceegen-addsectionreloc-method.md)|Nieaktualne. Dodaje instrukcję. reloc do bazy kodu.|  
|[AllocateMethodBuffer, metoda](iceegen-allocatemethodbuffer-method.md)|Nieaktualne. Tworzy bufor o określonym rozmiarze dla metody i pobiera względny adres wirtualny metody.|  
|[ComputePointer, metoda](iceegen-computepointer-method.md)|Nieaktualne. Określa bufor dla określonej sekcji kodu.|  
|[EmitString, metoda](iceegen-emitstring-method.md)|Nieaktualne. Emituje określony ciąg do bazy kodu.|  
|[GenerateCeeFile, metoda](iceegen-generateceefile-method.md)|Nieaktualne. Generuje plik bazy kodu, który zawiera bazę kodu, która jest aktualnie załadowana do tego `ICeeGen` .|  
|[GenerateCeeMemoryImage, metoda](iceegen-generateceememoryimage-method.md)|Nieaktualne. Generuje obraz w pamięci dla bazy kodu.|  
|[GetIlSection, metoda](iceegen-getilsection-method.md)|Nieaktualne. Pobiera sekcję bazy kodu języka pośredniego, do której odwołuje się określone dojście.|  
|[GetIMapTokenIface, metoda](iceegen-getimaptokeniface-method.md)|Nieaktualne. Pobiera interfejs przywoływany przez określony token.|  
|[GetMethodBuffer, metoda](iceegen-getmethodbuffer-method.md)|Nieaktualne. Pobiera bufor odpowiedniego rozmiaru dla metody pod określonym względnym adresem wirtualnym.|  
|[GetSectionBlock, metoda](iceegen-getsectionblock-method.md)|Nieaktualne. Pobiera blok sekcji bazy kodu.|  
|[GetSectionCreate, metoda](iceegen-getsectioncreate-method.md)|Nieaktualne. Generuje i pobiera sekcję kodu przy użyciu podanej wartości Name i flag.|  
|[GetSectionDataLen, metoda](iceegen-getsectiondatalen-method.md)|Nieaktualne. Pobiera długość określonej sekcji.|  
|[GetString — Metoda](iceegen-getstring-method.md)|Nieaktualne. Pobiera ciąg przechowywany w określonym względnym adresie wirtualnym.|  
|[GetStringSection, metoda](iceegen-getstringsection-method.md)|Nieaktualne. Pobiera ciąg reprezentujący sekcję kodu, do której odwołuje się określone dojście.|  
|[TruncateSection, metoda](iceegen-truncatesection-method.md)|Nieaktualne. Obcina określoną sekcję kodu o określoną długość.|  
  
## <a name="requirements"></a>Wymagania  

 **Platformy:** Zobacz [wymagania systemowe](../../get-started/system-requirements.md).  
  
 **Nagłówek:** Cor. h  
  
 **Biblioteka:** Używane jako zasób w MsCorEE.dll  
  
 **.NET Framework wersje:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Zobacz także

- [Interfejsy metadanych](metadata-interfaces.md)
