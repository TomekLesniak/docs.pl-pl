---
title: 'Instrukcje: Generowanie modelu i mapowania plików za pomocą EdmGen.exe'
ms.date: 03/30/2017
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
ms.openlocfilehash: 6b41ce971f14938c7bb04a174dbf6029c564c788
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546579"
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>Instrukcje: Generowanie modelu i mapowania plików za pomocą EdmGen.exe
W tym temacie przedstawiono sposób użycia narzędzia Generator EDM (EdmGen.exe) do generowania następujących plików na podstawie szkolnej bazy danych:  
  
- Model koncepcyjny (plik. csdl).  
  
- Model magazynu (plik. ssdl).  
  
- Mapowanie między modelami koncepcyjnymi i magazynowymi (plik. MSL).  
  
- Kod warstwy obiektu w Visual Basic lub C#.  
  
- Wyświetl pliki.  
  
 Narzędzie EdmGen.exe używa/Mode: trybu FullGeneration do generowania plików wymienionych powyżej. Aby uzyskać więcej informacji na temat poleceń EdmGen.exe, zobacz [Generator EDM (EdmGen.exe)](edm-generator-edmgen-exe.md).  
  
 Jeśli używasz EdmGen.exe do wygenerowania modelu i plików mapowania, nadal musisz skonfigurować projekt programu Visual Studio tak, aby korzystał z Entity Framework. Aby uzyskać więcej informacji, zobacz [jak: ręcznie skonfigurować projekt Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100)).  
  
> [!NOTE]
> Model koncepcyjny wygenerowany przez EdmGen.exe zawiera wszystkie obiekty w bazie danych. Jeśli chcesz wygenerować model koncepcyjny, który zawiera tylko określone obiekty, użyj Kreatora Entity Data Model. Aby uzyskać więcej informacji, zobacz [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Aby wygenerować model szkoły dla projektu Visual Basic przy użyciu EdmGen.exe  
  
1. Utwórz bazę danych szkoły. Aby uzyskać więcej informacji, zobacz [Tworzenie przykładowej bazy danych szkoły](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. W wierszu polecenia wykonaj następujące polecenie bez podziałów wierszy:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>Aby wygenerować model szkoły dla projektu C# przy użyciu EdmGen.exe  
  
1. Utwórz bazę danych szkoły. Aby uzyskać więcej informacji, zobacz [Tworzenie przykładowej bazy danych szkoły](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. W wierszu polecenia wykonaj następujące polecenie bez podziałów wierszy:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>Zobacz także

- [Modelowanie i mapowanie](modeling-and-mapping.md)
- [Instrukcje: ręczne Konfigurowanie projektu Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Instrukcje: wstępne Generowanie widoków w celu zwiększenia wydajności zapytań](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Narzędzia Entity Data Model ADO.NET](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Instrukcje: Walidacja modelu i mapowania plików za pomocą EdmGen.exe](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
