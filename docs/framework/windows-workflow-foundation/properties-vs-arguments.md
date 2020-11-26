---
title: Właściwości a Argumenty
ms.date: 03/30/2017
ms.assetid: 14651389-4a49-4cbb-9ddf-c83fdc155df1
ms.openlocfilehash: 2ed443b962e6cccb8a0f670f1dbd744bfa8ed354
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245929"
---
# <a name="properties-vs-arguments"></a>Właściwości a Argumenty

Istnieje kilka opcji przekazywania danych do działania. Poza korzystaniem z programu <xref:System.Activities.InArgument> można również opracowywać działania, które odbierają dane przy użyciu standardowych właściwości środowiska CLR lub <xref:System.Activities.ActivityAction> właściwości publicznych. W tym temacie omówiono sposób wybierania odpowiedniego typu metody.  
  
## <a name="using-clr-properties"></a>Korzystanie z właściwości CLR  

 Podczas przekazywania danych do działania właściwości CLR (czyli metody publiczne używające procedur get i Set do uwidaczniania danych) to opcja, która ma największe ograniczenia. Wartość parametru przekazana do właściwości CLR musi być znana podczas kompilowania rozwiązania; Ta wartość będzie taka sama dla każdego wystąpienia przepływu pracy. W ten sposób wartość przeniesiona do właściwości CLR jest podobna do stałej zdefiniowanej w kodzie; Ta wartość nie może ulec zmianie w okresie istnienia działania i nie można jej zmienić dla różnych wystąpień działania. <xref:System.Activities.Expressions.InvokeMethod%601.MethodName%2A> to przykład właściwości CLR uwidocznionej przez działanie; Nazwa metody, której nie można zmienić w zależności od warunków środowiska uruchomieniowego, i będzie taka sama dla każdego wystąpienia działania.  
  
## <a name="using-arguments"></a>Używanie argumentów  

 Argumenty powinny być używane, gdy dane są oceniane tylko raz w okresie istnienia działania. oznacza to, że jego wartość nie ulegnie zmianie w okresie istnienia działania, ale wartość może być różna dla różnych wystąpień działania. <xref:System.Activities.Statements.If.Condition%2A> jest przykładem wartości, która jest szacowana raz; w związku z tym jest zdefiniowany jako argument. <xref:System.Activities.Statements.WriteLine.Text%2A> jest kolejnym przykładem metody, która powinna być zdefiniowana jako argument, ponieważ jest szacowana tylko raz podczas wykonywania działania, ale może być różna dla różnych wystąpień działania.  
  
## <a name="using-activityaction"></a>Korzystanie z ActivityAction  

 Gdy dane muszą być oceniane wiele razy w okresie istnienia działania, <xref:System.Activities.ActivityAction> powinno być używane. Na przykład <xref:System.Activities.Statements.While.Condition%2A> Właściwość jest oceniana dla każdej iteracji <xref:System.Activities.Statements.While> pętli. Jeśli <xref:System.Activities.InArgument> zostały użyte do tego celu, pętla nigdy nie zostanie zakończona, ponieważ argument nie zostanie obliczony ponownie dla każdej iteracji, i zawsze zwróci ten sam wynik.
