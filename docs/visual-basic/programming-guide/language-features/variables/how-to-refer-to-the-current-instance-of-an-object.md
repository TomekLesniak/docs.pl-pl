---
title: 'Porady: odwoływanie się do bieżącego wystąpienia obiektu'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 64d21fe4aaf6fd34bf880373a7ab3067fb67820e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077062"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="3a397-102">Porady: odwoływanie się do bieżącego wystąpienia obiektu (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a397-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>

<span data-ttu-id="3a397-103">*Bieżące wystąpienie* obiektu to wystąpienie, w którym kod jest aktualnie wykonywany.</span><span class="sxs-lookup"><span data-stu-id="3a397-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="3a397-104">Użyj `Me` słowa kluczowego, aby odwołać się do bieżącego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="3a397-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="3a397-105">Aby odwołać się do bieżącego wystąpienia</span><span class="sxs-lookup"><span data-stu-id="3a397-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="3a397-106">Użyj `Me` słowa kluczowego, gdzie normalnie używać nazwy zmiennej obiektu.</span><span class="sxs-lookup"><span data-stu-id="3a397-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="3a397-107">Chociaż `Me` zachowuje się jak zmienna obiektu, nie można jej zadeklarować ani przypisać do niej niczego.</span><span class="sxs-lookup"><span data-stu-id="3a397-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="3a397-108">`Me` zawsze odwołuje się do bieżącego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="3a397-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a397-109">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="3a397-109">See also</span></span>

- [<span data-ttu-id="3a397-110">Zmienne obiektów</span><span class="sxs-lookup"><span data-stu-id="3a397-110">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="3a397-111">Przypisanie zmiennej obiektu</span><span class="sxs-lookup"><span data-stu-id="3a397-111">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="3a397-112">Me, My, MyBase i MyClass</span><span class="sxs-lookup"><span data-stu-id="3a397-112">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
