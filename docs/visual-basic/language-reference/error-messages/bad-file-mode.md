---
title: Zły tryb pliku
ms.date: 07/20/2015
f1_keywords:
- vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
ms.openlocfilehash: 99b84902ddf032f2ecb6e26400e200bea862dfdf
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875146"
---
# <a name="bad-file-mode"></a>Zły tryb pliku

Instrukcje używane podczas manipulowania zawartością pliku muszą być odpowiednie dla trybu, w którym plik został otwarty. Ta sytuacja może mieć następujące przyczyny:  
  
- `FilePutObject`Instrukcja or `FileGetObject` określa sekwencyjny plik.  
  
- `Print`Instrukcja Określa plik otwarty dla trybu dostępu innego niż `Output` lub `Append` .  
  
- `Input`Instrukcja Określa plik otwarty dla trybu dostępu innego niż`Input`  
  
- Próba zapisu w pliku tylko do odczytu.  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
- Upewnij się `FilePutObject` , że `FileGetObject` odwołują się tylko do plików otwartych dla programu `Random` lub `Binary` .  
  
- Upewnij się, że `Print` określony plik jest otwarty w `Output` trybie obu lub `Append` dostępu. Jeśli nie, użyj innej instrukcji, aby umieścić dane w pliku, lub Otwórz ponownie plik w odpowiednim trybie.  
  
- Upewnij się `Input` , że wybrano plik otwarty dla programu `Input` . Jeśli nie, użyj innej instrukcji, aby umieścić dane w pliku, lub Otwórz ponownie plik w odpowiednim trybie.  
  
- Jeśli zapisujesz do pliku tylko do odczytu, Zmień stan odczytu/zapisu pliku lub nie próbuj zapisywać do niego.  
  
- Użyj funkcji dostępnych w `My.Computer.FileSystem` obiekcie.  
  
## <a name="see-also"></a>Zobacz też

- <xref:Microsoft.VisualBasic.FileSystem>
- [Rozwiązywanie problemów: Odczytywanie z plików tekstowych oraz zapisywanie w nich](../../developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
