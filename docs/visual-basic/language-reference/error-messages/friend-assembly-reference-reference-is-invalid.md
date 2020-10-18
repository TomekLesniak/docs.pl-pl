---
title: Odwołanie do przyjaznego zestawu „<reference>” jest nieprawidłowe
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: a42dd99ffaa06dce4823ce5d022fac02ae99c6bd
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160714"
---
# <a name="bc31535-friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="fccb5-102">BC31535: odwołanie do zestawu zaprzyjaźnionego \<reference> jest nieprawidłowe</span><span class="sxs-lookup"><span data-stu-id="fccb5-102">BC31535: Friend assembly reference \<reference> is invalid</span></span>

<span data-ttu-id="fccb5-103">Odwołanie do zestawu zaprzyjaźnionego \<reference> jest nieprawidłowe.</span><span class="sxs-lookup"><span data-stu-id="fccb5-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="fccb5-104">Zestawy podpisane silnymi nazwami muszą określać klucz publiczny w swoich deklaracjach InternalsVisibleTo.</span><span class="sxs-lookup"><span data-stu-id="fccb5-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>

 <span data-ttu-id="fccb5-105">Nazwa zestawu przeniesiona do <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> konstruktora atrybutu identyfikuje zestaw o silnej nazwie, ale nie zawiera `PublicKey` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="fccb5-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>

 <span data-ttu-id="fccb5-106">**Identyfikator błędu:** BC31535</span><span class="sxs-lookup"><span data-stu-id="fccb5-106">**Error ID:** BC31535</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="fccb5-107">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="fccb5-107">To correct this error</span></span>

1. <span data-ttu-id="fccb5-108">Określ klucz publiczny dla zestawu o silnej nazwie zaprzyjaźnionej.</span><span class="sxs-lookup"><span data-stu-id="fccb5-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="fccb5-109">Dołącz klucz publiczny jako część nazwy zestawu przesłanej do <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> konstruktora atrybutu przy użyciu `PublicKey` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="fccb5-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>

## <a name="see-also"></a><span data-ttu-id="fccb5-110">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="fccb5-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="fccb5-111">Zaprzyjaźnione zestawy</span><span class="sxs-lookup"><span data-stu-id="fccb5-111">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
