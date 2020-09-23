---
title: Argument nie może mieć wartości Nothing
ms.date: 07/20/2015
f1_keywords:
- vbrGeneral_ArgumentNullException
ms.assetid: 2abd995b-36a5-45f0-b3c1-6e0c3b31a875
ms.openlocfilehash: 27c959b0fd62a930750bc731e6ca242b2415f1e3
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91087235"
---
# <a name="argument-cannot-be-nothing"></a><span data-ttu-id="683d7-102">Argument nie może mieć wartości Nothing</span><span class="sxs-lookup"><span data-stu-id="683d7-102">Argument cannot be Nothing</span></span>

<span data-ttu-id="683d7-103">Podano wartość null dla argumentu, który musi mieć wartość.</span><span class="sxs-lookup"><span data-stu-id="683d7-103">A null value has been supplied for an argument that must have a value.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="683d7-104">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="683d7-104">To correct this error</span></span>  
  
- <span data-ttu-id="683d7-105">Być może podjęto próbę użycia obiektu bez podawania wystąpienia obiektu.</span><span class="sxs-lookup"><span data-stu-id="683d7-105">You might have tried to use an object without providing an instance of the object.</span></span> <span data-ttu-id="683d7-106">W takim przypadku należy użyć `New` słowa kluczowego, aby utworzyć wystąpienie.</span><span class="sxs-lookup"><span data-stu-id="683d7-106">In such a case, use the `New` keyword to create the instance.</span></span>  
  
- <span data-ttu-id="683d7-107">Sprawdź, czy wartość jest obliczana prawidłowo.</span><span class="sxs-lookup"><span data-stu-id="683d7-107">Check that the value is calculated correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="683d7-108">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="683d7-108">See also</span></span>

- <xref:System.NullReferenceException>
