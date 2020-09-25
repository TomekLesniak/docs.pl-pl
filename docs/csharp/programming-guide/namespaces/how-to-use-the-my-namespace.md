---
title: Jak używać mojej przestrzeni nazw — Przewodnik programowania w języku C#
description: Dowiedz się, jak nam w naszym obszarze nazw "my". Przestrzeń nazw "my" zapewnia łatwy i intuicyjny dostęp do kilku klas platformy .NET.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
ms.openlocfilehash: 5310b911cc0abf0e82c4dc8efd45eb45ffb94c9d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176230"
---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a>Jak używać przestrzeni nazw my (Przewodnik programowania w języku C#)

<xref:Microsoft.VisualBasic.MyServices>Przestrzeń nazw ( `My` w Visual Basic) zapewnia łatwy i intuicyjny dostęp do kilku klas platformy .NET, co pozwala pisać kod, który współdziała z komputerem, aplikacją, ustawieniami, zasobami itd. Chociaż pierwotnie zaprojektowane do użytku z Visual Basic, `MyServices` przestrzeń nazw może być używana w aplikacjach C#.  
  
 Aby uzyskać więcej informacji o używaniu `MyServices` przestrzeni nazw z Visual Basic, zobacz [Programowanie za pomocą My](../../../visual-basic/developing-apps/development-with-my/index.md).  
  
## <a name="add-a-reference"></a>Dodaj odwołanie

 Aby można było używać `MyServices` klas w rozwiązaniu, należy dodać odwołanie do biblioteki Visual Basic.  
  
### <a name="add-a-reference-to-the-visual-basic-library"></a>Dodaj odwołanie do biblioteki Visual Basic  
  
1. W **Eksplorator rozwiązań**kliknij prawym przyciskiem myszy węzeł **odwołania** i wybierz polecenie **Dodaj odwołanie**.  
  
2. Gdy pojawi się okno dialogowe **odwołania** , przewiń w dół listy i wybierz pozycję Microsoft.VisualBasic.dll.  
  
     W sekcji na początku programu może być również uwzględniona następująca linia `using` .  
  
     [!code-csharp[csProgGuideNamespaces#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#18)]  
  
## <a name="example"></a>Przykład  

 Ten przykład wywołuje różne metody statyczne zawarte w `MyServices` przestrzeni nazw. Dla tego kodu do skompilowania do projektu należy dodać odwołanie do Microsoft.VisualBasic.DLL.  
  
 [!code-csharp[csProgGuideNamespaces#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#19)]  
  
 Nie wszystkie klasy w `MyServices` przestrzeni nazw mogą być wywoływane z poziomu aplikacji C#: na przykład <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> Klasa nie jest zgodna. W tym konkretnym przypadku metody statyczne, które są częścią <xref:Microsoft.VisualBasic.FileIO.FileSystem> , które są również zawarte w VisualBasic.dll, można zamiast nich użyć. Na przykład poniżej przedstawiono sposób korzystania z jednej z tych metod do duplikowania katalogu:  
  
 [!code-csharp[csProgGuideNamespaces#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#20)]  
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Przestrzenie nazw](./index.md)
- [Używanie przestrzeni nazw](./using-namespaces.md)
