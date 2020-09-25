---
title: 'Instrukcje: Używanie EdmGen.exe, aby wygenerować kod warstwy obiektu'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: a243a588dcb6f7e7001de331cb9011a23ee2fdbe
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198226"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a>Instrukcje: Używanie EdmGen.exe, aby wygenerować kod warstwy obiektu

W tym temacie przedstawiono sposób użycia narzędzia [Generator EDM (EdmGen.exe)](edm-generator-edmgen-exe.md) do generowania kodu warstwy obiektu na podstawie pliku. csdl.  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Aby wygenerować kod warstwy obiektu dla modelu szkoły dla Visual Basic projektu przy użyciu EdmGen.exe  
  
1. Utwórz bazę danych szkoły. Aby uzyskać więcej informacji, zobacz [Tworzenie przykładowej bazy danych szkoły](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Wygeneruj model szkoły lub uzyskaj plik uczelni. csdl. Aby uzyskać więcej informacji, zobacz [How to: Use EdmGen.exe by wygenerować model i pliki mapowania](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3. W wierszu polecenia wykonaj następujące polecenie bez podziałów wierszy:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a>Aby wygenerować kod warstwy obiektu dla modelu szkoły dla projektu C# przy użyciu EdmGen.exe  
  
1. Utwórz bazę danych szkoły. Aby uzyskać więcej informacji, zobacz [Tworzenie przykładowej bazy danych szkoły](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Wygeneruj model szkoły lub uzyskaj plik uczelni. csdl. Aby uzyskać więcej informacji, zobacz [How to: Use EdmGen.exe by wygenerować model i pliki mapowania](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3. W wierszu polecenia wykonaj następujące polecenie bez podziałów wierszy:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a>Zobacz też

- [Modelowanie i mapowanie](modeling-and-mapping.md)
- [Instrukcje: ręczne Konfigurowanie projektu Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Narzędzia Entity Data Model ADO.NET](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Instrukcje: wstępne Generowanie widoków w celu zwiększenia wydajności zapytań](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Instrukcje: Generowanie modelu i mapowania plików za pomocą EdmGen.exe](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
