---
title: Jak pisać do pliku tekstowego — Przewodnik programowania w języku C#
description: Dowiedz się, jak napisać plik tekstowy przy użyciu języka C#. Zobacz kilka przykładów kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: 4108163121d56268b810121ca3ae2b2c1338aeab
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301648"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Jak pisać do pliku tekstowego (Przewodnik programowania w języku C#)
W poniższych przykładach pokazano różne sposoby zapisywania tekstu w pliku. Pierwsze dwa przykłady używają statycznych metod dogodnych na <xref:System.IO.File?displayProperty=nameWithType> klasie, aby napisać każdy element dowolnego `IEnumerable<string>` i ciągu do pliku tekstowego. Przykład 3 pokazuje, jak dodać tekst do pliku, gdy trzeba przetwarzać każdy wiersz indywidualnie podczas zapisu w pliku. Przykłady 1-3 Zastąp całą istniejącą zawartość pliku, ale przykład 4 pokazuje, jak dołączyć tekst do istniejącego pliku.  
  
 Te przykłady umożliwiają zapisanie literałów ciągu do plików. Jeśli chcesz sformatować tekst zapisany w pliku, użyj <xref:System.String.Format%2A> metody [interpolacji ciągu](../../language-reference/tokens/interpolated.md) języka C#.  
  
## <a name="example"></a>Przykład  
 [!code-csharp[csFilesandFolders#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#3)]  
  
## <a name="robust-programming"></a>Niezawodne programowanie  
 Następujące warunki mogą spowodować wyjątek:  
  
- Plik istnieje i jest tylko do odczytu.  
  
- Nazwa ścieżki może być za długa.  
  
- Dysk może być zapełniony.  
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [System plików i rejestr (Przewodnik programowania w języku C#)](./index.md)
- [Przykład: zapisywanie kolekcji w magazynie aplikacji](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
