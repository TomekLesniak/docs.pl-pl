---
title: Erase, instrukcja
ms.date: 07/20/2015
f1_keywords:
- vb.Erase
helpviewer_keywords:
- Erase keyword [Visual Basic]
- Erase statement [Visual Basic]
ms.assetid: 7a8133d7-b750-4d74-8b66-ba1dd9778d4b
ms.openlocfilehash: 33d88b5ce71ceab8d4b4b59d356c53a804c360be
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873294"
---
# <a name="erase-statement-visual-basic"></a><span data-ttu-id="89030-102">Erase — Instrukcja (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="89030-102">Erase Statement (Visual Basic)</span></span>

<span data-ttu-id="89030-103">Używane do zwalniania zmiennych tablicowych i cofania alokacji pamięci używanej dla ich elementów.</span><span class="sxs-lookup"><span data-stu-id="89030-103">Used to release array variables and deallocate the memory used for their elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89030-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="89030-104">Syntax</span></span>  
  
```vb  
Erase arraylist  
```  
  
## <a name="parts"></a><span data-ttu-id="89030-105">Części</span><span class="sxs-lookup"><span data-stu-id="89030-105">Parts</span></span>  

 `arraylist`  
 <span data-ttu-id="89030-106">Wymagany.</span><span class="sxs-lookup"><span data-stu-id="89030-106">Required.</span></span> <span data-ttu-id="89030-107">Lista zmiennych tablicowych, które mają zostać wymazane.</span><span class="sxs-lookup"><span data-stu-id="89030-107">List of array variables to be erased.</span></span> <span data-ttu-id="89030-108">Wiele zmiennych jest oddzielonych przecinkami.</span><span class="sxs-lookup"><span data-stu-id="89030-108">Multiple variables are separated by commas.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89030-109">Uwagi</span><span class="sxs-lookup"><span data-stu-id="89030-109">Remarks</span></span>  

 <span data-ttu-id="89030-110">`Erase`Instrukcja może wystąpić tylko na poziomie procedury.</span><span class="sxs-lookup"><span data-stu-id="89030-110">The `Erase` statement can appear only at procedure level.</span></span> <span data-ttu-id="89030-111">Oznacza to, że można zwolnić tablice wewnątrz procedury, ale nie na poziomie klasy lub modułu.</span><span class="sxs-lookup"><span data-stu-id="89030-111">This means you can release arrays inside a procedure but not at class or module level.</span></span>  
  
 <span data-ttu-id="89030-112">`Erase`Instrukcja jest równoznaczna z przypisaniem `Nothing` do każdej zmiennej tablicowej.</span><span class="sxs-lookup"><span data-stu-id="89030-112">The `Erase` statement is equivalent to assigning `Nothing` to each array variable.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89030-113">Przykład</span><span class="sxs-lookup"><span data-stu-id="89030-113">Example</span></span>  

 <span data-ttu-id="89030-114">Poniższy przykład używa instrukcji, `Erase` Aby wyczyścić dwie tablice i zwolnić pamięć (odpowiednio 1000 i 100 elementów magazynu).</span><span class="sxs-lookup"><span data-stu-id="89030-114">The following example uses the `Erase` statement to clear two arrays and free their memory (1000 and 100 storage elements, respectively).</span></span> <span data-ttu-id="89030-115">`ReDim`Następnie instrukcja przypisuje nowe wystąpienie tablicy do trójwymiarowej tablicy.</span><span class="sxs-lookup"><span data-stu-id="89030-115">The `ReDim` statement then assigns a new array instance to the three-dimensional array.</span></span>  
  
 [!code-vb[VbVbalrStatements#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#19)]  
  
## <a name="see-also"></a><span data-ttu-id="89030-116">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="89030-116">See also</span></span>

- [<span data-ttu-id="89030-117">Nothing</span><span class="sxs-lookup"><span data-stu-id="89030-117">Nothing</span></span>](../nothing.md)
- [<span data-ttu-id="89030-118">ReDim, instrukcja</span><span class="sxs-lookup"><span data-stu-id="89030-118">ReDim Statement</span></span>](redim-statement.md)
