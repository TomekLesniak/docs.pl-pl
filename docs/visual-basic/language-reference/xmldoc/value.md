---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 550f8b63928f80878ba316bfaf09077e14091305
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875178"
---
# <a name="value-visual-basic"></a><span data-ttu-id="898f8-101">\<value> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="898f8-101">\<value> (Visual Basic)</span></span>

<span data-ttu-id="898f8-102">Określa opis właściwości.</span><span class="sxs-lookup"><span data-stu-id="898f8-102">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="898f8-103">Składnia</span><span class="sxs-lookup"><span data-stu-id="898f8-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="898f8-104">Parametry</span><span class="sxs-lookup"><span data-stu-id="898f8-104">Parameters</span></span>  

 `property-description`  
 <span data-ttu-id="898f8-105">Opis właściwości.</span><span class="sxs-lookup"><span data-stu-id="898f8-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="898f8-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="898f8-106">Remarks</span></span>  

 <span data-ttu-id="898f8-107">Użyj `<value>` znacznika, aby opisać właściwość.</span><span class="sxs-lookup"><span data-stu-id="898f8-107">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="898f8-108">Należy pamiętać, że po dodaniu właściwości przy użyciu kreatora kodu w środowisku deweloperskim programu Visual Studio zostanie dodany [\<summary>](summary.md) tag nowej właściwości.</span><span class="sxs-lookup"><span data-stu-id="898f8-108">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](summary.md) tag for the new property.</span></span> <span data-ttu-id="898f8-109">Następnie należy ręcznie dodać tag, `<value>` aby opisać wartość, którą reprezentuje właściwość.</span><span class="sxs-lookup"><span data-stu-id="898f8-109">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="898f8-110">Kompiluj z [-doc](../../reference/command-line-compiler/doc.md) , aby przetwarzać komentarze dokumentacji do pliku.</span><span class="sxs-lookup"><span data-stu-id="898f8-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="898f8-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="898f8-111">Example</span></span>  

 <span data-ttu-id="898f8-112">W tym przykładzie używa `<value>` znacznika do opisania wartości, jaką `Counter` zawiera właściwość.</span><span class="sxs-lookup"><span data-stu-id="898f8-112">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="898f8-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="898f8-113">See also</span></span>

- [<span data-ttu-id="898f8-114">Tagi komentarza XML</span><span class="sxs-lookup"><span data-stu-id="898f8-114">XML Comment Tags</span></span>](index.md)
