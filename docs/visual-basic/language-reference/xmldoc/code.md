---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d058663213cf02f2142bff740aeec1b60791362c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873026"
---
# <a name="code-visual-basic"></a><span data-ttu-id="92afc-101">\<code> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="92afc-101">\<code> (Visual Basic)</span></span>

<span data-ttu-id="92afc-102">Wskazuje, że tekst jest wieloma wierszami kodu.</span><span class="sxs-lookup"><span data-stu-id="92afc-102">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92afc-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="92afc-103">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="92afc-104">Parametry</span><span class="sxs-lookup"><span data-stu-id="92afc-104">Parameters</span></span>  

 `content`  
 <span data-ttu-id="92afc-105">Tekst, który ma zostać oznaczony jako kod.</span><span class="sxs-lookup"><span data-stu-id="92afc-105">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92afc-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="92afc-106">Remarks</span></span>  

 <span data-ttu-id="92afc-107">Użyj `<code>` znacznika, aby wskazać wiele wierszy jako kod.</span><span class="sxs-lookup"><span data-stu-id="92afc-107">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="92afc-108">Użyj, [\<c>](c.md) Aby wskazać, że tekst w opisie powinien być oznaczony jako kod.</span><span class="sxs-lookup"><span data-stu-id="92afc-108">Use [\<c>](c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="92afc-109">Kompiluj z [-doc](../../reference/command-line-compiler/doc.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="92afc-109">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92afc-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="92afc-110">Example</span></span>  

 <span data-ttu-id="92afc-111">W tym przykładzie użyto \<code> znacznika, aby dołączyć przykładowy kod do użycia `ID` pola.</span><span class="sxs-lookup"><span data-stu-id="92afc-111">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="92afc-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="92afc-112">See also</span></span>

- [<span data-ttu-id="92afc-113">Tagi komentarza XML</span><span class="sxs-lookup"><span data-stu-id="92afc-113">XML Comment Tags</span></span>](index.md)
