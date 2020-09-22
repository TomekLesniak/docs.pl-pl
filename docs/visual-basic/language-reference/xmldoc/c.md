---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 969df339eb766d2edb444ab5626af4e69accddba
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871696"
---
# <a name="c-visual-basic"></a><span data-ttu-id="e868a-101">\<c> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e868a-101">\<c> (Visual Basic)</span></span>

<span data-ttu-id="e868a-102">Wskazuje, że tekst w opisie ma kod.</span><span class="sxs-lookup"><span data-stu-id="e868a-102">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e868a-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="e868a-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e868a-104">Parametry</span><span class="sxs-lookup"><span data-stu-id="e868a-104">Parameters</span></span>  
  
|<span data-ttu-id="e868a-105">Parametr</span><span class="sxs-lookup"><span data-stu-id="e868a-105">Parameter</span></span>|<span data-ttu-id="e868a-106">Opis</span><span class="sxs-lookup"><span data-stu-id="e868a-106">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="e868a-107">Tekst, który ma być wskazywany jako kod.</span><span class="sxs-lookup"><span data-stu-id="e868a-107">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e868a-108">Uwagi</span><span class="sxs-lookup"><span data-stu-id="e868a-108">Remarks</span></span>  

 <span data-ttu-id="e868a-109">`<c>`Tag umożliwia wskazanie, że tekst w opisie powinien być oznaczony jako kod.</span><span class="sxs-lookup"><span data-stu-id="e868a-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="e868a-110">Użyj [\<code>](code.md) , aby wskazać wiele wierszy jako kod.</span><span class="sxs-lookup"><span data-stu-id="e868a-110">Use [\<code>](code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="e868a-111">Kompiluj z [-doc](../../reference/command-line-compiler/doc.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="e868a-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e868a-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="e868a-112">Example</span></span>  

 <span data-ttu-id="e868a-113">Ten przykład używa `<c>` znacznika w sekcji podsumowania, aby wskazać, że `Counter` jest to kod.</span><span class="sxs-lookup"><span data-stu-id="e868a-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e868a-114">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e868a-114">See also</span></span>

- [<span data-ttu-id="e868a-115">Tagi komentarza XML</span><span class="sxs-lookup"><span data-stu-id="e868a-115">XML Comment Tags</span></span>](index.md)
