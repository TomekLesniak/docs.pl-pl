---
title: Format schowka nie jest prawidłowy
ms.date: 07/20/2015
f1_keywords:
- vbrID460
ms.assetid: 71a4a045-65bb-417d-b3bd-99a9fa3c53f6
ms.openlocfilehash: 429d1e120a0044152a358a87663eb09989f45b0e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874583"
---
# <a name="clipboard-format-is-not-valid"></a>Format schowka nie jest prawidłowy

Określony format Schowka jest niezgodny z uruchomioną metodą. Wśród możliwych przyczyn tego błędu są:  
  
- Używanie schowka `GetText` lub `SetText` metody z innym formatem schowka niż `vbCFText` lub `vbCFLink` .  
  
- Używanie schowka `GetData` lub `SetData` metody z formatem schowka innym niż `vbCFBitmap` , `vbCFDIB` lub `vbCFMetafile` .  
  
- Używanie `GetData` metod lub z w `SetData` `DataObject` formacie Schowka w zakresie zarezerwowanym przez system Microsoft Windows dla zarejestrowanych formatów (&HC000-&HFFFF), gdy ten format schowka nie został zarejestrowany w systemie Microsoft Windows.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Usuń nieprawidłowy format i określ prawidłowy.  
  
## <a name="see-also"></a>Zobacz też

- [Schowek: Dodawanie innych formatów](/cpp/mfc/clipboard-adding-other-formats)
