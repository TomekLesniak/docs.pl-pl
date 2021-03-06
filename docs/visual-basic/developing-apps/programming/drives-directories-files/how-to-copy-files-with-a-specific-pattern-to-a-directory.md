---
title: 'Instrukcje: Kopiowanie plików z określonym wzorcem do katalogu'
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files [Visual Basic], copying
- CopyFile method [Visual Basic], copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: f205d2ad-bbe5-4d55-8a40-acda21aa82dd
ms.openlocfilehash: 7e263e2c9035db54dbb58c6c78c0647d5442504e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401709"
---
# <a name="how-to-copy-files-with-a-specific-pattern-to-a-directory-in-visual-basic"></a>Porady: kopiowanie plików z określonym wzorcem do katalogu w Visual Basic

<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>Metoda zwraca kolekcję ciągów służących tylko do odczytu, reprezentującą nazwy ścieżek dla plików. Możesz użyć parametru, `wildCards` Aby określić konkretny wzorzec.  
  
 Po znalezieniu pasujących plików zwracana jest pusta kolekcja.  
  
 Możesz użyć metody, <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> Aby skopiować pliki do katalogu.  
  
### <a name="to-copy-files-with-a-specific-pattern-to-a-directory"></a>Aby skopiować pliki z określonym wzorcem do katalogu  
  
1. Użyj `GetFiles` metody, aby zwrócić listę plików. Ten przykład zwraca wszystkie pliki. rtf w określonym katalogu.  
  
     [!code-vb[VbFileIOMisc#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#36)]  
  
2. Użyj `CopyFile` metody, aby skopiować pliki. W tym przykładzie pliki są kopiowane do katalogu o nazwie `testdirectory` .  
  
     [!code-vb[VbVbcnMyFileSystem#88](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#88)]  
  
3. Zamknij `For` instrukcję z `Next` instrukcją.  
  
     [!code-vb[VbVbcnMyFileSystem#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#89)]  
  
## <a name="example"></a>Przykład  

 Poniższy przykład przedstawiający powyższe fragmenty kodu w kompletnym formularzu kopiuje wszystkie pliki. rtf w określonym katalogu do katalogu o nazwie `testdirectory` .  
  
 [!code-vb[VbFileIOMisc#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOMisc/VB/Class1.vb#37)]  
  
## <a name="net-framework-security"></a>Zabezpieczenia.NET Framework  

 Następujące warunki mogą spowodować wyjątek:  
  
- Ścieżka jest nieprawidłowa z jednego z następujących powodów: jest ciągiem o zerowej długości, zawiera tylko biały znak, zawiera nieprawidłowe znaki lub jest ścieżką urządzenia (zaczyna się od \\ \\ . \\ ) (<xref:System.ArgumentException>).  
  
- Ścieżka jest nieprawidłowa, ponieważ jest `Nothing` ( <xref:System.ArgumentNullException> ).  
  
- Katalog nie istnieje ( <xref:System.IO.DirectoryNotFoundException> ).  
  
- Katalog wskazuje istniejący plik ( <xref:System.IO.IOException> ).  
  
- Ścieżka przekracza maksymalną długość zdefiniowaną przez system ( <xref:System.IO.PathTooLongException> ).  
  
- Nazwa pliku lub katalogu w ścieżce zawiera dwukropek (:) lub ma nieprawidłowy format ( <xref:System.NotSupportedException> ).  
  
- Użytkownik nie ma wystarczających uprawnień do wyświetlania ścieżki ( <xref:System.Security.SecurityException> ). Użytkownik nie ma wymaganych uprawnień ( <xref:System.UnauthorizedAccessException> ).  
  
## <a name="see-also"></a>Zobacz też

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>
- <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>
- [Instrukcje: Znajdowanie podkatalogów z określonym wzorcem](how-to-find-subdirectories-with-a-specific-pattern.md)
- [Rozwiązywanie problemów: Odczytywanie z plików tekstowych oraz zapisywanie w nich](troubleshooting-reading-from-and-writing-to-text-files.md)
- [Instrukcje: Pobieranie kolekcji plików z katalogu](how-to-get-the-collection-of-files-in-a-directory.md)
