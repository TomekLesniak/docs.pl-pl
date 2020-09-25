---
title: Jak łączyć delegatów (delegatów multiemisji) — Przewodnik programowania w języku C#
description: Dowiedz się, jak połączyć delegatów, aby utworzyć delegatów multiemisji. Zobacz przykładowy kod i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- delegates [C#], combining
- multicast delegates [C#]
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
ms.openlocfilehash: 3e86c8ed4b7b091ee8c75930d427c22aa5bc0c52
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185954"
---
# <a name="how-to-combine-delegates-multicast-delegates-c-programming-guide"></a><span data-ttu-id="2fb52-104">Łączenie obiektów delegowanych (obiekty delegowane multiemisji) (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="2fb52-104">How to combine delegates (Multicast Delegates) (C# Programming Guide)</span></span>

<span data-ttu-id="2fb52-105">W tym przykładzie pokazano, jak utworzyć delegatów multiemisji.</span><span class="sxs-lookup"><span data-stu-id="2fb52-105">This example demonstrates how to create multicast delegates.</span></span> <span data-ttu-id="2fb52-106">Przydatna właściwość obiektów [delegatów](../../language-reference/builtin-types/reference-types.md) polega na tym, że wiele obiektów może być przypisanych do jednego wystąpienia delegata przy użyciu `+` operatora.</span><span class="sxs-lookup"><span data-stu-id="2fb52-106">A useful property of [delegate](../../language-reference/builtin-types/reference-types.md) objects is that multiple objects can be assigned to one delegate instance by using the `+` operator.</span></span> <span data-ttu-id="2fb52-107">Delegat multiemisji zawiera listę przypisanych delegatów.</span><span class="sxs-lookup"><span data-stu-id="2fb52-107">The multicast delegate contains a list of the assigned delegates.</span></span> <span data-ttu-id="2fb52-108">Gdy obiekt delegowany multiemisji jest wywoływany, wywołuje delegatów z listy w kolejności.</span><span class="sxs-lookup"><span data-stu-id="2fb52-108">When the multicast delegate is called, it invokes the delegates in the list, in order.</span></span> <span data-ttu-id="2fb52-109">Łączyć można tylko Delegaty tego samego typu.</span><span class="sxs-lookup"><span data-stu-id="2fb52-109">Only delegates of the same type can be combined.</span></span>  
  
 <span data-ttu-id="2fb52-110">`-`Operatora można użyć do usunięcia delegata składnika z delegata multiemisji.</span><span class="sxs-lookup"><span data-stu-id="2fb52-110">The `-` operator can be used to remove a component delegate from a multicast delegate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fb52-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="2fb52-111">Example</span></span>  

 [!code-csharp[csProgGuideDelegates#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDelegates/CS/Delegates.cs#11)]  
  
## <a name="see-also"></a><span data-ttu-id="2fb52-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="2fb52-112">See also</span></span>

- <xref:System.MulticastDelegate>
- [<span data-ttu-id="2fb52-113">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="2fb52-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2fb52-114">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="2fb52-114">Events</span></span>](../events/index.md)
