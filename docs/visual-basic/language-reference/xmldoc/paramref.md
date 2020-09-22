---
title: <paramref>
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: d7aacc5faea22f9c5a4b865a32c832154fe624c5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872614"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="12933-101">\<paramref> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="12933-101">\<paramref> (Visual Basic)</span></span>

<span data-ttu-id="12933-102">Formatuje słowo jako parametr.</span><span class="sxs-lookup"><span data-stu-id="12933-102">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12933-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="12933-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="12933-104">Parametry</span><span class="sxs-lookup"><span data-stu-id="12933-104">Parameters</span></span>  

 `name`  
 <span data-ttu-id="12933-105">Nazwa parametru, do którego się odwołuje.</span><span class="sxs-lookup"><span data-stu-id="12933-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="12933-106">Ujmij nazwę w znaki podwójnego cudzysłowu ("").</span><span class="sxs-lookup"><span data-stu-id="12933-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12933-107">Uwagi</span><span class="sxs-lookup"><span data-stu-id="12933-107">Remarks</span></span>  

 <span data-ttu-id="12933-108">`<paramref>`Tag umożliwia wskazanie, że słowo jest parametrem.</span><span class="sxs-lookup"><span data-stu-id="12933-108">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="12933-109">Plik XML można przetworzyć, aby sformatować ten parametr w dowolny sposób.</span><span class="sxs-lookup"><span data-stu-id="12933-109">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="12933-110">Kompiluj z [-doc](../../reference/command-line-compiler/doc.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="12933-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="12933-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="12933-111">Example</span></span>  

 <span data-ttu-id="12933-112">W tym przykładzie używa `<paramref>` znacznika do odwoływania się do `id` parametru.</span><span class="sxs-lookup"><span data-stu-id="12933-112">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="12933-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="12933-113">See also</span></span>

- [<span data-ttu-id="12933-114">Tagi komentarza XML</span><span class="sxs-lookup"><span data-stu-id="12933-114">XML Comment Tags</span></span>](index.md)
