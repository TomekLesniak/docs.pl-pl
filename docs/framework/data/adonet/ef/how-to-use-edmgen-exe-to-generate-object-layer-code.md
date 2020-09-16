---
title: 'Instrukcje: Używanie EdmGen.exe, aby wygenerować kod warstwy obiektu'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 9a73a803d310ebd847e49f4bd71609f8ef9f2944
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546643"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a><span data-ttu-id="c3c70-102">Instrukcje: Używanie EdmGen.exe, aby wygenerować kod warstwy obiektu</span><span class="sxs-lookup"><span data-stu-id="c3c70-102">How to: Use EdmGen.exe to Generate Object-Layer Code</span></span>
<span data-ttu-id="c3c70-103">W tym temacie przedstawiono sposób użycia narzędzia [Generator EDM (EdmGen.exe)](edm-generator-edmgen-exe.md) do generowania kodu warstwy obiektu na podstawie pliku. csdl.</span><span class="sxs-lookup"><span data-stu-id="c3c70-103">This topic shows how to use the [EDM Generator (EdmGen.exe)](edm-generator-edmgen-exe.md) tool to generate object-layer code  based on the .csdl file.</span></span>  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a><span data-ttu-id="c3c70-104">Aby wygenerować kod warstwy obiektu dla modelu szkoły dla Visual Basic projektu przy użyciu EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="c3c70-104">To generate object-layer code for the School model for a Visual Basic project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="c3c70-105">Utwórz bazę danych szkoły.</span><span class="sxs-lookup"><span data-stu-id="c3c70-105">Create the School database.</span></span> <span data-ttu-id="c3c70-106">Aby uzyskać więcej informacji, zobacz [Tworzenie przykładowej bazy danych szkoły](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="c3c70-106">For more information, see [Creating the School Sample Database](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="c3c70-107">Wygeneruj model szkoły lub uzyskaj plik uczelni. csdl.</span><span class="sxs-lookup"><span data-stu-id="c3c70-107">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="c3c70-108">Aby uzyskać więcej informacji, zobacz [How to: Use EdmGen.exe by wygenerować model i pliki mapowania](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="c3c70-108">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="c3c70-109">W wierszu polecenia wykonaj następujące polecenie bez podziałów wierszy:</span><span class="sxs-lookup"><span data-stu-id="c3c70-109">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a><span data-ttu-id="c3c70-110">Aby wygenerować kod warstwy obiektu dla modelu szkoły dla projektu C# przy użyciu EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="c3c70-110">To generate object-layer code for the School model for a C# project using EdmGen.exe</span></span>  
  
1. <span data-ttu-id="c3c70-111">Utwórz bazę danych szkoły.</span><span class="sxs-lookup"><span data-stu-id="c3c70-111">Create the School database.</span></span> <span data-ttu-id="c3c70-112">Aby uzyskać więcej informacji, zobacz [Tworzenie przykładowej bazy danych szkoły](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="c3c70-112">For more information, see [Creating the School Sample Database](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="c3c70-113">Wygeneruj model szkoły lub uzyskaj plik uczelni. csdl.</span><span class="sxs-lookup"><span data-stu-id="c3c70-113">Generate the School model or obtain the School.csdl file.</span></span> <span data-ttu-id="c3c70-114">Aby uzyskać więcej informacji, zobacz [How to: Use EdmGen.exe by wygenerować model i pliki mapowania](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span><span class="sxs-lookup"><span data-stu-id="c3c70-114">For more information, see [How to: Use EdmGen.exe to Generate the Model and Mapping Files](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).</span></span>  
  
3. <span data-ttu-id="c3c70-115">W wierszu polecenia wykonaj następujące polecenie bez podziałów wierszy:</span><span class="sxs-lookup"><span data-stu-id="c3c70-115">At the command prompt, execute the following command without line breaks:</span></span>  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c3c70-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="c3c70-116">See also</span></span>

- [<span data-ttu-id="c3c70-117">Modelowanie i mapowanie</span><span class="sxs-lookup"><span data-stu-id="c3c70-117">Modeling and Mapping</span></span>](modeling-and-mapping.md)
- <span data-ttu-id="c3c70-118">[Instrukcje: ręczne Konfigurowanie projektu Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c3c70-118">[How to: Manually Configure an Entity Framework Project](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))</span></span>
- <span data-ttu-id="c3c70-119">[Narzędzia Entity Data Model ADO.NET](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c3c70-119">[ADO.NET Entity Data Model  Tools](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))</span></span>
- <span data-ttu-id="c3c70-120">[Instrukcje: wstępne Generowanie widoków w celu zwiększenia wydajności zapytań](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c3c70-120">[How to: Pre-Generate Views to Improve Query Performance](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))</span></span>
- [<span data-ttu-id="c3c70-121">Instrukcje: Generowanie modelu i mapowania plików za pomocą EdmGen.exe</span><span class="sxs-lookup"><span data-stu-id="c3c70-121">How to: Use EdmGen.exe to Generate the Model and Mapping Files</span></span>](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
