---
title: Ostrzeżenie SYSLIB0006
description: Dowiedz się więcej o Obsoletions, które generują ostrzeżenie SYSLIB0006 w czasie kompilacji.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 45d2d8ec6ad99996f8b8f46d0c2e0ac2e02cf450
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333359"
---
# <a name="syslib0006-threadabort-is-not-supported"></a><span data-ttu-id="f3902-103">SYSLIB0006: Thread. Abort nie jest obsługiwana</span><span class="sxs-lookup"><span data-stu-id="f3902-103">SYSLIB0006: Thread.Abort is not supported</span></span>

<span data-ttu-id="f3902-104">Następujące interfejsy API są oznaczone jako przestarzałe, począwszy od platformy .NET 5,0.</span><span class="sxs-lookup"><span data-stu-id="f3902-104">The following APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="f3902-105">Użycie tych interfejsów API generuje ostrzeżenie `SYSLIB0006` w czasie kompilacji.</span><span class="sxs-lookup"><span data-stu-id="f3902-105">Use of these APIs generates warning `SYSLIB0006` at compile time.</span></span>

- <xref:System.Threading.Thread.Abort?displayProperty=nameWithType>
- <xref:System.Threading.Thread.Abort(System.Object)?displayProperty=nameWithType>

## <a name="workaround"></a><span data-ttu-id="f3902-106">Obejście</span><span class="sxs-lookup"><span data-stu-id="f3902-106">Workaround</span></span>

<span data-ttu-id="f3902-107">Użyj, <xref:System.Threading.CancellationToken> Aby przerwać przetwarzanie jednostki pracy zamiast wywoływania <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="f3902-107">Use a <xref:System.Threading.CancellationToken> to abort processing of a unit of work instead of calling <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f3902-108">Poniższy przykład ilustruje użycie <xref:System.Threading.CancellationToken> .</span><span class="sxs-lookup"><span data-stu-id="f3902-108">The following example illustrates the use of <xref:System.Threading.CancellationToken>.</span></span>

```csharp
void ProcessPendingWorkItemsNew(CancellationToken cancellationToken)
{
    if (QueryIsMoreWorkPending())
    {
        // If the CancellationToken is marked as "needs to cancel",
        // this will throw the appropriate exception.
        cancellationToken.ThrowIfCancellationRequested();

        WorkItem work = DequeueWorkItem();
        ProcessWorkItem(work);
    }
}
```

## <a name="see-also"></a><span data-ttu-id="f3902-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="f3902-109">See also</span></span>

- [<span data-ttu-id="f3902-110">Wątek. Abort jest przestarzały — zmiana zostanie przerwana</span><span class="sxs-lookup"><span data-stu-id="f3902-110">Thread.Abort is obsolete - breaking change</span></span>](3.1-5.0.md#threadabort-is-obsolete)
- [<span data-ttu-id="f3902-111">Anulowanie w zarządzanych wątkach</span><span class="sxs-lookup"><span data-stu-id="f3902-111">Cancellation in managed threads</span></span>](../../standard/threading/cancellation-in-managed-threads.md)
