---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 51eaaef2ddb88afbb52ab58b85ed1a58ba251c1e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866447"
---
# <a name="see-visual-basic"></a><span data-ttu-id="de44c-101">\<see> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="de44c-101">\<see> (Visual Basic)</span></span>

<span data-ttu-id="de44c-102">Określa łącze do innego elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="de44c-102">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de44c-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="de44c-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="de44c-104">Parametry</span><span class="sxs-lookup"><span data-stu-id="de44c-104">Parameters</span></span>  

 `member`  
 <span data-ttu-id="de44c-105">Odwołanie do elementu członkowskiego lub pola, które jest dostępne do wywołania z bieżącego środowiska kompilacji.</span><span class="sxs-lookup"><span data-stu-id="de44c-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="de44c-106">Kompilator sprawdza, czy dany element kodu istnieje i przekazuje `member` do nazwy elementu w wyjściowym kodzie XML.</span><span class="sxs-lookup"><span data-stu-id="de44c-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="de44c-107">`member` musi znajdować się w podwójnym cudzysłowie ("").</span><span class="sxs-lookup"><span data-stu-id="de44c-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de44c-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="de44c-108">Remarks</span></span>  

 <span data-ttu-id="de44c-109">Użyj `<see>` znacznika, aby określić łącze z tekstu.</span><span class="sxs-lookup"><span data-stu-id="de44c-109">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="de44c-110">Użyj, [\<seealso>](seealso.md) Aby wskazać tekst, który może być wyświetlany w sekcji "Zobacz też".</span><span class="sxs-lookup"><span data-stu-id="de44c-110">Use [\<seealso>](seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="de44c-111">Kompiluj z [-doc](../../reference/command-line-compiler/doc.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="de44c-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="de44c-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="de44c-112">Example</span></span>  

 <span data-ttu-id="de44c-113">Ten przykład używa `<see>` znacznika w `UpdateRecord` sekcji uwagi, aby odwołać się do `DoesRecordExist` metody.</span><span class="sxs-lookup"><span data-stu-id="de44c-113">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="de44c-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="de44c-114">See also</span></span>

- [<span data-ttu-id="de44c-115">Tagi komentarza XML</span><span class="sxs-lookup"><span data-stu-id="de44c-115">XML Comment Tags</span></span>](index.md)
