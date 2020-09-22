---
title: Przestrzeń nazw lub typ określony w elemencie Imports „<qualifiedelementname>” na poziomie projektu nie zawierają żadnego członka publicznego lub nie można go odnaleźć
ms.date: 07/20/2015
f1_keywords:
- vbc40057
- bc40057
helpviewer_keywords:
- BC40057
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
ms.openlocfilehash: e0be18509d0d4b1b4f5eadfadce7a0785e9309f0
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871508"
---
# <a name="namespace-or-type-specified-in-the-project-level-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="d3683-102">Przestrzeń nazw lub typ określony w elemencie Imports „\<qualifiedelementname>” na poziomie projektu nie zawierają żadnego członka publicznego lub nie można go odnaleźć</span><span class="sxs-lookup"><span data-stu-id="d3683-102">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>

<span data-ttu-id="d3683-103">Przestrzeń nazw lub typ określony w elemencie Imports "" na poziomie projektu \<qualifiedelementname> nie zawiera żadnej publicznej składowej lub nie można jej znaleźć.</span><span class="sxs-lookup"><span data-stu-id="d3683-103">Namespace or type specified in the project-level Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="d3683-104">Upewnij się, że przestrzeń nazw lub typ jest zdefiniowany i zawiera co najmniej jedną publiczną składową.</span><span class="sxs-lookup"><span data-stu-id="d3683-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="d3683-105">Upewnij się, że Nazwa aliasu nie zawiera innych aliasów.</span><span class="sxs-lookup"><span data-stu-id="d3683-105">Make sure the alias name doesn't contain other aliases.</span></span>  
  
 <span data-ttu-id="d3683-106">Właściwość Import projektu określa element zawierający, którego nie można odnaleźć lub nie definiuje żadnych `Public` elementów członkowskich.</span><span class="sxs-lookup"><span data-stu-id="d3683-106">An import property of a project specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>  
  
 <span data-ttu-id="d3683-107">*Element zawierający* może być przestrzenią nazw, klasą, strukturą, modułem, interfejsem lub wyliczeniem.</span><span class="sxs-lookup"><span data-stu-id="d3683-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="d3683-108">Element zawierający zawiera elementy członkowskie, takie jak zmienne, procedury lub inne elementy zawierające.</span><span class="sxs-lookup"><span data-stu-id="d3683-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>  
  
 <span data-ttu-id="d3683-109">Celem importowania jest umożliwienie kodowi dostępu do przestrzeni nazw lub typów elementów członkowskich bez konieczności kwalifikowania się do nich.</span><span class="sxs-lookup"><span data-stu-id="d3683-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="d3683-110">W projekcie może być również konieczne dodanie odwołania do przestrzeni nazw lub typu.</span><span class="sxs-lookup"><span data-stu-id="d3683-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="d3683-111">Aby uzyskać więcej informacji, zobacz "Importowanie zawierających elementy" w [odniesieniu do zadeklarowanych elementów](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="d3683-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>  
  
 <span data-ttu-id="d3683-112">Jeśli kompilator nie może znaleźć określonego elementu zawierającego, wówczas nie może rozpoznać odwołań, które go używają.</span><span class="sxs-lookup"><span data-stu-id="d3683-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="d3683-113">Jeśli odnajdzie element, ale element nie ujawnia żadnych `Public` elementów członkowskich, odwołanie nie może się powieść.</span><span class="sxs-lookup"><span data-stu-id="d3683-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="d3683-114">W obu przypadkach nie ma znaczenia, aby zaimportować element.</span><span class="sxs-lookup"><span data-stu-id="d3683-114">In either case it is meaningless to import the element.</span></span>  
  
 <span data-ttu-id="d3683-115">Możesz użyć **projektanta projektu** , aby określić elementy do zaimportowania.</span><span class="sxs-lookup"><span data-stu-id="d3683-115">You use the **Project Designer** to specify elements to import.</span></span> <span data-ttu-id="d3683-116">Użyj sekcji **zaimportowane przestrzenie nazw** na stronie **odwołania** .</span><span class="sxs-lookup"><span data-stu-id="d3683-116">Use the **Imported namespaces** section of the **References** page.</span></span> <span data-ttu-id="d3683-117">Aby uzyskać dostęp do **projektanta projektu** , kliknij dwukrotnie ikonę **mój projekt** w **Eksplorator rozwiązań**.</span><span class="sxs-lookup"><span data-stu-id="d3683-117">You can get to the **Project Designer** by double-clicking the **My Project** icon in **Solution Explorer**.</span></span>  
  
 <span data-ttu-id="d3683-118">**Identyfikator błędu:** BC40057</span><span class="sxs-lookup"><span data-stu-id="d3683-118">**Error ID:** BC40057</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d3683-119">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="d3683-119">To correct this error</span></span>  
  
1. <span data-ttu-id="d3683-120">Otwórz **projektanta projektu** i przejdź do strony **referencyjnej** .</span><span class="sxs-lookup"><span data-stu-id="d3683-120">Open the **Project Designer** and switch to the **Reference** page.</span></span>  
  
2. <span data-ttu-id="d3683-121">W sekcji **zaimportowane przestrzenie nazw** Sprawdź, czy element zawierający jest dostępny z projektu.</span><span class="sxs-lookup"><span data-stu-id="d3683-121">In the **Imported namespaces** section, verify that the containing element is accessible from your project.</span></span>  
  
3. <span data-ttu-id="d3683-122">Sprawdź, czy zawierający element uwidacznia co najmniej jeden `Public` element członkowski.</span><span class="sxs-lookup"><span data-stu-id="d3683-122">Verify that the containing element exposes at least one `Public` member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3683-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="d3683-123">See also</span></span>

- [<span data-ttu-id="d3683-124">Strona odwołań, Projektant projektu (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3683-124">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
- [<span data-ttu-id="d3683-125">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="d3683-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="d3683-126">Publiczne</span><span class="sxs-lookup"><span data-stu-id="d3683-126">Public</span></span>](../modifiers/public.md)
- [<span data-ttu-id="d3683-127">Przestrzenie nazw w Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d3683-127">Namespaces in Visual Basic</span></span>](../../programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="d3683-128">Odwołania do elementów zadeklarowanych</span><span class="sxs-lookup"><span data-stu-id="d3683-128">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)
