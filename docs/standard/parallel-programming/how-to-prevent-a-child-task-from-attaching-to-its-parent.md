---
title: 'Instrukcje: Zapobieganie łączeniu zadania podrzędnego z odpowiadającym mu zadaniem nadrzędnym'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, preventing attachments
ms.assetid: c0fb85d4-9e80-4905-9f65-29acc54201c4
ms.openlocfilehash: afc8c99fe478337c8dc353d46a4e2ff5be531ae8
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826895"
---
# <a name="how-to-prevent-a-child-task-from-attaching-to-its-parent"></a>Instrukcje: Zapobieganie łączeniu zadania podrzędnego z odpowiadającym mu zadaniem nadrzędnym
W tym dokumencie przedstawiono sposób zapobiegania dołączeniu zadania podrzędnego do zadania nadrzędnego. Zapobieganie dołączeniu zadania podrzędnego do jego obiektu nadrzędnego jest przydatne w przypadku wywołania składnika, który jest zapisany przez inną firmę, który również korzysta z zadań. Na przykład składnik innej firmy, który używa <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent?displayProperty=nameWithType> opcji tworzenia <xref:System.Threading.Tasks.Task> <xref:System.Threading.Tasks.Task%601> obiektu lub może spowodować problemy w kodzie, jeśli jest długotrwały lub zgłasza nieobsługiwany wyjątek.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład porównuje efekty używania opcji domyślnych z efektami zapobiegania dołączeniu zadania podrzędnego do elementu nadrzędnego. Przykład tworzy <xref:System.Threading.Tasks.Task> obiekt, który wywołuje do biblioteki innej firmy, która również używa <xref:System.Threading.Tasks.Task> obiektu. Biblioteka innych firm używa <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> opcji, aby utworzyć <xref:System.Threading.Tasks.Task> obiekt. Aplikacja używa opcji, <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> Aby utworzyć zadanie nadrzędne. Ta opcja powoduje, że środowisko uruchomieniowe usuwa <xref:System.Threading.Tasks.TaskCreationOptions.AttachedToParent> specyfikację w zadaniach podrzędnych.  
  
 [!code-csharp[TPL_DenyChildAttach#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_denychildattach/cs/denychildattach.cs#1)]
 [!code-vb[TPL_DenyChildAttach#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_denychildattach/vb/denychildattach.vb#1)]  
  
 Ponieważ zadanie nadrzędne nie kończy się do momentu zakończenia wszystkich zadań podrzędnych, długotrwałe zadanie podrzędne może spowodować niewłaściwe działanie ogólnej aplikacji. W tym przykładzie, gdy aplikacja używa domyślnych opcji do utworzenia zadania nadrzędnego, zadanie podrzędne musi zakończyć się przed ukończeniem zadania nadrzędnego. Gdy aplikacja używa <xref:System.Threading.Tasks.TaskCreationOptions.DenyChildAttach?displayProperty=nameWithType> opcji, element podrzędny nie jest dołączony do elementu nadrzędnego. W związku z tym aplikacja może wykonać dodatkową pracę po zakończeniu zadania nadrzędnego i zanim będzie musiało oczekiwać na zakończenie zadania podrzędnego.  
  
## <a name="see-also"></a>Zobacz także

- [Programowanie asynchroniczne oparte na zadaniach](task-based-asynchronous-programming.md)
