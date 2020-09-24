---
title: Jak jawnie zaimplementować członków interfejsu — Przewodnik programowania w języku C#
description: Dowiedz się, jak jawnie zaimplementować elementy członkowskie interfejsu w tym przykładzie w języku C#. Dostęp do członków uzyskuje się za pomocą wystąpienia interfejsu.
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], explicitly implementing
ms.assetid: 514cde76-f981-474e-8b40-9493619f899c
ms.openlocfilehash: a9c019cdcf6e229199d980a2d1913df7c72a2169
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157398"
---
# <a name="how-to-explicitly-implement-interface-members-c-programming-guide"></a><span data-ttu-id="69e28-104">Jak jawnie zaimplementować członków interfejsu (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="69e28-104">How to explicitly implement interface members (C# Programming Guide)</span></span>

<span data-ttu-id="69e28-105">Ten przykład deklaruje [interfejs](../../language-reference/keywords/interface.md), `IDimensions` i klasę, `Box` , która jawnie implementuje elementy członkowskie interfejsu `GetLength` i `GetWidth` .</span><span class="sxs-lookup"><span data-stu-id="69e28-105">This example declares an [interface](../../language-reference/keywords/interface.md), `IDimensions`, and a class, `Box`, which explicitly implements the interface members `GetLength` and `GetWidth`.</span></span> <span data-ttu-id="69e28-106">Dostęp do członków uzyskuje się za pomocą wystąpienia interfejsu `dimensions` .</span><span class="sxs-lookup"><span data-stu-id="69e28-106">The members are accessed through the interface instance `dimensions`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69e28-107">Przykład</span><span class="sxs-lookup"><span data-stu-id="69e28-107">Example</span></span>  

 [!code-csharp[csProgGuideInheritance#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#8)]  
  
## <a name="robust-programming"></a><span data-ttu-id="69e28-108">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="69e28-108">Robust Programming</span></span>  
  
- <span data-ttu-id="69e28-109">Zwróć uwagę, że następujące wiersze w `Main` metodzie są oznaczone jako komentarze, ponieważ spowodują błędy kompilacji.</span><span class="sxs-lookup"><span data-stu-id="69e28-109">Notice that the following lines, in the `Main` method, are commented out because they would produce compilation errors.</span></span> <span data-ttu-id="69e28-110">Nie można uzyskać dostępu do elementu członkowskiego interfejsu, który jest jawnie zaimplementowany z wystąpienia [klasy](../../language-reference/keywords/class.md) :</span><span class="sxs-lookup"><span data-stu-id="69e28-110">An interface member that is explicitly implemented cannot be accessed from a [class](../../language-reference/keywords/class.md) instance:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#45)]  
  
- <span data-ttu-id="69e28-111">Zwróć również uwagę, że w `Main` metodzie pomyślnie Wydrukowano Wymiary pola, ponieważ metody są wywoływane z wystąpienia interfejsu:</span><span class="sxs-lookup"><span data-stu-id="69e28-111">Notice also that the following lines, in the `Main` method, successfully print out the dimensions of the box because the methods are being called from an instance of the interface:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#46)]  
  
## <a name="see-also"></a><span data-ttu-id="69e28-112">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="69e28-112">See also</span></span>

- [<span data-ttu-id="69e28-113">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="69e28-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="69e28-114">Klasy i struktury</span><span class="sxs-lookup"><span data-stu-id="69e28-114">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="69e28-115">Interfejsy</span><span class="sxs-lookup"><span data-stu-id="69e28-115">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="69e28-116">Jawne implementowanie elementów dwóch interfejsów</span><span class="sxs-lookup"><span data-stu-id="69e28-116">How to explicitly implement members of two interfaces</span></span>](./how-to-explicitly-implement-members-of-two-interfaces.md)
