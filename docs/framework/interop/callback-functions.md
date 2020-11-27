---
title: Funkcje wywołania zwrotnego
description: Przeczytaj o funkcjach wywołania zwrotnego, które są kodem z zarządzaną aplikacją, która ułatwia wykonywanie zadania w niezarządzanej bibliotece DLL.
ms.date: 03/30/2017
helpviewer_keywords:
- callback function
- platform invoke, calling unmanaged functions
ms.assetid: c0aa8533-3b3b-42e8-9f60-84919793098c
ms.openlocfilehash: 659f384f7bfc3a2326a40a9536c977d7c41ab076
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96283162"
---
# <a name="callback-functions"></a><span data-ttu-id="0fefc-103">Funkcje wywołania zwrotnego</span><span class="sxs-lookup"><span data-stu-id="0fefc-103">Callback Functions</span></span>

<span data-ttu-id="0fefc-104">Funkcja wywołania zwrotnego jest kodem w aplikacji zarządzanej, która ułatwia wykonywanie zadania przez niezarządzaną funkcję DLL.</span><span class="sxs-lookup"><span data-stu-id="0fefc-104">A callback function is code within a managed application that helps an unmanaged DLL function complete a task.</span></span> <span data-ttu-id="0fefc-105">Wywołania funkcji wywołania zwrotnego są przekazywane pośrednio z aplikacji zarządzanej za pośrednictwem funkcji DLL i z powrotem do zarządzanej implementacji.</span><span class="sxs-lookup"><span data-stu-id="0fefc-105">Calls to a callback function pass indirectly from a managed application, through a DLL function, and back to the managed implementation.</span></span> <span data-ttu-id="0fefc-106">Niektóre z wielu funkcji DLL wywoływanych za pomocą wywołania platformy wymagają poprawnego działania funkcji wywołania zwrotnego w kodzie zarządzanym.</span><span class="sxs-lookup"><span data-stu-id="0fefc-106">Some of the many DLL functions called with platform invoke require a callback function in managed code to run properly.</span></span>  
  
 <span data-ttu-id="0fefc-107">Aby wywołać większość funkcji DLL z kodu zarządzanego, należy utworzyć zarządzaną definicję funkcji, a następnie wywołać ją.</span><span class="sxs-lookup"><span data-stu-id="0fefc-107">To call most DLL functions from managed code, you create a managed definition of the function and then call it.</span></span> <span data-ttu-id="0fefc-108">Proces jest prosty.</span><span class="sxs-lookup"><span data-stu-id="0fefc-108">The process is straightforward.</span></span>  
  
 <span data-ttu-id="0fefc-109">Użycie funkcji DLL, która wymaga funkcji wywołania zwrotnego, zawiera kilka dodatkowych kroków.</span><span class="sxs-lookup"><span data-stu-id="0fefc-109">Using a DLL function that requires a callback function has some additional steps.</span></span> <span data-ttu-id="0fefc-110">Najpierw należy określić, czy funkcja wymaga wywołania zwrotnego, przeglądając dokumentację funkcji.</span><span class="sxs-lookup"><span data-stu-id="0fefc-110">First, you must determine whether the function requires a callback by looking at the documentation for the function.</span></span> <span data-ttu-id="0fefc-111">Następnie musisz utworzyć funkcję wywołania zwrotnego w aplikacji zarządzanej.</span><span class="sxs-lookup"><span data-stu-id="0fefc-111">Next, you have to create the callback function in your managed application.</span></span> <span data-ttu-id="0fefc-112">Na koniec należy wywołać funkcję DLL, przekazując wskaźnik do funkcji wywołania zwrotnego jako argument.</span><span class="sxs-lookup"><span data-stu-id="0fefc-112">Finally, you call the DLL function, passing a pointer to the callback function as an argument.</span></span>

 <span data-ttu-id="0fefc-113">Poniższa ilustracja zawiera podsumowanie funkcji wywołania zwrotnego i kroków implementacji:</span><span class="sxs-lookup"><span data-stu-id="0fefc-113">The following illustration summarizes the callback function and implementation steps:</span></span>  
  
 ![Diagram przedstawiający proces wywołania zwrotnego platformy.](./media/callback-functions/platform-invoke-callback-process.gif)  
  
 <span data-ttu-id="0fefc-115">Funkcje wywołania zwrotnego są idealne do użycia w sytuacjach, w których zadanie jest wykonywane wielokrotnie.</span><span class="sxs-lookup"><span data-stu-id="0fefc-115">Callback functions are ideal for use in situations in which a task is performed repeatedly.</span></span> <span data-ttu-id="0fefc-116">Innym typowym użyciem jest z funkcjami wyliczania, takimi jak **EnumFontFamilies**, **EnumPrinters** i **EnumWindows** w interfejsie API systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="0fefc-116">Another common usage is with enumeration functions, such as **EnumFontFamilies**, **EnumPrinters**, and **EnumWindows** in the Windows API.</span></span> <span data-ttu-id="0fefc-117">Funkcja **EnumWindows** wylicza wszystkie istniejące okna na komputerze, wywołując funkcję wywołania zwrotnego do wykonania zadania w poszczególnych oknach.</span><span class="sxs-lookup"><span data-stu-id="0fefc-117">The **EnumWindows** function enumerates through all existing windows on your computer, calling the callback function to perform a task on each window.</span></span> <span data-ttu-id="0fefc-118">Aby uzyskać instrukcje i przykład, zobacz [How to: Implementuj funkcje wywołania zwrotnego](how-to-implement-callback-functions.md).</span><span class="sxs-lookup"><span data-stu-id="0fefc-118">For instructions and an example, see [How to: Implement Callback Functions](how-to-implement-callback-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fefc-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="0fefc-119">See also</span></span>

- [<span data-ttu-id="0fefc-120">Instrukcje: Implementowanie funkcji wywołania zwrotnego</span><span class="sxs-lookup"><span data-stu-id="0fefc-120">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)
- [<span data-ttu-id="0fefc-121">Wywołanie funkcji DLL</span><span class="sxs-lookup"><span data-stu-id="0fefc-121">Calling a DLL Function</span></span>](calling-a-dll-function.md)
