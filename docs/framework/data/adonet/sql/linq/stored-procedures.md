---
title: Procedury składowane
ms.date: 03/30/2017
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
ms.openlocfilehash: 57420d95ec27af3b572940202fb6bc288c6888da
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203517"
---
# <a name="stored-procedures"></a>Procedury składowane

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] używa metod w modelu obiektu do reprezentowania procedur składowanych w bazie danych. Należy wyznaczyć metody jako procedury składowane, stosując <xref:System.Data.Linq.Mapping.FunctionAttribute> atrybut i, w razie potrzeby, <xref:System.Data.Linq.Mapping.ParameterAttribute> atrybut. Aby uzyskać więcej informacji, zobacz [model obiektów LINQ to SQL](the-linq-to-sql-object-model.md).  
  
 Deweloperzy korzystający z programu Visual Studio zwykle używają Object Relational Designer, aby mapować procedury składowane. W tematach w tej sekcji pokazano, jak tworzyć i wywoływać te metody w aplikacji, jeśli piszesz kod samodzielnie.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Instrukcje: Zwracane zestawy wierszy](how-to-return-rowsets.md)  
 Opisuje sposób zwracania wierszy danych i pokazuje, jak używać parametru wejściowego.  
  
 [Instrukcje: Używanie procedur składowanych, które przyjmują parametry](how-to-use-stored-procedures-that-take-parameters.md)  
 Opisuje sposób używania parametrów wejściowych i wyjściowych.  
  
 [Instrukcje: Używanie procedur składowanych zamapowanych na wiele kształtów wyników](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 Opisuje, jak zapewnić zwroty wielu kształtów w tej samej procedurze składowanej.  
  
 [Instrukcje: Używanie procedur składowanych zamapowanych na sekwencyjne kształty wyników](how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 Opisuje, w jaki sposób zapewnić wiele kształtów, w których jest znana sekwencja powrotu.  
  
 [Dostosowywanie operacji przy użyciu procedur składowanych](customizing-operations-by-using-stored-procedures.md)  
 Opisuje, jak używać procedur składowanych do implementowania operacji INSERT, Update i DELETE.  
  
 [Dostosowywanie operacji przy użyciu wyłącznie procedur składowanych](customizing-operations-by-using-stored-procedures-exclusively.md)  
 Opisuje, jak używać niczego, ale procedury składowane do implementowania operacji INSERT, Update i DELETE.  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Przewodnik programowania](programming-guide.md)  
 Zawiera informacje o sposobach tworzenia i używania [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modelu obiektów.  
  
 [Przewodnik: Używanie tylko procedur składowanych (Visual Basic)](walkthrough-using-only-stored-procedures-visual-basic.md)  
 Obejmuje procedury, które ilustrują sposób korzystania z procedur składowanych w Visual Basic.  
  
 [Przewodnik: Używanie tylko procedur składowanych (C#)](walkthrough-using-only-stored-procedures-csharp.md)  
 Obejmuje procedury, które ilustrują sposób korzystania z procedur składowanych w języku C#.
