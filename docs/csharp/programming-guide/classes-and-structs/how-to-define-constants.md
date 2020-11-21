---
title: 'Porada: definiowanie stałych w języku C#'
description: Dowiedz się, jak definiować stałe w języku C#, które są polami, których wartości są ustawiane w czasie kompilacji. Użyj stałych, aby podać znaczące nazwy dla specjalnych wartości.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: 42ea67e9012fd55fbceb8a7bad4c8df8bf6bf6da
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099390"
---
# <a name="how-to-define-constants-in-c"></a>Jak definiować stałe w języku C\#

Stałe są polami, których wartości są ustawiane w czasie kompilacji i nigdy nie mogą być zmieniane. Użyj stałych, aby podać znaczące nazwy zamiast literałów liczbowych ("liczby magiczne") dla specjalnych wartości.  
  
> [!NOTE]
> W języku C# dyrektywa preprocesora [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) nie może służyć do definiowania stałych w sposób, który jest zazwyczaj używany w C i C++.  
  
 Aby zdefiniować stałe wartości typów całkowitych ( `int` , `byte` , i tak dalej), użyj typu wyliczeniowego. Aby uzyskać więcej informacji, zobacz [Wyliczenie](../../language-reference/builtin-types/enum.md).  
  
 Aby zdefiniować niecałkowite stałe, jedno podejście polega na pogrupowania ich w pojedynczej klasie statycznej o nazwie `Constants` . To wymaga, aby wszystkie odwołania do stałych były poprzedzone nazwą klasy, jak pokazano w poniższym przykładzie.  
  
## <a name="example"></a>Przykład  

 [!code-csharp[csProgGuideObjects#89](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#89)]  
  
 Użycie kwalifikatora nazwy klasy pomaga upewnić się, że i inne osoby, które używają stałej, wiedzą, że jest stała i nie mogą być modyfikowane.  
  
## <a name="see-also"></a>Zobacz także

- [Klasy i struktury](./index.md)
