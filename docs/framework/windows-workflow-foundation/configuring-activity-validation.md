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
# <a name="configuring-activity-validation"></a><span data-ttu-id="14228-102">Konfigurowanie walidacji działania</span><span class="sxs-lookup"><span data-stu-id="14228-102">Configuring Activity Validation</span></span>

<span data-ttu-id="14228-103">Sprawdzanie poprawności działania umożliwia autorom działań i identyfikowanie błędów w konfiguracji działania przed jego wykonaniem.</span><span class="sxs-lookup"><span data-stu-id="14228-103">Activity validation enables activity authors and users to identify and report errors in an activity’s configuration prior to its execution.</span></span> <span data-ttu-id="14228-104">Windows Workflow Foundation (WF) oferuje następujące trzy typy weryfikacji aktywności:</span><span class="sxs-lookup"><span data-stu-id="14228-104">Windows Workflow Foundation (WF) provides the following three types of activity validation:</span></span>  
  
- <span data-ttu-id="14228-105">`RequiredArgument` i `OverloadGroup` atrybuty.</span><span class="sxs-lookup"><span data-stu-id="14228-105">`RequiredArgument` and `OverloadGroup` attributes.</span></span>  
  
- <span data-ttu-id="14228-106">Bezwzględna Walidacja oparta na kodzie.</span><span class="sxs-lookup"><span data-stu-id="14228-106">Imperative code-based validation.</span></span>  
  
- <span data-ttu-id="14228-107">Ograniczenia deklaracyjne.</span><span class="sxs-lookup"><span data-stu-id="14228-107">Declarative constraints.</span></span>  
  
 <span data-ttu-id="14228-108">`RequiredArgument` i `OverloadGroup` atrybuty wskazują, że określone argumenty działania są wymagane.</span><span class="sxs-lookup"><span data-stu-id="14228-108">`RequiredArgument` and `OverloadGroup` attributes indicate that certain arguments on an activity are required.</span></span> <span data-ttu-id="14228-109">Bezwzględna Walidacja oparta na kodzie zapewnia prosty sposób, aby działanie zapewniało weryfikację siebie, a ograniczenia deklaracyjne umożliwiają sprawdzenie poprawności działania i jego relacji z zawierającym przepływem pracy.</span><span class="sxs-lookup"><span data-stu-id="14228-109">Imperative code-based validation provides a simple way for an activity to provide validation about itself, and declarative constraints enable validation about the activity and its relationship with the containing workflow.</span></span> <span data-ttu-id="14228-110">Jeśli działanie nie jest prawidłowo skonfigurowane zgodnie z wymaganiami dotyczącymi weryfikacji, zwracane są błędy i ostrzeżenia walidacji.</span><span class="sxs-lookup"><span data-stu-id="14228-110">If an activity is not configured properly according to the validation requirements, validation errors and warnings are returned.</span></span> <span data-ttu-id="14228-111">Jeśli zawierający przepływ pracy jest tworzony za pomocą projektanta przepływów pracy, wszystkie błędy i ostrzeżenia dotyczące walidacji są wyświetlane w projektancie.</span><span class="sxs-lookup"><span data-stu-id="14228-111">If the containing workflow is created using the workflow designer, any validation errors and warnings are displayed in the designer.</span></span> <span data-ttu-id="14228-112">Jeśli przepływ pracy został utworzony poza projektantem przepływu pracy, wszelkie błędy walidacji są zwracane po wywołaniu przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="14228-112">If the workflow is created outside of the workflow designer any validation errors are returned when the workflow is invoked.</span></span> <span data-ttu-id="14228-113">Bez względu na sposób, w jaki przepływ pracy został utworzony, nie można nigdy wykonywać przepływu pracy z błędami walidacji.</span><span class="sxs-lookup"><span data-stu-id="14228-113">Regardless of how the workflow was created, a workflow with validation errors is never allowed to execute.</span></span> <span data-ttu-id="14228-114">Ta sekcja zawiera omówienie tego typu walidacji działań oraz sposobu wywoływania walidacji działania.</span><span class="sxs-lookup"><span data-stu-id="14228-114">This section provides an overview of these types of activity validation and how activity validation is invoked.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14228-115">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="14228-115">In This Section</span></span>  

 [<span data-ttu-id="14228-116">Wymagane argumenty i grupy metod przeciążonych</span><span class="sxs-lookup"><span data-stu-id="14228-116">Required Arguments and Overload Groups</span></span>](required-arguments-and-overload-groups.md)  
 <span data-ttu-id="14228-117">Opisuje sposób używania `RequiredArgument` `OverloadGroup` atrybutów i w celu zapewnienia walidacji.</span><span class="sxs-lookup"><span data-stu-id="14228-117">Describes how to use the `RequiredArgument` and `OverloadGroup` attributes to provide validation.</span></span>  
  
 [<span data-ttu-id="14228-118">Walidacja oparta na kodzie imperatywnym</span><span class="sxs-lookup"><span data-stu-id="14228-118">Imperative Code-Based Validation</span></span>](imperative-code-based-validation.md)  
 <span data-ttu-id="14228-119">Opisuje sposób korzystania z walidacji opartej na kodzie dla <xref:System.Activities.CodeActivity> <xref:System.Activities.NativeActivity> działań i.</span><span class="sxs-lookup"><span data-stu-id="14228-119">Describes how to use code-based validation for <xref:System.Activities.CodeActivity> and <xref:System.Activities.NativeActivity> based activities.</span></span>  
  
 [<span data-ttu-id="14228-120">Ograniczenia deklaratywne</span><span class="sxs-lookup"><span data-stu-id="14228-120">Declarative Constraints</span></span>](declarative-constraints.md)  
 <span data-ttu-id="14228-121">Opisuje sposób użycia ograniczeń deklaratywnych w celu zapewnienia złożonej weryfikacji działań.</span><span class="sxs-lookup"><span data-stu-id="14228-121">Describes how to use declarative constraints to provide complex activity validation.</span></span>  
  
 [<span data-ttu-id="14228-122">Wywoływanie walidacji działania</span><span class="sxs-lookup"><span data-stu-id="14228-122">Invoking Activity Validation</span></span>](invoking-activity-validation.md)  
 <span data-ttu-id="14228-123">W tym artykule omówiono, kiedy weryfikacja aktywności jest wywoływana automatycznie i jak jawnie wywołać walidację.</span><span class="sxs-lookup"><span data-stu-id="14228-123">Discusses when activity validation is invoked automatically and how to explicitly invoke validation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="14228-124">Dokumentacja</span><span class="sxs-lookup"><span data-stu-id="14228-124">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="14228-125">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="14228-125">Related Sections</span></span>
