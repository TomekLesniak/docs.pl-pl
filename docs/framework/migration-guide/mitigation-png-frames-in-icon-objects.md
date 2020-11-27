---
title: 'Środki zaradcze: ramki PNG w obiektach ikon'
description: Dowiedz się, jak skonfigurować zachowanie ramek PNG w obiektach ikon, jeśli nowe zachowanie zawarte w .NET Framework 4,6 i nowszych jest niepożądane.
ms.date: 03/30/2017
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
ms.openlocfilehash: a8bb4fca19a09f16c89ce8c5da08ebcae9a037ec
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276584"
---
# <a name="mitigation-png-frames-in-icon-objects"></a>Środki zaradcze: ramki PNG w obiektach ikon

Począwszy od .NET Framework 4,6, <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> metoda pomyślnie konwertuje ikony z ramkami PNG na <xref:System.Drawing.Bitmap> obiekty.  
  
 W aplikacjach przeznaczonych dla .NET Framework 4.5.2 i starszych wersji <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> Metoda zgłasza <xref:System.ArgumentOutOfRangeException> wyjątek, jeśli <xref:System.Drawing.Icon> obiekt zawiera ramki PNG.  
  
## <a name="impact"></a>Wpływ  

 Ta zmiana ma wpływ na aplikacje, które są ponownie kompilowane pod kątem .NET Framework 4,6 i implementowanie specjalnej obsługi dla <xref:System.ArgumentOutOfRangeException> , która jest generowany, gdy <xref:System.Drawing.Icon> obiekt ma ramki PNG. W przypadku uruchamiania w .NET Framework 4,6, konwersja kończy się powodzeniem, <xref:System.ArgumentOutOfRangeException> nie jest już zgłaszane i w związku z tym program obsługi wyjątków nie jest już wywoływany.  
  
### <a name="mitigation"></a>Ograniczanie ryzyka  

 Jeśli takie zachowanie jest niepożądane, można zachować poprzednie zachowanie, dodając następujący element do [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) sekcji pliku app.config:  
  
```xml  
<AppContextSwitchOverrides
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
```  
  
 Jeśli plik app.config zawiera już `AppContextSwitchOverrides` element, Nowa wartość powinna być scalona z `value` atrybutem podobnym do tego:  
  
```xml  
<AppContextSwitchOverrides
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;previous key=previous-value" />
```
  
## <a name="see-also"></a>Zobacz też

- [Zgodność aplikacji](application-compatibility.md)
