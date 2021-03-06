---
title: Jak czytać z pliku tekstowego — Przewodnik programowania w języku C#
description: Dowiedz się, jak czytać z pliku tekstowego przy użyciu metod statycznych z klasy File. Zobacz przykładowy kod i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
f1_keywords:
- StreamReader.ReadToEnd
helpviewer_keywords:
- text files, writing to
- reading text files
- reading data, text files
- text files, reading
ms.assetid: 92246c5b-e819-4eea-9370-1a9460e12de3
ms.openlocfilehash: 64ac99ec0a72ba7df120f6732edccf160a351738
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201840"
---
# <a name="how-to-read-from-a-text-file-c-programming-guide"></a>Jak czytać z pliku tekstowego (Przewodnik programowania w języku C#)

Ten przykład odczytuje zawartość pliku tekstowego przy użyciu metod statycznych <xref:System.IO.File.ReadAllText%2A> i <xref:System.IO.File.ReadAllLines%2A> z <xref:System.IO.File?displayProperty=nameWithType> klasy.  
  
Aby zapoznać się z przykładem korzystającym z <xref:System.IO.StreamReader> programu, zobacz [jak czytać plik tekstowy po jednym wierszu naraz](./how-to-read-a-text-file-one-line-at-a-time.md).
  
> [!NOTE]
> Pliki, które są używane w tym przykładzie, są tworzone w temacie [jak zapisywać w pliku tekstowym](./how-to-write-to-a-text-file.md).
  
## <a name="example"></a>Przykład  

 [!code-csharp[csFilesandFolders#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#4)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  

 Skopiuj kod i wklej go do aplikacji konsolowej C#.  
  
Jeśli nie używasz plików tekstowych z [metody zapisywania do pliku tekstowego](./how-to-write-to-a-text-file.md), Zamień argument na `ReadAllText` i `ReadAllLines` z odpowiednią ścieżką i nazwą pliku na komputerze.
  
## <a name="robust-programming"></a>Niezawodne programowanie  

 Następujące warunki mogą spowodować wyjątek:  
  
- Plik nie istnieje lub nie istnieje w określonej lokalizacji. Sprawdź ścieżkę i pisownię nazwy pliku.  
  
## <a name="net-security"></a>Zabezpieczenia platformy .NET  

 Nie należy polegać na nazwie pliku, aby ustalić zawartość pliku. Na przykład plik `myFile.cs` może nie być plikiem źródłowym języka C#.  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.IO?displayProperty=nameWithType>
- [Przewodnik programowania w języku C#](../index.md)
- [System plików i rejestr (Przewodnik programowania w języku C#)](./index.md)
