---
title: Zastępowanie obiektu głównego
ms.date: 07/15/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- principal objects, replacing
- security [.NET], replacing principal objects
- security [.NET], principals
ms.assetid: c323687e-b196-487b-beba-f38f9b3f961b
ms.openlocfilehash: b8f7a8fbd3b9c65126d6a3a65a5f6722f2ad93de
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824177"
---
# <a name="replacing-a-principal-object"></a>Zastępowanie obiektu głównego

Aplikacje, które zapewniają usługi uwierzytelniania, muszą być w stanie zastąpić obiekt **podmiotu zabezpieczeń** ( <xref:System.Security.Principal.IPrincipal> ) dla danego wątku. Ponadto system zabezpieczeń musi pomagać w ochronie możliwości zastąpienia obiektów **głównych** , ponieważ złośliwie podłączona, nieprawidłowa **podmiot** zabezpieczeń narusza zabezpieczenia aplikacji przez zajęcie nieprawdziwej tożsamością lub rolą. W związku z tym aplikacje, które wymagają możliwości zastąpienia obiektów **Principal** , muszą mieć przyznany <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType> obiekt dla kontroli podmiotu zabezpieczeń. (Należy zauważyć, że to uprawnienie nie jest wymagane do wykonywania kontroli zabezpieczeń opartych na rolach ani do tworzenia obiektów **głównych** ).  
  
Bieżący obiekt **Principal** można zastąpić, wykonując następujące zadania:  
  
1. Utwórz zastępujący obiekt **podmiotu zabezpieczeń** i skojarzony obiekt **tożsamości** .  
  
2. Dołącz nowy obiekt **Principal** do kontekstu wywołania.  
  
## <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak utworzyć ogólny obiekt główny i używać go do ustawiania podmiotu zabezpieczeń wątku.  
  
[!code-csharp[SetCurrentPrincipal#1](../../../samples/snippets/csharp/VS_Snippets_CLR/SetCurrentPrincipal/CS/program.cs#1)]
[!code-vb[SetCurrentPrincipal#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/SetCurrentPrincipal/VB/program.vb#1)]  
  
## <a name="see-also"></a>Zobacz także

- <xref:System.Security.Permissions.SecurityPermission?displayProperty=nameWithType>
- [Obiekty główne i obiekty tożsamości](principal-and-identity-objects.md)
- [Zabezpieczenia ASP.NET Core](/aspnet/core/security/)
