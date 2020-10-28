---
title: Podstawowe operacje na ciągach w programie .NET
description: Zobacz przykład, który wywołuje wiele metod String.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], examples
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
ms.openlocfilehash: cc04f0c874b732668b4813f8325bd7060927f22a
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889130"
---
# <a name="how-to-perform-basic-string-manipulations-in-net"></a>Instrukcje: wykonywanie podstawowych operacji na ciągach w programie .NET

W poniższym przykładzie zastosowano niektóre metody omówione w temacie [podstawowe operacje na ciągach](basic-string-operations.md) w celu skonstruowania klasy służącej do manipulowania ciągami w sposób, który może znajdować się w rzeczywistej aplikacji. `MailToData`Klasa przechowuje nazwę i adres osoby w osobnych właściwościach i umożliwia łączenie `City` `State` pól, i w postaci `Zip` pojedynczego ciągu do wyświetlania użytkownikowi. Ponadto Klasa umożliwia użytkownikowi wprowadzanie informacji o miejscowości, stanie i kodzie POCZTOWYm jako jednego ciągu; Aplikacja automatycznie analizuje pojedynczy ciąg i wprowadza odpowiednie informacje do odpowiedniej właściwości.  
  
Dla uproszczenia w tym przykładzie użyto aplikacji konsolowej z interfejsem wiersza polecenia.  
  
## <a name="example"></a>Przykład  

[!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
[!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]  
  
Gdy poprzedni kod jest wykonywany, użytkownik zostanie poproszony o wprowadzenie nazwy i adresu. Aplikacja umieszcza informacje w odpowiednich właściwościach i wyświetla informacje z powrotem do użytkownika, tworząc pojedynczy ciąg, który wyświetla miasto, Województwo i informacje o kodzie POCZTOWYm.  
  
## <a name="see-also"></a>Zobacz także

- [Podstawowe operacje na ciągach](basic-string-operations.md)
