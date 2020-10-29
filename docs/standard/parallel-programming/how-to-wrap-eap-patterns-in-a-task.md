---
title: 'Instrukcje: Opakowywanie wzorców EAP w zadaniu'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
ms.openlocfilehash: 339544ce9f0ee44097d1a60e0d2c2035d81f674d
ms.sourcegitcommit: 6d09ae36acba0b0e2ba47999f8f1a725795462a2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92925366"
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a><span data-ttu-id="ce1e7-102">Instrukcje: Opakowywanie wzorców EAP w zadaniu</span><span class="sxs-lookup"><span data-stu-id="ce1e7-102">How to: Wrap EAP Patterns in a Task</span></span>
<span data-ttu-id="ce1e7-103">Poniższy przykład pokazuje, jak uwidocznić dowolną sekwencję operacji Event-Based asynchronicznego wzorca (EAP) jako jedno zadanie przy użyciu <xref:System.Threading.Tasks.TaskCompletionSource%601> .</span><span class="sxs-lookup"><span data-stu-id="ce1e7-103">The following example shows how to expose an arbitrary sequence of Event-Based Asynchronous Pattern (EAP) operations as one task by using a <xref:System.Threading.Tasks.TaskCompletionSource%601>.</span></span> <span data-ttu-id="ce1e7-104">W przykładzie pokazano również, jak użyć elementu <xref:System.Threading.CancellationToken> do wywołania wbudowanych metod anulowania dla <xref:System.Net.WebClient> obiektów.</span><span class="sxs-lookup"><span data-stu-id="ce1e7-104">The example also shows how to use a <xref:System.Threading.CancellationToken> to invoke the built-in cancellation methods on the <xref:System.Net.WebClient> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce1e7-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="ce1e7-105">Example</span></span>  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a><span data-ttu-id="ce1e7-106">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="ce1e7-106">See also</span></span>

- [<span data-ttu-id="ce1e7-107">TPL i tradycyjne programowanie asynchroniczne platformy .NET</span><span class="sxs-lookup"><span data-stu-id="ce1e7-107">TPL and Traditional .NET Asynchronous Programming</span></span>](tpl-and-traditional-async-programming.md)
