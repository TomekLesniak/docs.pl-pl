---
title: Zła długość rekordu
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 6967015572b2567f52697f7ddcb1ff594013a2c4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869257"
---
# <a name="bad-record-length"></a>Zła długość rekordu

Wśród możliwych przyczyn tego błędu są:  
  
- Zmienna rekordu określona w `FileGet` `FileGetObject` instrukcji,, `FilePut` lub `FilePutObject` jest inna niż długość określona w odpowiedniej `FileOpen` instrukcji.  
  
- Zmienna w `FilePut` `FilePutObject` instrukcji or ma lub zawiera ciąg o zmiennej długości.  
  
- Zmienna w `FilePut` lub `FilePutObject` jest lub zawiera `Variant` Typ.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Upewnij się, że suma rozmiarów zmiennych o stałej długości w typie zdefiniowanym przez użytkownika definiująca typ zmiennej rekordu jest taka sama jak wartość określona w `FileOpen` `Len` klauzuli instrukcji.  
  
2. Jeśli zmienna w `FilePut` `FilePutObject` instrukcji or ma lub zawiera ciąg o zmiennej długości, upewnij się, że ciąg o zmiennej długości ma co najmniej 2 znaki krótsze niż długość rekordu określona w `Len` klauzuli `FileOpen` instrukcji.  
  
3. Jeśli zmienna w lub lub `FilePut` `FilePutObject` jest lub zawiera, `Variant` upewnij się, że ciąg o zmiennej długości występuje co najmniej 4 bajty krótszy niż długość rekordu określona w `Len` klauzuli `FileOpen` instrukcji.  
  
## <a name="see-also"></a>Zobacz też

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
