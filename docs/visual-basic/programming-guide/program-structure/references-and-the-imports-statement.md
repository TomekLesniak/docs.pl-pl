---
title: Referencje i instrukcja Imports
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: 13f250e1b015e5a821da83e557033bc878a8a3b8
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097907"
---
# <a name="references-and-the-imports-statement-visual-basic"></a><span data-ttu-id="8a55d-102">Referencje i importy — Instrukcja (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a55d-102">References and the Imports Statement (Visual Basic)</span></span>

<span data-ttu-id="8a55d-103">Obiekty zewnętrzne można udostępnić projekt, wybierając polecenie **Dodaj odwołanie** w menu **projekt** .</span><span class="sxs-lookup"><span data-stu-id="8a55d-103">You can make external objects available to your project by choosing the **Add Reference** command on the **Project** menu.</span></span> <span data-ttu-id="8a55d-104">Odwołania w Visual Basic mogą wskazywać zestawy, które są takie jak biblioteki typów, ale zawierają więcej informacji.</span><span class="sxs-lookup"><span data-stu-id="8a55d-104">References in Visual Basic can point to assemblies, which are like type libraries but contain more information.</span></span>  
  
## <a name="the-imports-statement"></a><span data-ttu-id="8a55d-105">Instrukcja Imports</span><span class="sxs-lookup"><span data-stu-id="8a55d-105">The Imports Statement</span></span>  

 <span data-ttu-id="8a55d-106">Zestawy obejmują co najmniej jedną przestrzeń nazw.</span><span class="sxs-lookup"><span data-stu-id="8a55d-106">Assemblies include one or more namespaces.</span></span> <span data-ttu-id="8a55d-107">Po dodaniu odwołania do zestawu, można również dodać `Imports` instrukcję do modułu, który kontroluje widoczność przestrzeni nazw tego zestawu w module.</span><span class="sxs-lookup"><span data-stu-id="8a55d-107">When you add a reference to an assembly, you can also add an `Imports` statement to a module that controls the visibility of that assembly's namespaces within the module.</span></span> <span data-ttu-id="8a55d-108">`Imports`Instrukcja zawiera kontekst zakresu, który umożliwia użycie tylko części przestrzeni nazw niezbędnej do dostarczenia unikatowego odwołania.</span><span class="sxs-lookup"><span data-stu-id="8a55d-108">The `Imports` statement provides a scoping context that lets you use only the portion of the namespace necessary to supply a unique reference.</span></span>  
  
 <span data-ttu-id="8a55d-109">`Imports`Instrukcja ma następującą składnię:</span><span class="sxs-lookup"><span data-stu-id="8a55d-109">The `Imports` statement has the following syntax:</span></span>  
  
 `Imports [Aliasname =] Namespace`  
  
 <span data-ttu-id="8a55d-110">`Aliasname` odwołuje się do krótkiej nazwy, której można użyć w kodzie, aby odwołać się do zaimportowanej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="8a55d-110">`Aliasname` refers to a short name you can use within code to refer to an imported namespace.</span></span> <span data-ttu-id="8a55d-111">`Namespace` jest przestrzenią nazw dostępną za pomocą odwołania do projektu, za pomocą definicji w ramach projektu lub poprzedniej `Imports` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="8a55d-111">`Namespace` is a namespace available through either a project reference, through a definition within the project, or through a previous `Imports` statement.</span></span>  
  
 <span data-ttu-id="8a55d-112">Moduł może zawierać dowolną liczbę `Imports` instrukcji.</span><span class="sxs-lookup"><span data-stu-id="8a55d-112">A module may contain any number of `Imports` statements.</span></span> <span data-ttu-id="8a55d-113">Muszą one znajdować się po każdej `Option` instrukcji, jeśli jest obecny, ale przed jakimkolwiek innym kodem.</span><span class="sxs-lookup"><span data-stu-id="8a55d-113">They must appear after any `Option` statements, if present, but before any other code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8a55d-114">Nie należy mylić odwołań projektu z `Imports` instrukcją lub `Declare` instrukcją.</span><span class="sxs-lookup"><span data-stu-id="8a55d-114">Do not confuse project references with the `Imports` statement or the `Declare` statement.</span></span> <span data-ttu-id="8a55d-115">Odwołania projektu tworzą obiekty zewnętrzne, takie jak obiekty w zestawach, dostępne do Visual Basic projektów.</span><span class="sxs-lookup"><span data-stu-id="8a55d-115">Project references make external objects, such as objects in assemblies, available to Visual Basic projects.</span></span> <span data-ttu-id="8a55d-116">`Imports`Instrukcja służy do uproszczenia dostępu do odwołań do projektu, ale nie zapewnia dostępu do tych obiektów.</span><span class="sxs-lookup"><span data-stu-id="8a55d-116">The `Imports` statement is used to simplify access to project references, but does not provide access to these objects.</span></span> <span data-ttu-id="8a55d-117">`Declare`Instrukcja jest używana do deklarowania odwołania do procedury zewnętrznej w bibliotece dołączanej dynamicznie (dll).</span><span class="sxs-lookup"><span data-stu-id="8a55d-117">The `Declare` statement is used to declare a reference to an external procedure in a dynamic-link library (DLL).</span></span>  
  
## <a name="using-aliases-with-the-imports-statement"></a><span data-ttu-id="8a55d-118">Używanie aliasów z instrukcją Imports</span><span class="sxs-lookup"><span data-stu-id="8a55d-118">Using Aliases with the Imports Statement</span></span>  

 <span data-ttu-id="8a55d-119">`Imports`Instrukcja ułatwia dostęp do metod klas przez wyeliminowanie konieczności jawnego wpisywania w pełni kwalifikowanych nazw odwołań.</span><span class="sxs-lookup"><span data-stu-id="8a55d-119">The `Imports` statement makes it easier to access methods of classes by eliminating the need to explicitly type the fully qualified names of references.</span></span> <span data-ttu-id="8a55d-120">Aliasy umożliwiają przypisanie nazwy bardziej przyjaznej tylko do jednej części przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="8a55d-120">Aliases let you assign a friendlier name to just one part of a namespace.</span></span> <span data-ttu-id="8a55d-121">Na przykład sekwencja powrotu karetki i wysuwu wiersza, która powoduje, że pojedynczy fragment tekstu, który ma być wyświetlany w wielu wierszach, jest częścią <xref:Microsoft.VisualBasic.ControlChars> modułu w <xref:Microsoft.VisualBasic?displayProperty=nameWithType> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="8a55d-121">For example, the carriage return/line feed sequence that causes a single piece of text to be displayed on multiple lines is part of the <xref:Microsoft.VisualBasic.ControlChars> module in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="8a55d-122">Aby użyć tej stałej w programie bez aliasu, należy wpisać następujący kod:</span><span class="sxs-lookup"><span data-stu-id="8a55d-122">To use this constant in a program without an alias, you would need to type the following code:</span></span>  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 <span data-ttu-id="8a55d-123">`Imports` instrukcje muszą zawsze być pierwszym wierszem bezpośrednio po `Option` instrukcjach w module.</span><span class="sxs-lookup"><span data-stu-id="8a55d-123">`Imports` statements must always be the first lines immediately following any `Option` statements in a module.</span></span> <span data-ttu-id="8a55d-124">Poniższy fragment kodu przedstawia sposób importowania i przypisywania aliasu do <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> modułu:</span><span class="sxs-lookup"><span data-stu-id="8a55d-124">The following code fragment shows how to import and assign an alias to the <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> module:</span></span>  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 <span data-ttu-id="8a55d-125">Przyszłe odwołania do tej przestrzeni nazw mogą być znacznie krótsze:</span><span class="sxs-lookup"><span data-stu-id="8a55d-125">Future references to this namespace can be considerably shorter:</span></span>  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 <span data-ttu-id="8a55d-126">Jeśli `Imports` instrukcja nie zawiera nazwy aliasu, elementy zdefiniowane w zaimportowanej przestrzeni nazw mogą być używane w module bez kwalifikacji.</span><span class="sxs-lookup"><span data-stu-id="8a55d-126">If an `Imports` statement does not include an alias name, elements defined within the imported namespace can be used in the module without qualification.</span></span> <span data-ttu-id="8a55d-127">Jeśli Nazwa aliasu jest określona, musi być używana jako kwalifikator dla nazw zawartych w tej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="8a55d-127">If the alias name is specified, it must be used as a qualifier for names contained within that namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a55d-128">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="8a55d-128">See also</span></span>

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [<span data-ttu-id="8a55d-129">Przestrzenie nazw w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8a55d-129">Namespaces in Visual Basic</span></span>](namespaces.md)
- [<span data-ttu-id="8a55d-130">Zestawy w środowisku .NET</span><span class="sxs-lookup"><span data-stu-id="8a55d-130">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="8a55d-131">Imports — Instrukcja (.NET Namespace i Type)</span><span class="sxs-lookup"><span data-stu-id="8a55d-131">Imports Statement (.NET Namespace and Type)</span></span>](../../language-reference/statements/imports-statement-net-namespace-and-type.md)
