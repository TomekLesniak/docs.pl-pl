---
title: 'Porady: pobieranie zawartości katalogu Moje dokumenty'
ms.date: 07/20/2015
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
ms.openlocfilehash: cf4470020507c581999b9d72602ddb6e3e76ed74
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/15/2020
ms.locfileid: "74334537"
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a>Porady: pobieranie zawartości katalogu Moje dokumenty w Visual Basic

<xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> Obiekt może być używany do odczytywania z wielu katalogów **użytkowników** , takich jak **Moje dokumenty** lub **pulpit**.  
  
### <a name="to-read-from-the-my-documents-folder"></a>Aby czytać z folderu Moje dokumenty  
  
- Użyj metody `ReadAllText` , aby odczytać tekst z każdego pliku w określonym katalogu. Poniższy kod określa katalog i plik, a następnie używa `ReadAllText` do odczytywania ich w postaci ciągu o `patients`nazwie.  
  
     [!code-vb[VbVbcnMyFileSystem#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
