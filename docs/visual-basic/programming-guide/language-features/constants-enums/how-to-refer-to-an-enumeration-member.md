---
title: 'Porady: odwoływanie się do elementu członkowskiego wyliczenia'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: d1b239e7d6be3ebf1e64d6589a4cc14dce8946f5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095671"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a>Porady: odwoływanie się do elementu członkowskiego wyliczenia (Visual Basic)

Wyliczenia zapewniają wygodny sposób pracy z zestawami powiązanych stałych i kojarzenia wartości stałych z nazwami. Na przykład można zadeklarować Wyliczenie dla zestawu stałych całkowitych skojarzonych z dniami tygodnia, a następnie użyć nazw dni, a nie ich wartości całkowitych w kodzie.  
  
 Można uniknąć używania w pełni kwalifikowanych nazw przy użyciu `Imports` instrukcji. Aby uzyskać więcej informacji, zobacz [wyliczenia i kwalifikowanie nazw](enumerations-and-name-qualification.md).  
  
### <a name="to-refer-to-an-enumeration-member"></a>Aby odwołać się do elementu członkowskiego wyliczenia  
  
- Zakwalifikuj nazwę elementu członkowskiego z wyliczeniem. Na przykład poniższy przykład przypisuje `Saturday` element członkowski `FirstDayOfWeek` wyliczenia do zmiennej `DayValue` .  
  
     [!code-vb[VbEnumsTask#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#19)]  
  
## <a name="see-also"></a>Zobacz także

- [Instrukcje: deklarowanie wyliczenia](how-to-declare-enumerations.md)
- [Wyliczenie i kwantyfikacja nazwy](enumerations-and-name-qualification.md)
- [Porady: iterowanie za pomocą wyliczania w Visual Basic](how-to-iterate-through-an-enumeration.md)
- [Instrukcje: określanie ciągu skojarzonego z wartością wyliczenia](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [Kiedy stosować wyliczanie](when-to-use-an-enumeration.md)
