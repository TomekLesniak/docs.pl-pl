---
title: Użyj elementu "FilePutObject" zamiast elementu "FilePut" w przypadku używania argumentu typu "Object"
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: c6ae755ad3eca4b1c50b83049885b6cf66f13c07
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100337"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a><span data-ttu-id="dd200-102">Użyj elementu "FilePutObject" zamiast elementu "FilePut" w przypadku używania argumentu typu "Object"</span><span class="sxs-lookup"><span data-stu-id="dd200-102">Use 'FilePutObject' instead of 'FilePut' when using argument of type 'Object'</span></span>

<span data-ttu-id="dd200-103">`FilePut`Metoda zawiera argument typu `Object` .</span><span class="sxs-lookup"><span data-stu-id="dd200-103">The `FilePut` method includes an argument of type `Object`.</span></span> <span data-ttu-id="dd200-104">`FilePutObject` należy zamiast tego użyć, `FilePut` Aby uniknąć niejasności.</span><span class="sxs-lookup"><span data-stu-id="dd200-104">`FilePutObject` should be used in place of `FilePut` to avoid ambiguities.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="dd200-105">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="dd200-105">To correct this error</span></span>  
  
- <span data-ttu-id="dd200-106">Zastąp element `FilePut` pytaniem `FilePutObject`.</span><span class="sxs-lookup"><span data-stu-id="dd200-106">Replace `FilePut` with `FilePutObject`.</span></span>  
  
- <span data-ttu-id="dd200-107">Rzutowanie `Object` argumentu na bardziej konkretny typ.</span><span class="sxs-lookup"><span data-stu-id="dd200-107">Cast the `Object` argument to a more specific type.</span></span>  
  
- <span data-ttu-id="dd200-108">Użyj funkcji dostępnych w `My.Computer.FileSystem` obiekcie.</span><span class="sxs-lookup"><span data-stu-id="dd200-108">Use the functionality available in the `My.Computer.FileSystem` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd200-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="dd200-109">See also</span></span>

- [<span data-ttu-id="dd200-110">My. Computer. FileSystem</span><span class="sxs-lookup"><span data-stu-id="dd200-110">My.Computer.FileSystem</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [<span data-ttu-id="dd200-111">My. Computer. FileSystem. WriteAllBytes</span><span class="sxs-lookup"><span data-stu-id="dd200-111">My.Computer.FileSystem.WriteAllBytes</span></span>](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
