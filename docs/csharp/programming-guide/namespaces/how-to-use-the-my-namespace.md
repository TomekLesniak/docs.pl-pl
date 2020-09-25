---
title: Jak używać mojej przestrzeni nazw — Przewodnik programowania w języku C#
description: Dowiedz się, jak nam w naszym obszarze nazw "my". Przestrzeń nazw "my" zapewnia łatwy i intuicyjny dostęp do kilku klas platformy .NET.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, My namespace access
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
ms.openlocfilehash: 5310b911cc0abf0e82c4dc8efd45eb45ffb94c9d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176230"
---
# <a name="how-to-use-the-my-namespace-c-programming-guide"></a><span data-ttu-id="603d9-104">Jak używać przestrzeni nazw my (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="603d9-104">How to use the My namespace (C# Programming Guide)</span></span>

<span data-ttu-id="603d9-105"><xref:Microsoft.VisualBasic.MyServices>Przestrzeń nazw ( `My` w Visual Basic) zapewnia łatwy i intuicyjny dostęp do kilku klas platformy .NET, co pozwala pisać kod, który współdziała z komputerem, aplikacją, ustawieniami, zasobami itd.</span><span class="sxs-lookup"><span data-stu-id="603d9-105">The <xref:Microsoft.VisualBasic.MyServices> namespace (`My` in Visual Basic) provides easy and intuitive access to a number of .NET classes, enabling you to write code that interacts with the computer, application, settings, resources, and so on.</span></span> <span data-ttu-id="603d9-106">Chociaż pierwotnie zaprojektowane do użytku z Visual Basic, `MyServices` przestrzeń nazw może być używana w aplikacjach C#.</span><span class="sxs-lookup"><span data-stu-id="603d9-106">Although originally designed for use with Visual Basic, the `MyServices` namespace can be used in C# applications.</span></span>  
  
 <span data-ttu-id="603d9-107">Aby uzyskać więcej informacji o używaniu `MyServices` przestrzeni nazw z Visual Basic, zobacz [Programowanie za pomocą My](../../../visual-basic/developing-apps/development-with-my/index.md).</span><span class="sxs-lookup"><span data-stu-id="603d9-107">For more information about using the `MyServices` namespace from Visual Basic, see [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md).</span></span>  
  
## <a name="add-a-reference"></a><span data-ttu-id="603d9-108">Dodaj odwołanie</span><span class="sxs-lookup"><span data-stu-id="603d9-108">Add a reference</span></span>

 <span data-ttu-id="603d9-109">Aby można było używać `MyServices` klas w rozwiązaniu, należy dodać odwołanie do biblioteki Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="603d9-109">Before you can use the `MyServices` classes in your solution, you must add a reference to the Visual Basic library.</span></span>  
  
### <a name="add-a-reference-to-the-visual-basic-library"></a><span data-ttu-id="603d9-110">Dodaj odwołanie do biblioteki Visual Basic</span><span class="sxs-lookup"><span data-stu-id="603d9-110">Add a reference to the Visual Basic library</span></span>  
  
1. <span data-ttu-id="603d9-111">W **Eksplorator rozwiązań**kliknij prawym przyciskiem myszy węzeł **odwołania** i wybierz polecenie **Dodaj odwołanie**.</span><span class="sxs-lookup"><span data-stu-id="603d9-111">In **Solution Explorer**, right-click the **References** node, and select **Add Reference**.</span></span>  
  
2. <span data-ttu-id="603d9-112">Gdy pojawi się okno dialogowe **odwołania** , przewiń w dół listy i wybierz pozycję Microsoft.VisualBasic.dll.</span><span class="sxs-lookup"><span data-stu-id="603d9-112">When the **References** dialog box appears, scroll down the list, and select Microsoft.VisualBasic.dll.</span></span>  
  
     <span data-ttu-id="603d9-113">W sekcji na początku programu może być również uwzględniona następująca linia `using` .</span><span class="sxs-lookup"><span data-stu-id="603d9-113">You might also want to include the following line in the `using` section at the start of your program.</span></span>  
  
     [!code-csharp[csProgGuideNamespaces#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#18)]  
  
## <a name="example"></a><span data-ttu-id="603d9-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="603d9-114">Example</span></span>  

 <span data-ttu-id="603d9-115">Ten przykład wywołuje różne metody statyczne zawarte w `MyServices` przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="603d9-115">This example calls various static methods contained in the `MyServices` namespace.</span></span> <span data-ttu-id="603d9-116">Dla tego kodu do skompilowania do projektu należy dodać odwołanie do Microsoft.VisualBasic.DLL.</span><span class="sxs-lookup"><span data-stu-id="603d9-116">For this code to compile, a reference to Microsoft.VisualBasic.DLL must be added to the project.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#19)]  
  
 <span data-ttu-id="603d9-117">Nie wszystkie klasy w `MyServices` przestrzeni nazw mogą być wywoływane z poziomu aplikacji C#: na przykład <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> Klasa nie jest zgodna.</span><span class="sxs-lookup"><span data-stu-id="603d9-117">Not all the classes in the `MyServices` namespace can be called from a C# application: for example, the <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> class is not compatible.</span></span> <span data-ttu-id="603d9-118">W tym konkretnym przypadku metody statyczne, które są częścią <xref:Microsoft.VisualBasic.FileIO.FileSystem> , które są również zawarte w VisualBasic.dll, można zamiast nich użyć.</span><span class="sxs-lookup"><span data-stu-id="603d9-118">In this particular case, the static methods that are part of <xref:Microsoft.VisualBasic.FileIO.FileSystem>, which are also contained in VisualBasic.dll, can be used instead.</span></span> <span data-ttu-id="603d9-119">Na przykład poniżej przedstawiono sposób korzystania z jednej z tych metod do duplikowania katalogu:</span><span class="sxs-lookup"><span data-stu-id="603d9-119">For example, here is how to use one such method to duplicate a directory:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces3.cs#20)]  
  
## <a name="see-also"></a><span data-ttu-id="603d9-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="603d9-120">See also</span></span>

- [<span data-ttu-id="603d9-121">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="603d9-121">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="603d9-122">Przestrzenie nazw</span><span class="sxs-lookup"><span data-stu-id="603d9-122">Namespaces</span></span>](./index.md)
- [<span data-ttu-id="603d9-123">Używanie przestrzeni nazw</span><span class="sxs-lookup"><span data-stu-id="603d9-123">Using Namespaces</span></span>](./using-namespaces.md)
