---
title: Tworzenie strumieni
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, base streams
- I/O [.NET], composing streams
- Stream class, composing streams
- base streams
- streams, backing stores
ms.assetid: da761658-a535-4f26-a452-b30df47f73d5
ms.openlocfilehash: d848a989378ed40df794554f3a0a9a7f135fbd4e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732193"
---
# <a name="compose-streams"></a>Tworzenie strumieni

*Magazyn zapasowy* jest nośnikiem magazynującym, takim jak dysk lub pamięć. Każdy inny magazyn zapasowy implementuje swój własny strumień jako implementację <xref:System.IO.Stream> klasy.

Każdy typ strumienia odczytuje i zapisuje bajty z i do danego magazynu zapasowego. Strumienie łączące się z magazynami zapasowymi są nazywane *strumieniami podstawowymi*. Strumienie podstawowe mają konstruktory z parametrami niezbędnymi do połączenia strumienia z magazynem zapasowym. Na przykład <xref:System.IO.FileStream> ma konstruktory, które określają parametr path, który określa sposób, w jaki plik będzie współużytkowany przez procesy.  

Projekt <xref:System.IO> klas zawiera uproszczoną kompozycję strumienia. Można dołączyć strumienie podstawowe do co najmniej jednego strumienia przekazującego, który zapewnia odpowiednie funkcje. Do końca łańcucha można dołączyć czytelnika lub moduł zapisujący, dzięki czemu preferowane typy mogą być łatwo odczytywane lub zapisywane.  

Poniższy przykład kodu tworzy element **FILESTREAM** wokół istniejącego *MyFile.txt* w celu buforowania *MyFile.txt*. Należy pamiętać, że **FILESTREAM** domyślnie są buforowane.

>[!IMPORTANT]
>W przykładach założono, że plik o nazwie *MyFile.txt* już istnieje w tym samym folderze, w którym znajduje się aplikacja.  

## <a name="example-use-streamreader"></a>Przykład: Użyj StreamReader

Poniższy przykład tworzy <xref:System.IO.StreamReader> do odczytu znaki z **FILESTREAM**, które są przesyłane do **StreamReader** jako argument konstruktora. <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType> następnie odczytuje do momentu <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType> znalezienia nie więcej znaków.  
  
 [!code-csharp[System.IO.StreamReader#20](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source2.cs#20)]
 [!code-vb[System.IO.StreamReader#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source2.vb#20)]  
  
## <a name="example-use-binaryreader"></a>Przykład: Użyj BinaryReader

Poniższy przykład tworzy <xref:System.IO.BinaryReader> do odczytu bajtów z **FILESTREAM**, który jest przesyłany do **BinaryReader** jako argument konstruktora. <xref:System.IO.BinaryReader.ReadByte%2A> następnie odczytuje do momentu <xref:System.IO.BinaryReader.PeekChar%2A> znalezienia braku więcej bajtów.  
  
 [!code-csharp[System.IO.StreamReader#21](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.StreamReader/CS/source3.cs#21)]
 [!code-vb[System.IO.StreamReader#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.StreamReader/VB/source3.vb#21)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.IO.StreamReader>
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>
- <xref:System.IO.StreamReader.Peek%2A?displayProperty=nameWithType>
- <xref:System.IO.FileStream>
- <xref:System.IO.BinaryReader>
- <xref:System.IO.BinaryReader.ReadByte%2A?displayProperty=nameWithType>
- <xref:System.IO.BinaryReader.PeekChar%2A?displayProperty=nameWithType>
