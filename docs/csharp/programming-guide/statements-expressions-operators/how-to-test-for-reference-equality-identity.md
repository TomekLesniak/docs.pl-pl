---
title: Jak przetestować równość odwołań (tożsamość) — Przewodnik programowania w języku C#
description: Dowiedz się, jak przetestować równość odwołań (tożsamość). Zobacz przykładowy kod i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- object identity [C#]
- reference equality [C#]
ms.assetid: 91307fda-267b-4fd2-a338-2aada39ee791
ms.openlocfilehash: 1d1a0e5d80ac8d2a689e75acbc6099b92e16f23f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91151444"
---
# <a name="how-to-test-for-reference-equality-identity-c-programming-guide"></a><span data-ttu-id="ebcd3-104">Testowanie równości odwołań (tożsamość) (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="ebcd3-104">How to test for reference equality (Identity) (C# Programming Guide)</span></span>

<span data-ttu-id="ebcd3-105">Nie trzeba implementować żadnej logiki niestandardowej w celu obsługi porównania równości odwołań w typach.</span><span class="sxs-lookup"><span data-stu-id="ebcd3-105">You do not have to implement any custom logic to support reference equality comparisons in your types.</span></span> <span data-ttu-id="ebcd3-106">Ta funkcja jest dostępna dla wszystkich typów przez metodę statyczną <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="ebcd3-106">This functionality is provided for all types by the static <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="ebcd3-107">Poniższy przykład pokazuje, jak określić, czy dwie zmienne mają *równość odwołania*, co oznacza, że odwołują się do tego samego obiektu w pamięci.</span><span class="sxs-lookup"><span data-stu-id="ebcd3-107">The following example shows how to determine whether two variables have *reference equality*, which means that they refer to the same object in memory.</span></span>  
  
 <span data-ttu-id="ebcd3-108">W przykładzie pokazano również, dlaczego <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> zawsze są zwracane `false` dla typów wartości i dlaczego nie należy używać  <xref:System.Object.ReferenceEquals%2A> do określania równości ciągów.</span><span class="sxs-lookup"><span data-stu-id="ebcd3-108">The example also shows why <xref:System.Object.ReferenceEquals%2A?displayProperty=nameWithType> always returns `false` for value types and why you should not use  <xref:System.Object.ReferenceEquals%2A> to determine string equality.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebcd3-109">Przykład</span><span class="sxs-lookup"><span data-stu-id="ebcd3-109">Example</span></span>  

 [!code-csharp[csProgGuideObjects#90](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#90)]  
  
 <span data-ttu-id="ebcd3-110">Implementacja `Equals` w <xref:System.Object?displayProperty=nameWithType> uniwersalnej klasie bazowej również wykonuje kontrolę równości odwołań, ale nie jest to zalecane, ponieważ jeśli klasa ma przesłonić metodę, wyniki mogą nie być oczekiwane.</span><span class="sxs-lookup"><span data-stu-id="ebcd3-110">The implementation of `Equals` in the <xref:System.Object?displayProperty=nameWithType> universal base class also performs a reference equality check, but it is best not to use this because, if a class happens to override the method, the results might not be what you expect.</span></span> <span data-ttu-id="ebcd3-111">Ta sama wartość dotyczy `==` `!=` operatorów i.</span><span class="sxs-lookup"><span data-stu-id="ebcd3-111">The same is true for the `==` and `!=` operators.</span></span> <span data-ttu-id="ebcd3-112">Gdy są one wykonywane na typach referencyjnych, domyślne zachowanie `==` i `!=` ma na celu wykonywanie kontroli równości odwołań.</span><span class="sxs-lookup"><span data-stu-id="ebcd3-112">When they are operating on reference types, the default behavior of `==` and `!=` is to perform a reference equality check.</span></span> <span data-ttu-id="ebcd3-113">Jednak klasy pochodne mogą przeciążać operator, aby wykonać kontrolę równości wartości.</span><span class="sxs-lookup"><span data-stu-id="ebcd3-113">However, derived classes can overload the operator to perform a value equality check.</span></span> <span data-ttu-id="ebcd3-114">Aby zminimalizować prawdopodobieństwo wystąpienia błędu, najlepiej jest zawsze używać, gdy trzeba <xref:System.Object.ReferenceEquals%2A> określić, czy dwa obiekty mają równość odwołania.</span><span class="sxs-lookup"><span data-stu-id="ebcd3-114">To minimize the potential for error, it is best to always use <xref:System.Object.ReferenceEquals%2A> when you have to determine whether two objects have reference equality.</span></span>  
  
 <span data-ttu-id="ebcd3-115">Stałe ciągi w tym samym zestawie są zawsze Interni przez środowisko uruchomieniowe.</span><span class="sxs-lookup"><span data-stu-id="ebcd3-115">Constant strings within the same assembly are always interned by the runtime.</span></span> <span data-ttu-id="ebcd3-116">Oznacza to, że jest obsługiwane tylko jedno wystąpienie każdego unikatowego ciągu literału.</span><span class="sxs-lookup"><span data-stu-id="ebcd3-116">That is, only one instance of each unique literal string is maintained.</span></span> <span data-ttu-id="ebcd3-117">Jednak środowisko uruchomieniowe nie gwarantuje, że ciągi utworzone w czasie wykonywania są InterNIC, ani nie gwarantujemy, że dwie równe ciągi stałe w różnych zestawach są InterNIC.</span><span class="sxs-lookup"><span data-stu-id="ebcd3-117">However, the runtime does not guarantee that strings created at runtime are interned, nor does it guarantee that two equal constant strings in different assemblies are interned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebcd3-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ebcd3-118">See also</span></span>

- [<span data-ttu-id="ebcd3-119">Porównania równości</span><span class="sxs-lookup"><span data-stu-id="ebcd3-119">Equality Comparisons</span></span>](./equality-comparisons.md)
