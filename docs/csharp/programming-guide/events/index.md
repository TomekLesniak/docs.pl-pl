---
title: Zdarzenia — Przewodnik programowania w języku C#
description: Dowiedz się więcej o zdarzeniach. Zdarzenia umożliwiają klasie lub obiektowi powiadamianie innych klas lub obiektów w przypadku wystąpienia czegoś zainteresowania.
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 14c18006e393dece5d32d30c2a727d797515c779
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167460"
---
# <a name="events-c-programming-guide"></a>Zdarzenia (Przewodnik programowania w języku C#)

Zdarzenia umożliwiają [klasie](../../language-reference/keywords/class.md) lub obiektowi powiadamianie innych klas lub obiektów w przypadku wystąpienia czegoś zainteresowania. Klasa, która wysyła (lub *podnosi*) zdarzenie, jest nazywana *wydawcą* i klasy, które odbierają (lub *obsługują*) zdarzenie są nazywane *subskrybentami*.  
  
W typowej Windows Forms lub aplikacji sieci Web w języku C# zasubskrybujesz zdarzenia wywoływane przez kontrolki, takie jak przyciski i pola listy. Do przeglądania zdarzeń publikowanych przez formant i wybierania tych, które mają być obsługiwane, można użyć zintegrowanego środowiska programistycznego (IDE) języka Visual C#. Środowisko IDE zapewnia łatwy sposób automatycznego dodawania pustej metody obsługi zdarzeń i kodu w celu subskrybowania zdarzenia. Aby uzyskać więcej informacji, zobacz [subskrybowanie i anulowanie subskrypcji zdarzeń](./how-to-subscribe-to-and-unsubscribe-from-events.md).
  
## <a name="events-overview"></a>Przegląd zdarzeń  

 Zdarzenia mają następujące właściwości:  
  
- Wydawca określa, kiedy zdarzenie jest zgłaszane; Subskrybenci określają, jakie działania są podejmowane w odpowiedzi na zdarzenie.  
  
- Wydarzenie może mieć wielu subskrybentów. Subskrybenci mogą obsługiwać wiele zdarzeń z wielu wydawców.  
  
- Zdarzenia, które nie mają subskrybentów nigdy nie są zgłaszane.  
  
- Zdarzenia są zwykle używane do sygnalizowania akcji użytkownika, takich jak kliknięcia przycisków lub menu w graficznym interfejsie użytkownika.  
  
- Gdy zdarzenie ma wielu subskrybentów, programy obsługi zdarzeń są wywoływane synchronicznie, gdy zdarzenie jest zgłaszane. Aby wywoływać zdarzenia asynchronicznie, zobacz [wywoływanie metod synchronicznych asynchronicznie](../../../standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md).  
  
- W bibliotece klas .NET zdarzenia są oparte na <xref:System.EventHandler> delegatze i <xref:System.EventArgs> klasie bazowej.  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 Aby uzyskać więcej informacji, zobacz:  
  
- [Subskrybowanie i anulowanie subskrypcji zdarzeń](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [Publikowanie zdarzeń zgodnych ze wskazówkami dotyczącymi programu .NET](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [Wywoływanie zdarzeń klasy podstawowej w klasach pochodnych](./how-to-raise-base-class-events-in-derived-classes.md)

- [Implementowanie zdarzeń interfejsu](./how-to-implement-interface-events.md)

- [Implementowanie niestandardowych metod dostępu zdarzeń](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a>Specyfikacja języka C#  

Aby uzyskać więcej informacji, zobacz [zdarzenia](~/_csharplang/spec/classes.md#events) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction). Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.
  
## <a name="featured-book-chapters"></a>Polecane rozdziały książki  

 [Delegaty, zdarzenia i wyrażenia lambda](/previous-versions/visualstudio/visual-studio-2008/ff518994(v=orm.10)) w [języku c# 3,0 Cookbook, wydanie trzecie: więcej niż 250 rozwiązań dla programistów 3,0 c#](/previous-versions/visualstudio/visual-studio-2008/ff518995(v=orm.10))  
  
 [Delegaty i zdarzenia](/previous-versions/visualstudio/visual-studio-2008/ff652490(v=orm.10)) w [uczeniu C# 3,0: główne podstawy języka c# 3,0](/previous-versions/visualstudio/visual-studio-2008/ff652493(v=orm.10))  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.EventHandler>
- [Przewodnik programowania w języku C#](../index.md)
- [Delegaci](../delegates/index.md)
- [Tworzenie programów obsługi zdarzeń w formularzach systemu Windows](/dotnet/desktop/winforms/creating-event-handlers-in-windows-forms)
