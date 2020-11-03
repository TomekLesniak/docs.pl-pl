---
title: Tworzenie szablonów i korzystanie z nich
ms.date: 07/20/2015
helpviewer_keywords:
- components [Visual Basic]
ms.assetid: ee6a4156-73f7-4e9b-8e01-c74c4798b65c
ms.openlocfilehash: 106b8791ee5cb3db95759ccca2fddd799661ef3c
ms.sourcegitcommit: 74d05613d6c57106f83f82ce8ee71176874ea3f0
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2020
ms.locfileid: "93282060"
---
# <a name="creating-and-using-components-in-visual-basic"></a>Tworzenie składników i korzystanie z nich w Visual Basic

*Składnik* jest klasą, która implementuje <xref:System.ComponentModel.IComponent?displayProperty=nameWithType> interfejs lub który dziedziczy bezpośrednio lub pośrednio z klasy implementującej <xref:System.ComponentModel.IComponent> . Składnik .NET to obiekt, który jest wielokrotnego użytku, może współdziałać z innymi obiektami i zapewnia kontrolę nad zasobami zewnętrznymi i obsługą czasu projektowania.  
  
 Ważną cechą składników jest możliwość projektowania, co oznacza, że Klasa, która jest składnikiem, może być używana w zintegrowanym środowisku programistycznym programu Visual Studio. Składnik może być dodany do przybornika, przeciągany i upuszczany na formularz oraz do manipulowania na powierzchni projektowej. Podstawowa obsługa czasu projektowania składników jest wbudowana w platformę .NET. Deweloper składnika nie musi wykonywać żadnych dodatkowych czynności, aby korzystać z podstawowych funkcji czasu projektowania.  
  
 *Kontrolka* jest podobna do składnika, zarówno do projektowania. Jednak formant udostępnia interfejs użytkownika, natomiast składnik nie jest. Kontrolka musi być pochodną jednej z klas podstawowych formantów: <xref:System.Windows.Forms.Control> lub <xref:System.Web.UI.Control> .  
  
## <a name="when-to-create-a-component"></a>Kiedy należy utworzyć składnik  

 Jeśli Klasa zostanie użyta na powierzchni projektowej (takiej jak Windows Forms lub Projektant formularzy Web Forms), ale nie ma interfejsu użytkownika, powinien być składnikiem i implementować <xref:System.ComponentModel.IComponent> lub pochodzić od klasy, która bezpośrednio lub pośrednio implementuje <xref:System.ComponentModel.IComponent> .  
  
 <xref:System.ComponentModel.Component>Klasy i <xref:System.ComponentModel.MarshalByValueComponent> to podstawowe implementacje <xref:System.ComponentModel.IComponent> interfejsu. Główna różnica między tymi klasami polega na tym, że <xref:System.ComponentModel.Component> Klasa jest organizowana przez odwołanie, podczas gdy <xref:System.ComponentModel.IComponent> jest organizowane przez wartość. Poniższa lista zawiera szczegółowe wskazówki dotyczące implementacji.  
  
- Jeśli składnik musi być zorganizowany przez odwołanie, pochodzi od <xref:System.ComponentModel.Component> .  
  
- Jeśli składnik musi być zorganizowany przez wartość, pochodzi od <xref:System.ComponentModel.MarshalByValueComponent> .  
  
- Jeśli składnik nie może pochodzić z jednej z implementacji podstawowych z powodu pojedynczego dziedziczenia, zaimplementuj <xref:System.ComponentModel.IComponent> .  
  
## <a name="component-classes"></a>Klasy składników  

 <xref:System.ComponentModel>Przestrzeń nazw zawiera klasy, które są używane do implementowania działania składników i formantów w czasie wykonywania oraz w czasie projektowania. Ta przestrzeń nazw zawiera klasy bazowe i interfejsy służące do implementowania atrybutów i konwerterów typów, powiązania ze źródłami danych i składnikami licencjonowania.  
  
 Podstawowe klasy składników to:  
  
- <xref:System.ComponentModel.Component>. Podstawowa implementacja dla <xref:System.ComponentModel.IComponent> interfejsu. Ta klasa umożliwia udostępnianie obiektów między aplikacjami.  
  
- <xref:System.ComponentModel.MarshalByValueComponent>. Podstawowa implementacja dla <xref:System.ComponentModel.IComponent> interfejsu.  
  
- <xref:System.ComponentModel.Container>. Podstawowa implementacja <xref:System.ComponentModel.IContainer> interfejsu. Ta klasa hermetyzuje zero lub więcej składników.  
  
 Niektóre klasy używane do licencjonowania składników są następujące:  
  
- <xref:System.ComponentModel.License>. Abstrakcyjna klasa bazowa dla wszystkich licencji. Licencja jest udzielana do określonego wystąpienia składnika.  
  
- <xref:System.ComponentModel.LicenseManager>. Zawiera właściwości i metody umożliwiające dodanie licencji do składnika i zarządzanie programem <xref:System.ComponentModel.LicenseProvider> .  
  
- <xref:System.ComponentModel.LicenseProvider>. Abstrakcyjna klasa bazowa służąca do implementowania dostawcy licencji.  
  
- <xref:System.ComponentModel.LicenseProviderAttribute>. Określa <xref:System.ComponentModel.LicenseProvider> klasę, która ma być używana z klasą.  
  
 Klasy często używane do opisywania i utrwalania składników.  
  
- <xref:System.ComponentModel.TypeDescriptor>. Zawiera informacje o charakterystyce składnika, takie jak jego atrybuty, właściwości i zdarzenia.  
  
- <xref:System.ComponentModel.EventDescriptor>. Zawiera informacje o zdarzeniu.  
  
- <xref:System.ComponentModel.PropertyDescriptor>. Zawiera informacje o właściwości.  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Rozwiązywanie problemów związanych z formantami oraz autoryzacją elementów](/dotnet/desktop/winforms/controls/troubleshooting-control-and-component-authoring)  
 Wyjaśnia, jak rozwiązać typowe problemy.  
  
## <a name="see-also"></a>Zobacz także

- [Instrukcje: dostęp do Design-Time pomocy technicznej w programie Windows Forms](/dotnet/desktop/winforms/controls/developing-windows-forms-controls-at-design-time)
