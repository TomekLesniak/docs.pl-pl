---
title: 'Instrukcje: Opakowywanie wzorców EAP w zadaniu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to wrap EAP patterns
ms.assetid: f11ed467-af2f-4504-8a2e-299a6c36d44e
ms.openlocfilehash: 2d6788634fe03bed7a380184c0e954954e224aec
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826687"
---
# <a name="how-to-wrap-eap-patterns-in-a-task"></a>Instrukcje: Opakowywanie wzorców EAP w zadaniu
Poniższy przykład pokazuje, jak uwidocznić dowolną sekwencję operacji Event-Based asynchronicznego wzorca (EAP) jako jedno zadanie przy użyciu <xref:System.Threading.Tasks.TaskCompletionSource%601> . W przykładzie pokazano również, jak użyć elementu <xref:System.Threading.CancellationToken> do wywołania wbudowanych metod anulowania dla <xref:System.Net.WebClient> obiektów.  
  
## <a name="example"></a>Przykład  
 [!code-csharp[FromAsync#08](../../../samples/snippets/csharp/VS_Snippets_Misc/fromasync/cs/fromasync.cs#08)]
 [!code-vb[FromAsync#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/fromasync/vb/module1.vb#08)]  
  
## <a name="see-also"></a>Zobacz także

- [Model TPL i tradycyjne programowanie asynchroniczne na platformie .NET](tpl-and-traditional-async-programming.md)
