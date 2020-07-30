---
title: Zdarzenia — Przewodnik programowania w języku C#
description: Dowiedz się więcej o zdarzeniach. Zdarzenia umożliwiają klasie lub obiektowi powiadamianie innych klas lub obiektów w przypadku wystąpienia czegoś zainteresowania.
ms.date: 07/20/2015
helpviewer_keywords:
- classes [C#], events
- C# language, events
- events [C#]
ms.assetid: a8e51b22-d294-44fb-9539-0072f06c4cb3
ms.openlocfilehash: 3160d1e381c6cb3af0f017538f9555b3fded9910
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302077"
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
  
- W bibliotece klas .NET Framework zdarzenia są oparte na <xref:System.EventHandler> delegatze i <xref:System.EventArgs> klasie bazowej.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 Aby uzyskać więcej informacji, zobacz:  
  
- [Subskrybowanie i anulowanie subskrypcji zdarzeń](./how-to-subscribe-to-and-unsubscribe-from-events.md)

- [Jak opublikować zdarzenia zgodne z zaleceniami dotyczącymi platformy .NET](./how-to-publish-events-that-conform-to-net-framework-guidelines.md)

- [Wywoływanie zdarzeń klasy podstawowej w klasach pochodnych](./how-to-raise-base-class-events-in-derived-classes.md)

- [Implementowanie zdarzeń interfejsu](./how-to-implement-interface-events.md)

- [Implementowanie niestandardowych metod dostępu zdarzeń](./how-to-implement-custom-event-accessors.md)

## <a name="c-language-specification"></a>Specyfikacja języka C#  

Aby uzyskać więcej informacji, zobacz [zdarzenia](~/_csharplang/spec/classes.md#events) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction). Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.
  
## <a name="featured-book-chapters"></a>Polecane rozdziały książki  
 [Delegaty, zdarzenia i wyrażenia lambda](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518994%28v=orm.10%29) w [języku c# 3,0 Cookbook, wydanie trzecie: więcej niż 250 rozwiązań dla programistów 3,0 c#](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff518995%28v=orm.10%29)  
  
 [Delegaty i zdarzenia](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652490%28v=orm.10%29) w [uczeniu C# 3,0: główne podstawy języka c# 3,0](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v=orm.10%29)  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.EventHandler>
- [Przewodnik programowania w języku C#](../index.md)
- [Delegaci](../delegates/index.md)
- [Tworzenie programów obsługi zdarzeń w formularzach systemu Windows](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
