---
title: 'Instrukcje: kopiowanie katalogów'
description: Zapoznaj się z tematem jak kopiować katalogi przy użyciu klas we/wy, które synchronicznie kopiują zawartość katalogu do innej lokalizacji.
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET], copying directories
- subdirectory copying
- copying directories
- directories [.NET], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
ms.openlocfilehash: 476473d5c25ce29d070abbeef7fa29a7cb9621e1
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/02/2020
ms.locfileid: "93187986"
---
# <a name="how-to-copy-directories"></a>Instrukcje: kopiowanie katalogów

W tym artykule pokazano, jak używać klas we/wy do synchronicznego kopiowania zawartości katalogu do innej lokalizacji.

Aby zapoznać się z przykładem asynchronicznego kopiowania plików, zobacz [asynchroniczne operacje we/wy na plikach](asynchronous-file-i-o.md).

Ten przykład kopiuje podkatalogi przez ustawienie `copySubDirs` `DirectoryCopy` metody na `true` . `DirectoryCopy`Metoda cyklicznie kopiuje podkatalogi przez wywołanie ich w każdym podkatalogu, dopóki nie będzie więcej do kopiowania.  
  
## <a name="example"></a>Przykład  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="see-also"></a>Zobacz także

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [We/wy plików i strumieni](index.md)
- [Typowe zadania we/wy](common-i-o-tasks.md)
- [Asynchroniczne operacje we/wy pliku](asynchronous-file-i-o.md)
