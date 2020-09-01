---
description: Dokumentacja Get-C#
title: Dokumentacja Get-C#
ms.date: 03/10/2017
f1_keywords:
- get_CSharpKeyword
- get
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
ms.openlocfilehash: 7e13dc3ed6577717c64b4e36000a9e090f7b4751
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139739"
---
# <a name="get-c-reference"></a>get (odwołanie w C#)

`get`Słowo kluczowe definiuje metodę *dostępu* we właściwości lub indeksatora, która zwraca wartość właściwości lub element indeksatora. Aby uzyskać więcej informacji, zobacz [Właściwości](../../programming-guide/classes-and-structs/properties.md), [zaimplementowane właściwości](../../programming-guide/classes-and-structs/auto-implemented-properties.md) i [indeksatory](../../programming-guide/indexers/index.md).  
  
W poniższym przykładzie zdefiniowano `get` `set` metodę dostępu a i dla właściwości o nazwie `Seconds` . Używa pola prywatnego o nazwie `_seconds` do wstecz wartości właściwości.  

 [!code-csharp[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
Często `get` metoda dostępu składa się z pojedynczej instrukcji, która zwraca wartość, tak jak w poprzednim przykładzie. Począwszy od języka C# 7,0, można zaimplementować `get` metodę dostępu jako element członkowski będący w postaci wyrażeń. W poniższym przykładzie zaimplementowane są `get` i `set` Akcesory jako elementy członkowskie z wyrażeniami.

 [!code-csharp[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]

W przypadku prostych przypadków, w których właściwości `get` i metody `set` dostępu nie wykonują innej operacji niż ustawienie lub pobranie wartości w prywatnym polu zapasowym, można skorzystać z obsługi kompilatora języka C# dla właściwości, które są implementowane. Poniższy przykład implementuje `Hours` jako właściwość, która jest implementowana.
  
 [!code-csharp[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a>Specyfikacja języka C#

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie w C#](../index.md)
- [Przewodnik programowania w języku C#](../../programming-guide/index.md)
- [Słowa kluczowe języka C#](./index.md)
- [Właściwości](../../programming-guide/classes-and-structs/properties.md)
