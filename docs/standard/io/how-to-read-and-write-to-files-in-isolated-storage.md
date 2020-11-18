---
title: 'Instrukcje: Odczyt i zapis w plikach w izolowanym magazynie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- files, isolated storage
- reading data
- storing data using isolated storage, reading and writing to files
- writing to files within store
- data storage using isolated storage, reading and writing to files
- reading files within store
- isolated storage, reading and writing to files
- data stores, reading and writing to files
- stores, reading and writing to files
ms.assetid: f977ebdc-1b55-475a-bc3d-3376470b08ae
ms.openlocfilehash: eff020ebb1de40f83582bbf872339c7652d1d4b1
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830704"
---
# <a name="how-to-read-and-write-to-files-in-isolated-storage"></a>Instrukcje: Odczyt i zapis w plikach w izolowanym magazynie
Aby odczytywać lub zapisywać dane w pliku w izolowanym magazynie, użyj <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> obiektu z czytnikiem strumienia ( <xref:System.IO.StreamReader> obiektem) lub składnikiem zapisywania strumienia ( <xref:System.IO.StreamWriter> Object).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład kodu uzyskuje izolowany magazyn i sprawdza, czy plik o nazwie TestStore.txt istnieje w magazynie. Jeśli nie istnieje, tworzy plik i zapisuje "Hello izolowany magazyn" do pliku. Jeśli TestStore.txt już istnieje, przykładowy kod odczytuje z pliku.  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>
- <xref:System.IO.FileMode?displayProperty=nameWithType>
- <xref:System.IO.FileAccess?displayProperty=nameWithType>
- <xref:System.IO.StreamReader?displayProperty=nameWithType>
- <xref:System.IO.StreamWriter?displayProperty=nameWithType>
- [We/wy plików i strumieni](index.md)
- [Magazyn izolowany](isolated-storage.md)
