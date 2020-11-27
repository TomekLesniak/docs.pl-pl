---
title: Konfigurowanie walidacji działania
ms.date: 03/30/2017
ms.assetid: 25a4eccb-b8fc-4857-a01d-2683b6341219
ms.openlocfilehash: c3e10fc096b16ef2cf7a6c7533ac9bad8c5ec205
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288960"
---
# <a name="configuring-activity-validation"></a>Konfigurowanie walidacji działania

Sprawdzanie poprawności działania umożliwia autorom działań i identyfikowanie błędów w konfiguracji działania przed jego wykonaniem. Windows Workflow Foundation (WF) oferuje następujące trzy typy weryfikacji aktywności:  
  
- `RequiredArgument` i `OverloadGroup` atrybuty.  
  
- Bezwzględna Walidacja oparta na kodzie.  
  
- Ograniczenia deklaracyjne.  
  
 `RequiredArgument` i `OverloadGroup` atrybuty wskazują, że określone argumenty działania są wymagane. Bezwzględna Walidacja oparta na kodzie zapewnia prosty sposób, aby działanie zapewniało weryfikację siebie, a ograniczenia deklaracyjne umożliwiają sprawdzenie poprawności działania i jego relacji z zawierającym przepływem pracy. Jeśli działanie nie jest prawidłowo skonfigurowane zgodnie z wymaganiami dotyczącymi weryfikacji, zwracane są błędy i ostrzeżenia walidacji. Jeśli zawierający przepływ pracy jest tworzony za pomocą projektanta przepływów pracy, wszystkie błędy i ostrzeżenia dotyczące walidacji są wyświetlane w projektancie. Jeśli przepływ pracy został utworzony poza projektantem przepływu pracy, wszelkie błędy walidacji są zwracane po wywołaniu przepływu pracy. Bez względu na sposób, w jaki przepływ pracy został utworzony, nie można nigdy wykonywać przepływu pracy z błędami walidacji. Ta sekcja zawiera omówienie tego typu walidacji działań oraz sposobu wywoływania walidacji działania.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Wymagane argumenty i grupy metod przeciążonych](required-arguments-and-overload-groups.md)  
 Opisuje sposób używania `RequiredArgument` `OverloadGroup` atrybutów i w celu zapewnienia walidacji.  
  
 [Walidacja oparta na kodzie imperatywnym](imperative-code-based-validation.md)  
 Opisuje sposób korzystania z walidacji opartej na kodzie dla <xref:System.Activities.CodeActivity> <xref:System.Activities.NativeActivity> działań i.  
  
 [Ograniczenia deklaratywne](declarative-constraints.md)  
 Opisuje sposób użycia ograniczeń deklaratywnych w celu zapewnienia złożonej weryfikacji działań.  
  
 [Wywoływanie walidacji działania](invoking-activity-validation.md)  
 W tym artykule omówiono, kiedy weryfikacja aktywności jest wywoływana automatycznie i jak jawnie wywołać walidację.  
  
## <a name="reference"></a>Dokumentacja  
  
## <a name="related-sections"></a>Sekcje pokrewne
