---
title: Procedura Let właściwości nie została zdefiniowana, a procedura Get właściwości nie zwraca obiektu
ms.date: 07/20/2015
f1_keywords:
- vbrID451
ms.assetid: 8542382a-689f-4e1b-abc0-c1e2dadb92f4
ms.openlocfilehash: fbeaa224ea9e095f86c37e571492d83bc98b4397
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871092"
---
# <a name="property-let-procedure-not-defined-and-property-get-procedure-did-not-return-an-object"></a><span data-ttu-id="325fb-102">Procedura Let właściwości nie została zdefiniowana, a procedura Get właściwości nie zwraca obiektu</span><span class="sxs-lookup"><span data-stu-id="325fb-102">Property let procedure not defined and property get procedure did not return an object</span></span>

<span data-ttu-id="325fb-103">Niektóre właściwości, metody i operacje mogą dotyczyć tylko `Collection` obiektów.</span><span class="sxs-lookup"><span data-stu-id="325fb-103">Certain properties, methods, and operations can only apply to `Collection` objects.</span></span> <span data-ttu-id="325fb-104">Określono operację lub właściwość, która jest wyłączna dla kolekcji, ale obiekt nie jest kolekcją.</span><span class="sxs-lookup"><span data-stu-id="325fb-104">You specified an operation or property that is exclusive to collections, but the object is not a collection.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="325fb-105">Aby poprawić ten błąd</span><span class="sxs-lookup"><span data-stu-id="325fb-105">To correct this error</span></span>  
  
1. <span data-ttu-id="325fb-106">Sprawdź pisownię nazwy obiektu lub właściwości albo sprawdź, czy obiekt jest `Collection` obiektem.</span><span class="sxs-lookup"><span data-stu-id="325fb-106">Check the spelling of the object or property name, or verify that the object is a `Collection` object.</span></span>  
  
2. <span data-ttu-id="325fb-107">Przyjrzyj się `Add` metodzie użytej do dodania obiektu do kolekcji, aby upewnić się, że składnia jest poprawna i że wszystkie identyfikatory zostały wpisane prawidłowo.</span><span class="sxs-lookup"><span data-stu-id="325fb-107">Look at the `Add` method used to add the object to the collection to be sure the syntax is correct and that any identifiers were spelled correctly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="325fb-108">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="325fb-108">See also</span></span>

- <xref:Microsoft.VisualBasic.Collection>
