---
title: Błąd dostępu do ścieżki/pliku
ms.date: 07/20/2015
f1_keywords:
- vbrID75
ms.assetid: 6ce3a161-7316-46bd-a785-0d50e5414020
ms.openlocfilehash: 70de8f9cb33ab3d889f4916ae3d5de48cd218092
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871200"
---
# <a name="pathfile-access-error"></a>Błąd dostępu do ścieżki/pliku

Podczas operacji dostępu do pliku lub dysku system operacyjny nie może nawiązać połączenia między ścieżką i nazwą pliku.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Upewnij się, że Specyfikacja pliku jest poprawnie sformatowana. Nazwa pliku może zawierać w pełni kwalifikowaną (bezwzględną) lub ścieżkę względną. W pełni kwalifikowana ścieżka rozpoczyna się od nazwy dysku (jeśli ścieżka znajduje się na innym dysku) i zawiera listę jawną ścieżki z katalogu głównego do pliku. Każda ścieżka, która nie jest w pełni kwalifikowana, jest określana względem bieżącego dysku i katalogu.  
  
2. Upewnij się, że nie podjęto próby zapisania pliku, który zastąpi istniejący plik tylko do odczytu. W takim przypadku należy zmienić atrybut tylko do odczytu pliku docelowego lub zapisać plik z inną nazwą pliku.  
  
3. Upewnij się, że nie podjęto próby otworzenia pliku tylko do odczytu w trybie sekwencyjnym `Output` lub `Append` . W takim przypadku należy otworzyć plik w `Input` trybie lub zmienić atrybut tylko do odczytu pliku.  
  
4. Upewnij się, że nie podjęto próby zmiany projektu Visual Basic w bazie danych lub dokumencie.  
  
## <a name="see-also"></a>Zobacz też

- [Typy błędów](../../programming-guide/language-features/error-types.md)
