---
title: 'Instrukcje: Zapisywanie tekstu w plikach w katalogu Moje dokumenty'
ms.date: 07/20/2015
helpviewer_keywords:
- files [Visual Basic], writing to
- text, writing to files
- examples [Visual Basic], text files
- writing to files [Visual Basic], in My Documents
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
ms.openlocfilehash: bb3a9bdc44f86fbcdb3c56ee088740efdfebe95d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546461"
---
# <a name="how-to-write-text-to-files-in-the-my-documents-directory-in-visual-basic"></a>Porady: zapisywanie tekstu do plików w katalogu Moje dokumenty w Visual Basic

`My.Computer.FileSystem.SpecialDirectories`Obiekt umożliwia dostęp do katalogów specjalnych, takich jak katalog **WebDocuments** .  
  
## <a name="procedure"></a>Procedura  
  
#### <a name="to-write-new-text-files-in-the-my-documents-directory"></a>Aby napisać nowe pliki tekstowe w katalogu Moje dokumenty  
  
1. Użyj `My.Computer.FileSystem.SpecialDirectories.MyDocuments` właściwości, aby podać ścieżkę.  
  
     [!code-vb[VbFileIOWrite#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#1)]  
  
2. Użyj `WriteAllText` metody, aby zapisać tekst do określonego pliku.  
  
     [!code-vb[VbVbcnMyFileSystem#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#14)]  
  
## <a name="example"></a>Przykład  

 [!code-vb[VbFileIOWrite#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbFileIOWrite/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  

 Zamień na `test.txt` nazwę pliku, do którego chcesz pisać.  
  
## <a name="robust-programming"></a>Niezawodne programowanie  

 Ten kod ponownie generuje wszystkie wyjątki, które mogą wystąpić podczas zapisywania tekstu do pliku. Możliwe jest zmniejszenie prawdopodobieństwa wyjątków za pomocą kontrolek Windows Forms, takich jak [OpenFileDialog](/dotnet/desktop/winforms/controls/openfiledialog-component-windows-forms) i składniki [SaveFileDialog](/dotnet/desktop/winforms/controls/savefiledialog-component-windows-forms) , które ograniczają Opcje użytkownika do prawidłowych nazw plików. Korzystanie z tych kontrolek nie jest jednak foolproof. System plików można zmienić między czasem, gdy użytkownik wybierze plik i czas wykonywania kodu. Obsługa wyjątków jest w związku z tym niemal zawsze niepotrzebna podczas pracy z plikami.  
  
## <a name="net-framework-security"></a>Zabezpieczenia.NET Framework  

 Jeśli używasz w kontekście częściowego zaufania, kod może zgłosić wyjątek z powodu niewystarczających uprawnień. Aby uzyskać więcej informacji, zobacz podstawowe informacje o [zabezpieczeniach dostępu kodu](../../../../framework/misc/code-access-security-basics.md).  
  
 Ten przykład tworzy nowy plik. Jeśli aplikacja musi utworzyć plik, aplikacja musi mieć uprawnienie Tworzenie dla tego folderu. Uprawnienia są ustawiane przy użyciu list kontroli dostępu. Jeśli plik już istnieje, aplikacja wymaga tylko uprawnienia Zapis, ale ma mniejsze uprawnienia. Jeśli to możliwe, bezpieczniejsze jest tworzenie pliku podczas wdrażania i udzielanie uprawnień do odczytu tylko do jednego pliku, a nie do przyznawania uprawnień do tworzenia folderów. Ponadto bardziej bezpieczne jest zapisanie danych do folderów użytkowników niż folder główny lub folder **Program Files** . Aby uzyskać więcej informacji, zobacz [Omówienie technologii list ACL](/previous-versions/dotnet/netframework-4.0/ms229742(v=vs.100)).  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.IO.Path.Combine%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>
- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
