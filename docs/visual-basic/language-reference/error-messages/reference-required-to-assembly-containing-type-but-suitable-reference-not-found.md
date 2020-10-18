---
title: Wymagane odwołanie do zestawu „<assemblyidentity>” z typem „<typename>”, ale nie można odnaleźć pasującego odwołania z powodu niejednoznaczności między projektami „<projectname1>” i „<projectname2>”.
ms.date: 07/20/2015
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
ms.openlocfilehash: ca574bfe926b7b9df272e296190b36f8635263db
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162313"
---
# <a name="bc30969-reference-required-to-assembly-assemblyidentity-containing-type-typename-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-projectname1-and-projectname2"></a><span data-ttu-id="cc4f9-102">BC30969: odwołanie wymagane do zestawu " \<assemblyidentity> " zawierającego typ " \<typename> ", ale nie można odnaleźć odpowiedniego odwołania z powodu niejednoznaczności między projektami " \<projectname1> " i " \<projectname2> "</span><span class="sxs-lookup"><span data-stu-id="cc4f9-102">BC30969: Reference required to assembly '\<assemblyidentity>' containing type '\<typename>', but a suitable reference could not be found due to ambiguity between projects '\<projectname1>' and '\<projectname2>'</span></span>

<span data-ttu-id="cc4f9-103">Wyrażenie używa typu, takiego jak Klasa, struktura, interfejs, Wyliczenie lub delegat, który jest zdefiniowany poza projektem.</span><span class="sxs-lookup"><span data-stu-id="cc4f9-103">An expression uses a type, such as a class, structure, interface, enumeration, or delegate, that is defined outside your project.</span></span> <span data-ttu-id="cc4f9-104">Istnieją jednak odwołania do projektu do więcej niż jednego zestawu definiującego ten typ.</span><span class="sxs-lookup"><span data-stu-id="cc4f9-104">However, you have project references to more than one assembly defining that type.</span></span>

 <span data-ttu-id="cc4f9-105">Projekty cytowane tworzą zestawy o tej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="cc4f9-105">The cited projects produce assemblies with the same name.</span></span> <span data-ttu-id="cc4f9-106">W związku z tym kompilator nie może określić, który zestaw ma być używany dla typu, do którego uzyskujesz dostęp.</span><span class="sxs-lookup"><span data-stu-id="cc4f9-106">Therefore, the compiler cannot determine which assembly to use for the type you are accessing.</span></span>

 <span data-ttu-id="cc4f9-107">Aby uzyskać dostęp do typu zdefiniowanego w innym zestawie, kompilator Visual Basic musi mieć odwołanie do tego zestawu.</span><span class="sxs-lookup"><span data-stu-id="cc4f9-107">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="cc4f9-108">Musi to być jedno, niejednoznaczne odwołanie, które nie powoduje cyklicznych odwołań między projektami.</span><span class="sxs-lookup"><span data-stu-id="cc4f9-108">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>

 <span data-ttu-id="cc4f9-109">**Identyfikator błędu:** BC30969</span><span class="sxs-lookup"><span data-stu-id="cc4f9-109">**Error ID:** BC30969</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="cc4f9-110">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="cc4f9-110">To correct this error</span></span>

1. <span data-ttu-id="cc4f9-111">Ustal, który projekt tworzy najlepszy zestaw dla projektu do odwołania.</span><span class="sxs-lookup"><span data-stu-id="cc4f9-111">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="cc4f9-112">W przypadku tej decyzji można użyć kryteriów, takich jak łatwość dostępu do plików i częstotliwość aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="cc4f9-112">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>

2. <span data-ttu-id="cc4f9-113">We właściwościach projektu Dodaj odwołanie do pliku zawierającego zestaw, który definiuje używany typ.</span><span class="sxs-lookup"><span data-stu-id="cc4f9-113">In your project properties, add a reference to the file that contains the assembly that defines the type you are using.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc4f9-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cc4f9-114">See also</span></span>

- [<span data-ttu-id="cc4f9-115">Zarządzanie odwołaniami w projekcie</span><span class="sxs-lookup"><span data-stu-id="cc4f9-115">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="cc4f9-116">Odwołania do elementów zadeklarowanych</span><span class="sxs-lookup"><span data-stu-id="cc4f9-116">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="cc4f9-117">Zarządzanie właściwościami projektów i rozwiązań</span><span class="sxs-lookup"><span data-stu-id="cc4f9-117">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="cc4f9-118">Rozwiązywanie problemów z przerwanymi odwołaniami</span><span class="sxs-lookup"><span data-stu-id="cc4f9-118">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
