---
title: Typy ogólne i atrybuty — Przewodnik programowania w języku C#
description: Dowiedz się więcej na temat stosowania atrybutów do typów ogólnych. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 17556af2e1bc2963de953cea242d7000509acbcd
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299880"
---
# <a name="generics-and-attributes-c-programming-guide"></a>Typy ogólne i atrybuty (Przewodnik programowania w języku C#)
Atrybuty mogą być stosowane do typów ogólnych w taki sam sposób jak typy nieogólne. Aby uzyskać więcej informacji na temat stosowania atrybutów, zobacz [atrybuty](../concepts/attributes/index.md).  
  
 Atrybuty niestandardowe są dozwolone tylko w celu odwoływania się do otwartych typów ogólnych, które są typami ogólnymi, dla których nie są dostarczane żadne argumenty typu, i zamknięto skonstruowane typy ogólne, które dostarczają argumentów dla wszystkich parametrów typu.  
  
 W poniższych przykładach użyto tego atrybutu niestandardowego:  
  
 [!code-csharp[csProgGuideGenerics#48](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#48)]  
  
 Atrybut może odwoływać się do otwartego typu ogólnego:  
  
 [!code-csharp[csProgGuideGenerics#49](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#49)]  
  
 Określ wiele parametrów typu przy użyciu odpowiedniej liczby przecinków. W tym przykładzie `GenericClass2` ma dwa parametry typu:  
  
 [!code-csharp[csProgGuideGenerics#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#50)]  
  
 Atrybut może odwoływać się do zamkniętego skonstruowanego typu ogólnego:  
  
 [!code-csharp[csProgGuideGenerics#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#51)]  
  
 Atrybut, który odwołuje się do parametru typu ogólnego, spowoduje błąd czasu kompilacji:  
  
 [!code-csharp[csProgGuideGenerics#52](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#52)]  
  
 Typ ogólny nie może dziedziczyć po elemencie <xref:System.Attribute> :  
  
 [!code-csharp[csProgGuideGenerics#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#53)]  
  
 Aby uzyskać informacje o typie ogólnym lub parametrze typu w czasie wykonywania, można użyć metod <xref:System.Reflection> . Aby uzyskać więcej informacji, zobacz [Ogólne i odbicie](./generics-and-reflection.md)  
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../index.md)
- [Typy ogólne](./index.md)
- [Atrybuty](../../../standard/attributes/index.md)
