---
title: Odwołanie do przyjaznego zestawu „<reference>” jest nieprawidłowe
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: 72c030d18d5339908c5088e104f6a8ad3e76943b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874100"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="e0c90-102">Odwołanie do przyjaznego zestawu „\<reference>” jest nieprawidłowe</span><span class="sxs-lookup"><span data-stu-id="e0c90-102">Friend assembly reference \<reference> is invalid</span></span>

<span data-ttu-id="e0c90-103">Odwołanie do zestawu zaprzyjaźnionego \<reference> jest nieprawidłowe.</span><span class="sxs-lookup"><span data-stu-id="e0c90-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="e0c90-104">Zestawy podpisane silnymi nazwami muszą określać klucz publiczny w swoich deklaracjach InternalsVisibleTo.</span><span class="sxs-lookup"><span data-stu-id="e0c90-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="e0c90-105">Nazwa zestawu przeniesiona do <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> konstruktora atrybutu identyfikuje zestaw o silnej nazwie, ale nie zawiera `PublicKey` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="e0c90-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="e0c90-106">**Identyfikator błędu:** BC31535</span><span class="sxs-lookup"><span data-stu-id="e0c90-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e0c90-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="e0c90-107">To correct this error</span></span>  
  
1. <span data-ttu-id="e0c90-108">Określ klucz publiczny dla zestawu o silnej nazwie zaprzyjaźnionej.</span><span class="sxs-lookup"><span data-stu-id="e0c90-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="e0c90-109">Dołącz klucz publiczny jako część nazwy zestawu przesłanej do <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> konstruktora atrybutu przy użyciu `PublicKey` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="e0c90-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c90-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e0c90-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="e0c90-111">Zaprzyjaźnione zestawy</span><span class="sxs-lookup"><span data-stu-id="e0c90-111">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
