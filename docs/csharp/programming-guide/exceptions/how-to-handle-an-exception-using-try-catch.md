---
title: Jak obsłużyć wyjątek przy użyciu przewodnika programowania try-catch-C#
description: Dowiedz się, jak obsłużyć wyjątek przy użyciu bloku try-catch. Zobacz przykładowy kod i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], try/catch blocks
- exceptions [C#], try/catch blocks
- try/catch blocks [C#]
ms.assetid: ca8e3773-980e-4767-8633-7408540e9818
ms.openlocfilehash: 556f4459f5d1f8b7a7419122b640c661e182a51c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178661"
---
# <a name="how-to-handle-an-exception-using-trycatch-c-programming-guide"></a>Jak obsłużyć wyjątek przy użyciu try/catch (Przewodnik programowania w języku C#)

Celem bloku [try-catch](../../language-reference/keywords/try-catch.md) jest przechwycenie i obsłużenie wyjątku wygenerowanego przez kod roboczy. Niektóre wyjątki mogą być obsługiwane w `catch` bloku i problem został rozwiązany bez ponownego zgłaszania wyjątku; jednak częściej, którą można wykonać, jest upewnienie się, że jest zgłaszany odpowiedni wyjątek.  
  
## <a name="example"></a>Przykład  

 W tym przykładzie <xref:System.IndexOutOfRangeException> nie jest to najbardziej odpowiedni wyjątek: jest to <xref:System.ArgumentOutOfRangeException> bardziej zrozumiałe dla metody, ponieważ błąd jest spowodowany przez argument, który został `index` przesłany przez obiekt wywołujący.  
  
 [!code-csharp[csProgGuideExceptions#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#5)]  
  
## <a name="comments"></a>Komentarze  

 Kod, który powoduje, że wyjątek jest ujęty w `try` bloku. `catch`Instrukcja jest dodawana natychmiast po do dojścia `IndexOutOfRangeException` , jeśli wystąpi. `catch`Blok obsługuje `IndexOutOfRangeException` i zgłasza `ArgumentOutOfRangeException` zamiast niego bardziej odpowiedni wyjątek. Aby zapewnić wywołującemu możliwie jak najwięcej informacji, rozważ określenie oryginalnego wyjątku jako <xref:System.Exception.InnerException%2A> nowego wyjątku. Ponieważ <xref:System.Exception.InnerException%2A> Właściwość jest [tylko do odczytu](../../properties.md#read-only), należy przypisać ją w konstruktorze nowego wyjątku.  
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Wyjątki i obsługa wyjątków](./index.md)
- [Obsługa wyjątków](./exception-handling.md)
