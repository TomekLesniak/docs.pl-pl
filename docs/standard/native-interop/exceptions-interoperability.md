---
title: Współdziałanie wyjątków
ms.date: 01/16/2020
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- interop, exceptions
- exceptions, interop
ms.openlocfilehash: db7c9943c298607aa91a4bd08ddc12bbafc872be
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830626"
---
# <a name="working-with-interop-exceptions-in-unmanaged-code"></a><span data-ttu-id="53101-102">Praca z wyjątkami międzyoperacyjnymi w kodzie niezarządzanym</span><span class="sxs-lookup"><span data-stu-id="53101-102">Working with Interop Exceptions in Unmanaged Code</span></span>

<span data-ttu-id="53101-103">Międzyoperacyjność wyjątku kodu niezarządzanego jest obsługiwana tylko na platformach systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="53101-103">Unmanaged code exception interop is supported on Windows platforms only.</span></span> <span data-ttu-id="53101-104">Problemy z przenośnością powstają na platformach innych niż Windows.</span><span class="sxs-lookup"><span data-stu-id="53101-104">Portability issues arise on non-Windows platforms.</span></span> <span data-ttu-id="53101-105">Ponieważ ABI systemu UNIX nie ma definicji obsługi wyjątków, kod zarządzany nie może wiedzieć, jak mechanizmy wyjątków działają w ramach okładek.</span><span class="sxs-lookup"><span data-stu-id="53101-105">Since the Unix ABI has no definition for exception handling, managed code can't know how exception mechanisms work under the covers.</span></span> <span data-ttu-id="53101-106">W związku z tym wyjątki mogą kończyć się wynikiem nieprzewidywalnych zachowań i awarii.</span><span class="sxs-lookup"><span data-stu-id="53101-106">Therefore, exceptions can end up resulting in unpredictable behaviors and crashes.</span></span>

## <a name="setjmplongjmp-behaviors"></a><span data-ttu-id="53101-107">Zachowania setjmp/longjmp</span><span class="sxs-lookup"><span data-stu-id="53101-107">Setjmp/Longjmp Behaviors</span></span>

<span data-ttu-id="53101-108">Funkcje Interop with `setjmp` i języka `longjmp` C nie są obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="53101-108">Interop with `setjmp` and `longjmp` C functions is not supported.</span></span> <span data-ttu-id="53101-109">Nie można użyć, `longjmp` Aby pominąć ramki zarządzane.</span><span class="sxs-lookup"><span data-stu-id="53101-109">You can't use `longjmp` to skip over managed frames.</span></span>

<span data-ttu-id="53101-110">Aby uzyskać więcej informacji, zobacz [dokumentację longjmp](/cpp/c-runtime-library/reference/longjmp).</span><span class="sxs-lookup"><span data-stu-id="53101-110">For more information, see [longjmp documentation](/cpp/c-runtime-library/reference/longjmp).</span></span>

## <a name="see-also"></a><span data-ttu-id="53101-111">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="53101-111">See also</span></span>

- [<span data-ttu-id="53101-112">Wyjątki</span><span class="sxs-lookup"><span data-stu-id="53101-112">Exceptions</span></span>](index.md)
- [<span data-ttu-id="53101-113">Współdziałanie z natywnymi bibliotekami</span><span class="sxs-lookup"><span data-stu-id="53101-113">Interop with Native Libraries</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/#runtime-exception-propagation)
