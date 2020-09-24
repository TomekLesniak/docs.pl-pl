---
title: Konstruktory prywatne — Przewodnik programowania w języku C#
description: Konstruktor prywatny jest specjalnym konstruktorem wystąpienia w języku C# używanym do ograniczania sposobu tworzenia obiektu. Mogą być używane z metodami fabryki lub innymi idiomy konstrukcyjnymi.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: c6048424128b462bfc56d9c7c3cf8f75cca9298d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159348"
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="54176-104">Konstruktory prywatne (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="54176-104">Private Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="54176-105">Konstruktor prywatny jest specjalnym konstruktorem wystąpień.</span><span class="sxs-lookup"><span data-stu-id="54176-105">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="54176-106">Jest on zazwyczaj używany w klasach, które zawierają tylko statyczne elementy członkowskie.</span><span class="sxs-lookup"><span data-stu-id="54176-106">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="54176-107">Jeśli klasa ma jeden lub więcej konstruktorów prywatnych i nie ma konstruktorów publicznych, inne klasy (poza klasami zagnieżdżonymi) nie mogą tworzyć wystąpień tej klasy.</span><span class="sxs-lookup"><span data-stu-id="54176-107">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="54176-108">Na przykład:</span><span class="sxs-lookup"><span data-stu-id="54176-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 <span data-ttu-id="54176-109">Deklaracja pustego konstruktora uniemożliwia automatyczne generowanie konstruktora bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="54176-109">The declaration of the empty constructor prevents the automatic generation of a parameterless constructor.</span></span> <span data-ttu-id="54176-110">Należy pamiętać, że jeśli nie używasz modyfikatora dostępu z konstruktorem, będzie on nadal domyślnie prywatny.</span><span class="sxs-lookup"><span data-stu-id="54176-110">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="54176-111">Jednak modyfikator [prywatny](../../language-reference/keywords/private.md) jest zwykle używany jawnie, aby wyczyścił, że nie można utworzyć wystąpienia klasy.</span><span class="sxs-lookup"><span data-stu-id="54176-111">However, the [private](../../language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="54176-112">Konstruktory prywatne są używane do zapobiegania tworzeniu wystąpień klasy w przypadku braku pól lub metod wystąpienia, takich jak <xref:System.Math> Klasa, lub gdy wywoływana jest metoda w celu uzyskania wystąpienia klasy.</span><span class="sxs-lookup"><span data-stu-id="54176-112">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="54176-113">Jeśli wszystkie metody w klasie są statyczne, należy rozważyć uczynienie kompletnej klasy statycznej.</span><span class="sxs-lookup"><span data-stu-id="54176-113">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="54176-114">Aby uzyskać więcej informacji [, zobacz klasy statyczne i statyczne elementy członkowskie klas](./static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="54176-114">For more information see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="54176-115">Przykład</span><span class="sxs-lookup"><span data-stu-id="54176-115">Example</span></span>  

 <span data-ttu-id="54176-116">Poniżej znajduje się przykład klasy korzystającej z konstruktora prywatnego.</span><span class="sxs-lookup"><span data-stu-id="54176-116">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[csProgGuideObjects#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#12)]  
  
 <span data-ttu-id="54176-117">Zwróć uwagę, że jeśli dodasz komentarz z następującej instrukcji z przykładu, zostanie wygenerowany błąd, ponieważ Konstruktor jest niedostępny z powodu swojego poziomu ochrony:</span><span class="sxs-lookup"><span data-stu-id="54176-117">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[csProgGuideObjects#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#13)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="54176-118">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="54176-118">C# Language Specification</span></span>  

<span data-ttu-id="54176-119">Aby uzyskać więcej informacji, zobacz [prywatne konstruktory](~/_csharplang/spec/classes.md#private-constructors) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="54176-119">For more information, see [Private constructors](~/_csharplang/spec/classes.md#private-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="54176-120">Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.</span><span class="sxs-lookup"><span data-stu-id="54176-120">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="54176-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="54176-121">See also</span></span>

- [<span data-ttu-id="54176-122">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="54176-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="54176-123">Klasy i struktury</span><span class="sxs-lookup"><span data-stu-id="54176-123">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="54176-124">Konstruktory</span><span class="sxs-lookup"><span data-stu-id="54176-124">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="54176-125">Finalizatory</span><span class="sxs-lookup"><span data-stu-id="54176-125">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="54176-126">private</span><span class="sxs-lookup"><span data-stu-id="54176-126">private</span></span>](../../language-reference/keywords/private.md)
- [<span data-ttu-id="54176-127">public</span><span class="sxs-lookup"><span data-stu-id="54176-127">public</span></span>](../../language-reference/keywords/public.md)
