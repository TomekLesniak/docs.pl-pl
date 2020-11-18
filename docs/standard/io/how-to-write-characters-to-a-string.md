---
title: 'Instrukcje: Wpisywanie znaków do ciągu'
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data streams, writing characters to string
- writing characters to strings
- streams, writing characters to strings
- I/O [.NET], writing characters to strings
ms.assetid: 1222cbeb-0760-44bf-9888-914a2a37174b
ms.openlocfilehash: d4a6bbc77a9feb16293fc88e1598d124d8d2d75d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829729"
---
# <a name="how-to-write-characters-to-a-string"></a>Instrukcje: Wpisywanie znaków do ciągu

Poniższe przykłady kodu zapisują znaki synchronicznie lub asynchronicznie z tablicy znaków w ciągu.  
  
## <a name="example-write-characters-synchronously-in-a-console-app"></a>Przykład: zapisuj znaki synchronicznie w aplikacji konsolowej  
 Poniższy przykład używa <xref:System.IO.StringWriter> do zapisu pięciu znaków synchronicznie do <xref:System.Text.StringBuilder> obiektu.
  
 [!code-csharp[Conceptual.StringBuilder#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.StringBuilder/cs/example2.cs#9)]
 [!code-vb[Conceptual.StringBuilder#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.StringBuilder/vb/example2.vb#9)]  
  
## <a name="example-write-characters-asynchronously-in-a-wpf-app"></a>Przykład: zapisuj znaki asynchronicznie w aplikacji WPF
 Następny przykład to kod związany z aplikacją WPF. W przypadku ładowania okna przykład Asynchronicznie odczytuje wszystkie znaki z <xref:System.Windows.Controls.TextBox> kontrolki i zapisuje je w tablicy. Następnie asynchronicznie zapisuje każdą literę lub biały znak w osobnym wierszu <xref:System.Windows.Controls.TextBlock> kontrolki.  
  
 [!code-csharp[StreamReaderWriter](../../../samples/snippets/csharp/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.cs)]
 [!code-vb[StreamReaderWriter](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringReaderWriter/MainWindow.xaml.vb)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.IO.StringWriter>  
- <xref:System.IO.StringWriter.Write%2A?displayProperty=nameWithType>  
- <xref:System.Text.StringBuilder>  
- [We/wy plików i strumieni](index.md)  
- [Asynchroniczne operacje we/wy pliku](asynchronous-file-i-o.md)  
- [Instrukcje: Wyliczanie katalogów i plików](how-to-enumerate-directories-and-files.md)  
- [Instrukcje: Odczyt i zapis w nowo utworzonym pliku danych](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Instrukcje: otwieranie pliku dziennika i dołączanie do niego](how-to-open-and-append-to-a-log-file.md)  
- [Instrukcje: odczytywanie tekstu z pliku](how-to-read-text-from-a-file.md)  
- [Instrukcje: wpisywanie tekstu do pliku](how-to-write-text-to-a-file.md)  
- [Instrukcje: odczytywanie znaków z ciągu](how-to-read-characters-from-a-string.md)
