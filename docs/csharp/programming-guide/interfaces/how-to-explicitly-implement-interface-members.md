---
title: Jak jawnie zaimplementować członków interfejsu — Przewodnik programowania w języku C#
description: Dowiedz się, jak jawnie zaimplementować elementy członkowskie interfejsu w tym przykładzie w języku C#. Dostęp do członków uzyskuje się za pomocą wystąpienia interfejsu.
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: 35b512ff6cbee1dd942f5b3476db660481808297
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303078"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a>Jak jawnie zaimplementować członków interfejsu (Przewodnik programowania w języku C#)
Ten przykład deklaruje [interfejs](../../language-reference/keywords/interface.md), `IDimensions` i klasę, `Box` , która jawnie implementuje elementy członkowskie interfejsu `GetLength` i `GetWidth` . Dostęp do członków uzyskuje się za pomocą wystąpienia interfejsu `dimensions` .  
  
## <a name="example"></a>Przykład  
 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a>Niezawodne programowanie  
  
- Zwróć uwagę, że następujące wiersze w `Main` metodzie są oznaczone jako komentarze, ponieważ spowodują błędy kompilacji. Nie można uzyskać dostępu do elementu członkowskiego interfejsu, który jest jawnie zaimplementowany z wystąpienia [klasy](../../language-reference/keywords/class.md) :  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- Zwróć również uwagę, że w `Main` metodzie pomyślnie Wydrukowano Wymiary pola, ponieważ metody są wywoływane z wystąpienia interfejsu:  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Klasy i struktury](../classes-and-structs/index.md)
- [Interfejsy](./index.md)
- [Jawne implementowanie elementów dwóch interfejsów](./how-to-explicitly-implement-members-of-two-interfaces.md)
