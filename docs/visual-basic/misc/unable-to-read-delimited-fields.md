---
title: Nie można odczytać rozdzielonych pól, ponieważ podwójny cudzysłów nie jest dozwolonym ogranicznikiem, gdy EscapeQuotes jest ustawiona na wartość true
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
ms.openlocfilehash: 29682edb78b848897ac2999f2d84dc1a9c1a3367
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100362"
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a>Nie można odczytać rozdzielonych pól, ponieważ podwójny cudzysłów nie jest dozwolonym ogranicznikiem, gdy EscapeQuotes jest ustawiona na wartość true

`TextFieldParser`Nie można odczytać z pliku, ponieważ znak cudzysłowu (") został dostarczony jako ogranicznik i `EscapeQuotes` jest ustawiony na `True` .  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Ustaw `EscapeQuotes` wartość `False` .  
  
## <a name="see-also"></a>Zobacz także

- [TextFieldParser. ungraniczers — Metoda](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A)
- [TextFieldParser. ograniczników — Właściwość](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A)
- [Instrukcje: Odczyt z rozdzielonych przecinkami plików testowych](../developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [TextFieldParser — Obiekt](../language-reference/objects/textfieldparser-object.md)
