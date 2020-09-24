---
title: Typy danych podstawowych
ms.date: 03/30/2017
ms.assetid: eca2c472-9548-4800-bd31-5d8d9f11752b
ms.openlocfilehash: ae561bad3315977ba12dd0e12abda1da163ca456
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156020"
---
# <a name="basic-data-types"></a>Typy danych podstawowych

Ponieważ zapytania LINQ to SQL przekładają się na Transact-SQL przed wykonaniem na Microsoft SQL Server. LINQ to SQL obsługuje wiele z tych samych wbudowanych funkcji, które SQL Server dla podstawowych typów danych.  
  
## <a name="casting"></a>Rzutowanie  

 Rzuty niejawne lub jawne są włączane ze źródłowego typu CLR do docelowego typu CLR, jeśli istnieje podobna prawidłowa konwersja w SQL Server. Aby uzyskać więcej informacji na temat rzutowania CLR, zobacz [Funkcja CType](../../../../../visual-basic/language-reference/functions/ctype-function.md) (Visual Basic) i [Operatory przerzutowania typu](../../../../../csharp/language-reference/operators/type-testing-and-cast.md). Po konwersji rzuty zmieniają zachowanie operacji wykonywanych w wyrażeniu CLR w celu dopasowania ich zachowania do innych wyrażeń CLR, które w sposób naturalny są mapowane na typ docelowy. Rzutowania są również tłumaczenia w kontekście mapowania dziedziczenia. Obiekty mogą być rzutowane na bardziej konkretne podtypy jednostek, aby można było uzyskać dostęp do ich danych specyficznych dla typu.  
  
## <a name="equality-operators"></a>Operatory równości  

 LINQ to SQL obsługuje następujące operatory równości dla podstawowych typów danych wewnątrz zapytań LINQ to SQL:  
  
- Operator równości i nierówności: operatory równości i nierówności są obsługiwane w przypadku typów numerycznych, <xref:System.Boolean> , <xref:System.DateTime> i <xref:System.TimeSpan> . Aby uzyskać więcej informacji na temat operatorów Visual Basic `=` i `<>` , zobacz [Operatory porównania](../../../../../visual-basic/language-reference/operators/comparison-operators.md). Aby uzyskać więcej informacji na temat operatorów porównania C# `==` i `!=` , zobacz [Operatory równości](../../../../../csharp/language-reference/operators/equality-operators.md).
  
- IS — operator: `IS` operator ma obsługiwane tłumaczenie, gdy jest używane mapowanie dziedziczenia. Można go użyć zamiast bezpośredniego testowania kolumny rozróżniacza, aby określić, czy obiekt jest określonego typu jednostki, i jest tłumaczony na sprawdzenie kolumny dyskryminatora. Aby uzyskać więcej informacji na temat operatorów Visual Basic i C#, zobacz [is operator](../../../../../visual-basic/language-reference/operators/is-operator.md) i [is](../../../../../csharp/language-reference/operators/type-testing-and-cast.md#is-operator).  
  
## <a name="see-also"></a>Zobacz też

- [Mapowania typów środowiska SQL-CLR](sql-clr-type-mapping.md)
- [Typy danych i funkcje](data-types-and-functions.md)
