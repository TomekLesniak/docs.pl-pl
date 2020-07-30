---
title: Kopiowanie, usuwanie i przenoszenie plików i folderów — Przewodnik programowania w języku C#
description: Dowiedz się, jak kopiować, usuwać i przenosić pliki i foldery przy użyciu klas File, Directory, FileInfo i DirectoryInfo.
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: 208502651080f4fd614e34d1bf5b088dfb1207a6
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303364"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a>Kopiowanie, usuwanie i przenoszenie plików i folderów (Przewodnik programowania w języku C#)
W poniższych przykładach pokazano, jak kopiować, przenosić i usuwać pliki i foldery w sposób synchroniczny przy użyciu <xref:System.IO.File?displayProperty=nameWithType> klas, <xref:System.IO.Directory?displayProperty=nameWithType> , <xref:System.IO.FileInfo?displayProperty=nameWithType> i <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> z <xref:System.IO?displayProperty=nameWithType> przestrzeni nazw. Te przykłady nie zapewniają paska postępu ani żadnego innego interfejsu użytkownika. Jeśli chcesz podać standardowe okno dialogowe postępu, zobacz, [jak zapewnić postęp dla operacji na plikach](how-to-provide-a-progress-dialog-box-for-file-operations.md).  
  
 Służy <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> do dostarczania zdarzeń, które umożliwią obliczenie postępu podczas działania na wielu plikach. Innym podejściem jest użycie wywołania platformy w celu wywołania odpowiednich metod związanych z plikiem w powłoce systemu Windows. Aby uzyskać informacje o tym, jak wykonywać te operacje na plikach asynchronicznie, zobacz [asynchroniczne we/wy pliku](../../../standard/io/asynchronous-file-i-o.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak kopiować pliki i katalogi.  
  
 [!code-csharp[csFilesandFolders#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#7)]  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak przenieść pliki i katalogi.  
  
 [!code-csharp[csFilesandFolders#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#8)]  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak usunąć pliki i katalogi.  
  
 [!code-csharp[csFilesandFolders#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#9)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.IO?displayProperty=nameWithType>
- [Przewodnik programowania w języku C#](../index.md)
- [System plików i rejestr (Przewodnik programowania w języku C#)](index.md)
- [Dostarczanie okna dialogowego postępu dla operacji na plikach](how-to-provide-a-progress-dialog-box-for-file-operations.md)
- [We/wy plików i strumieni](../../../standard/io/index.md)
- [Typowe zadania we/wy](../../../standard/io/common-i-o-tasks.md)
