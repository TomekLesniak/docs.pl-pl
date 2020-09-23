---
title: Użyj elementu "FileGetObject" zamiast elementu "FileGet" w przypadku używania argumentu typu "Object"
ms.date: 07/20/2015
ms.assetid: 090b8088-895a-482a-9362-606596bac304
ms.openlocfilehash: 318a0772a99aa86d9a4633e6021f77616a43fc7e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91059408"
---
# <a name="use-filegetobject-instead-of-fileget-when-using-argument-of-type-object"></a><span data-ttu-id="94af7-102">Użyj elementu "FileGetObject" zamiast elementu "FileGet" w przypadku używania argumentu typu "Object"</span><span class="sxs-lookup"><span data-stu-id="94af7-102">Use 'FileGetObject' instead of 'FileGet' when using argument of type 'Object'</span></span>

<span data-ttu-id="94af7-103">`FileGet`Metoda zawiera argument typu `Object` .</span><span class="sxs-lookup"><span data-stu-id="94af7-103">The `FileGet` method includes an argument of type `Object`.</span></span> <span data-ttu-id="94af7-104">`FileGetObject` należy zamiast tego użyć, `FileGet` Aby uniknąć niejasności.</span><span class="sxs-lookup"><span data-stu-id="94af7-104">`FileGetObject` should be used in place of `FileGet` to avoid ambiguities.</span></span>  
  
 <span data-ttu-id="94af7-105">Zwróć uwagę, że funkcje oferowane przez program `My.Computer.Filesystem` oferują większą łatwość użytkowania i wydajności niż `FileGet` lub `FileGetObject` .</span><span class="sxs-lookup"><span data-stu-id="94af7-105">Notice that the functionality offered by `My.Computer.Filesystem` offers greater ease of use and performance than either `FileGet` or `FileGetObject`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="94af7-106">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="94af7-106">To correct this error</span></span>  
  
1. <span data-ttu-id="94af7-107">Zastąp element `FileGet` pytaniem `FileGetObject`.</span><span class="sxs-lookup"><span data-stu-id="94af7-107">Replace `FileGet` with `FileGetObject`.</span></span>  
  
2. <span data-ttu-id="94af7-108">Rzutowanie `Object` argumentu na bardziej konkretny typ.</span><span class="sxs-lookup"><span data-stu-id="94af7-108">Cast the `Object` argument to a more specific type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94af7-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="94af7-109">See also</span></span>

- [<span data-ttu-id="94af7-110">My. Computer. FileSystem</span><span class="sxs-lookup"><span data-stu-id="94af7-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
