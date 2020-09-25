---
title: Jak uzyskać informacje o plikach, folderach i dyskach — Przewodnik programowania w języku C#
description: Dowiedz się, jak uzyskać informacje o plikach, folderach i dyskach. Zobacz przykład kodu i dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- files [C#], getting information about
ms.assetid: 22fc2da6-5494-405b-995e-c0b99142a93e
ms.openlocfilehash: 7cbaea4dc5381a2ebeb97ce2797ffe850488e126
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170457"
---
# <a name="how-to-get-information-about-files-folders-and-drives--c-programming-guide"></a>Jak uzyskać informacje o plikach, folderach i dyskach (Przewodnik programowania w języku C#)

W programie .NET można uzyskać dostęp do informacji o systemie plików przy użyciu następujących klas:  
  
- <xref:System.IO.FileInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DirectoryInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.DriveInfo?displayProperty=nameWithType>  
  
- <xref:System.IO.Directory?displayProperty=nameWithType>  
  
- <xref:System.IO.File?displayProperty=nameWithType>  
  
 <xref:System.IO.FileInfo>Klasy i <xref:System.IO.DirectoryInfo> reprezentują plik lub katalog i zawierają właściwości, które uwidaczniają wiele atrybutów plików, które są obsługiwane przez system plików NTFS. Zawierają również metody otwierania, zamykania, przechodzenia i usuwania plików i folderów. Wystąpienia tych klas można utworzyć, przekazując ciąg, który reprezentuje nazwę pliku, folderu lub dysku w konstruktorze:  
  
```csharp  
System.IO.DriveInfo di = new System.IO.DriveInfo(@"C:\");  
```  
  
 Można również uzyskać nazwy plików, folderów lub dysków przy użyciu wywołań do <xref:System.IO.DirectoryInfo.GetDirectories%2A?displayProperty=nameWithType> , <xref:System.IO.DirectoryInfo.GetFiles%2A?displayProperty=nameWithType> i <xref:System.IO.DriveInfo.RootDirectory%2A?displayProperty=nameWithType> .  
  
 <xref:System.IO.Directory?displayProperty=nameWithType>Klasy i <xref:System.IO.File?displayProperty=nameWithType> zapewniają statyczne metody pobierania informacji o katalogach i plikach.  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie przedstawiono różne sposoby uzyskiwania dostępu do informacji o plikach i folderach.  
  
 [!code-csharp[csFilesandFolders#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#6)]  
  
## <a name="robust-programming"></a>Niezawodne programowanie  

 Podczas przetwarzania ciągów ścieżki określonych przez użytkownika należy również obsługiwać wyjątki dla następujących warunków:  
  
- Nazwa pliku jest źle sformułowana. Na przykład zawiera nieprawidłowe znaki lub tylko odstęp.  
  
- Nazwa pliku ma wartość null.  
  
- Nazwa pliku jest dłuższa niż zdefiniowana w systemie długość maksymalna.  
  
- Nazwa pliku zawiera dwukropek (:).  
  
 Jeśli aplikacja nie ma wystarczających uprawnień do odczytu określonego pliku, `Exists` Metoda zwraca `false` bez względu na to, czy ścieżka istnieje; metoda nie zgłasza wyjątku.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.IO?displayProperty=nameWithType>
- [Przewodnik programowania w języku C#](../index.md)
- [System plików i rejestr (Przewodnik programowania w języku C#)](./index.md)
