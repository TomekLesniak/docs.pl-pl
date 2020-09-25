---
title: 'Instrukcje: Walidacja modelu i mapowania plików za pomocą EdmGen.exe'
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: 62a3bde9d2431b9e9e86e2a8d8896520f3456590
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198122"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>Instrukcje: Walidacja modelu i mapowania plików za pomocą EdmGen.exe

W tym temacie pokazano, jak za pomocą narzędzia [Generator EDM (EdmGen.exe)](edm-generator-edmgen-exe.md) sprawdzić poprawność modelu i plików mapowania. Aby uzyskać więcej informacji, zobacz [Entity Data Model](../entity-data-model.md).  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>Aby sprawdzić poprawność modelu szkoły przy użyciu EdmGen.exe  
  
1. Utwórz bazę danych szkoły. Aby uzyskać więcej informacji, zobacz [Tworzenie przykładowej bazy danych szkoły](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Generuj model szkoły. Aby uzyskać więcej informacji, zobacz [How to: Use EdmGen.exe by wygenerować model i pliki mapowania](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3. W wierszu polecenia wykonaj następujące polecenie bez podziałów wierszy:  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>Zobacz też

- [Instrukcje: ręczne Konfigurowanie projektu Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Narzędzia Entity Data Model ADO.NET](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Instrukcje: wstępne Generowanie widoków w celu zwiększenia wydajności zapytań](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Instrukcje: Używanie EdmGen.exe, aby wygenerować kod warstwy obiektu](how-to-use-edmgen-exe-to-generate-object-layer-code.md)
