---
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 6e9f63e4d31df7790f51ae4d166b606f2c63f14b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872971"
---
# <a name="example-visual-basic"></a><span data-ttu-id="a3d68-101">\<example> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a3d68-101">\<example> (Visual Basic)</span></span>

<span data-ttu-id="a3d68-102">Określa przykład dla elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="a3d68-102">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3d68-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="a3d68-103">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3d68-104">Parametry</span><span class="sxs-lookup"><span data-stu-id="a3d68-104">Parameters</span></span>  

 `description`  
 <span data-ttu-id="a3d68-105">Opis przykładu kodu.</span><span class="sxs-lookup"><span data-stu-id="a3d68-105">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3d68-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="a3d68-106">Remarks</span></span>  

 <span data-ttu-id="a3d68-107">`<example>`Tag pozwala określić przykład użycia metody lub innego elementu członkowskiego biblioteki.</span><span class="sxs-lookup"><span data-stu-id="a3d68-107">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="a3d68-108">Zwykle obejmuje to użycie [\<code>](code.md) znacznika.</span><span class="sxs-lookup"><span data-stu-id="a3d68-108">This commonly involves using the [\<code>](code.md) tag.</span></span>  
  
 <span data-ttu-id="a3d68-109">Kompiluj z [-doc](../../reference/command-line-compiler/doc.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="a3d68-109">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3d68-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="a3d68-110">Example</span></span>  

 <span data-ttu-id="a3d68-111">W tym przykładzie użyto `<example>` znacznika, aby dołączyć przykład do użycia `ID` pola.</span><span class="sxs-lookup"><span data-stu-id="a3d68-111">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a3d68-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a3d68-112">See also</span></span>

- [<span data-ttu-id="a3d68-113">Tagi komentarza XML</span><span class="sxs-lookup"><span data-stu-id="a3d68-113">XML Comment Tags</span></span>](index.md)
