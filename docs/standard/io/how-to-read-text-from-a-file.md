---
title: 'Instrukcje: odczytywanie tekstu z pliku'
description: W tym artykule przedstawiono przykłady synchronicznego lub asynchronicznego odczytywania tekstu z pliku tekstowego przy użyciu klasy StreamReader w programie .NET dla aplikacji klasycznych.
ms.date: 01/03/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- streams, reading text from files
- reading text files
- reading data, text files
- data streams, reading text from files
- I/O [.NET Framework], reading text from files
ms.assetid: ed180baa-dfc6-4c69-a725-46e87edafb27
ms.openlocfilehash: fafd1cda13b46e56183489aa15d3c4df9051ae06
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553938"
---
# <a name="how-to-read-text-from-a-file"></a>Instrukcje: odczytywanie tekstu z pliku
W poniższych przykładach pokazano, jak odczytać tekst synchronicznie i asynchronicznie z pliku tekstowego przy użyciu platformy .NET dla aplikacji komputerowych. W obu przykładach podczas tworzenia wystąpienia <xref:System.IO.StreamReader> klasy należy podać względną lub bezwzględną ścieżkę do pliku.
  
> [!NOTE]
> Te przykłady kodu nie dotyczą tworzenia aplikacji uniwersalnych systemu Windows (platformy UWP), ponieważ środowisko wykonawcze systemu Windows udostępnia różne typy strumieni do odczytu i zapisu w plikach. Przykład pokazujący, jak odczytać tekst z pliku w aplikacji platformy UWP, zobacz [Szybki Start: odczytywanie i zapisywanie plików](/previous-versions/windows/apps/hh758325(v=win.10)). Przykłady pokazujące sposób konwersji między strumieniami .NET Framework i strumieniami środowisko wykonawcze systemu Windows można znaleźć w temacie [How to: converting in .NET Framework Streams and środowisko wykonawcze systemu Windows](how-to-convert-between-dotnet-streams-and-winrt-streams.md)Streams.  
  
## <a name="example-synchronous-read-in-a-console-app"></a>Przykład: Synchroniczne odczyty w aplikacji konsolowej  
W poniższym przykładzie pokazano synchroniczną operację odczytu w aplikacji konsolowej. Ten przykład otwiera plik tekstowy przy użyciu czytnika strumienia, kopiuje zawartość do ciągu i wyprowadza ciąg do konsoli.  
  
> [!IMPORTANT]
> W przykładzie założono, że plik o nazwie *TestFile.txt* już istnieje w tym samym folderze, w którym znajduje się aplikacja.  

:::code language="csharp" source="snippets/how-to-read-text-from-a-file/csharp/sync-console/Program.cs":::
:::code language="vb" source="snippets/how-to-read-text-from-a-file/vb/sync-console/Program.vb":::
  
## <a name="example-asynchronous-read-in-a-wpf-app"></a>Przykład: asynchroniczny odczyt w aplikacji WPF
 W poniższym przykładzie pokazano asynchroniczne operacje odczytu w aplikacji Windows Presentation Foundation (WPF).  
  
> [!IMPORTANT]
> W przykładzie założono, że plik o nazwie *TestFile.txt* już istnieje w tym samym folderze, w którym znajduje się aplikacja.  

:::code language="csharp" source="snippets/how-to-read-text-from-a-file/csharp/async-wpf/MainWindow.xaml.cs":::
:::code language="vb" source="snippets/how-to-read-text-from-a-file/vb/async-wpf/MainWindow.xaml.vb":::
  
## <a name="see-also"></a>Zobacz także

- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [Asynchroniczne operacje we/wy pliku](asynchronous-file-i-o.md)  
- [Instrukcje: Tworzenie listy katalogów](/previous-versions/dotnet/netframework-4.0/5cf8zcfh(v=vs.100))  
- [Szybki Start: odczytywanie i zapisywanie plików](/previous-versions/windows/apps/hh758325(v=win.10))  
- [Instrukcje: konwertowanie między strumieniami .NET Framework a strumieniami środowisko wykonawcze systemu Windows](how-to-convert-between-dotnet-streams-and-winrt-streams.md)  
- [Instrukcje: Odczyt i zapis w nowo utworzonym pliku danych](how-to-read-and-write-to-a-newly-created-data-file.md)  
- [Instrukcje: otwieranie pliku dziennika i dołączanie do niego](how-to-open-and-append-to-a-log-file.md)  
- [Instrukcje: wpisywanie tekstu do pliku](how-to-write-text-to-a-file.md)  
- [Instrukcje: odczytywanie znaków z ciągu](how-to-read-characters-from-a-string.md)  
- [Instrukcje: Wpisywanie znaków do ciągu](how-to-write-characters-to-a-string.md)  
- [We/wy plików i strumieni](index.md)
