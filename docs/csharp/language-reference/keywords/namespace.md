---
description: Namespace — słowo kluczowe — odwołanie w C#
title: Namespace — słowo kluczowe — odwołanie w C#
ms.date: 07/20/2015
f1_keywords:
- namespace_CSharpKeyword
- namespace
helpviewer_keywords:
- namespace keyword [C#]
- scope [C#]
ms.assetid: 0a788423-9110-42e0-97d9-bda41ca4870f
ms.openlocfilehash: a6cfd1c3d37cbdef1f0dd72ddca85ce91f2e183b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139583"
---
# <a name="namespace-c-reference"></a><span data-ttu-id="c22b4-103">namespace (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="c22b4-103">namespace (C# Reference)</span></span>

<span data-ttu-id="c22b4-104">`namespace`Słowo kluczowe jest używane do deklarowania zakresu, który zawiera zestaw powiązanych obiektów.</span><span class="sxs-lookup"><span data-stu-id="c22b4-104">The `namespace` keyword is used to declare a scope that contains a set of related objects.</span></span> <span data-ttu-id="c22b4-105">Można użyć przestrzeni nazw do organizowania elementów kodu i tworzenia unikatowych typów globalnie.</span><span class="sxs-lookup"><span data-stu-id="c22b4-105">You can use a namespace to organize code elements and to create globally unique types.</span></span>

[!code-csharp[csrefKeywordsNamespace#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#1)]

## <a name="remarks"></a><span data-ttu-id="c22b4-106">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c22b4-106">Remarks</span></span>

<span data-ttu-id="c22b4-107">W przestrzeni nazw można zadeklarować zero lub więcej następujących typów:</span><span class="sxs-lookup"><span data-stu-id="c22b4-107">Within a namespace, you can declare zero or more of the following types:</span></span>

- <span data-ttu-id="c22b4-108">inna przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="c22b4-108">another namespace</span></span>

- [<span data-ttu-id="c22b4-109">określonej</span><span class="sxs-lookup"><span data-stu-id="c22b4-109">class</span></span>](class.md)

- [<span data-ttu-id="c22b4-110">interfejsu</span><span class="sxs-lookup"><span data-stu-id="c22b4-110">interface</span></span>](interface.md)

- [<span data-ttu-id="c22b4-111">konstrukcja</span><span class="sxs-lookup"><span data-stu-id="c22b4-111">struct</span></span>](../builtin-types/struct.md)

- [<span data-ttu-id="c22b4-112">podstawowe</span><span class="sxs-lookup"><span data-stu-id="c22b4-112">enum</span></span>](../builtin-types/enum.md)

- [<span data-ttu-id="c22b4-113">Wierz</span><span class="sxs-lookup"><span data-stu-id="c22b4-113">delegate</span></span>](../builtin-types/reference-types.md#the-delegate-type)

<span data-ttu-id="c22b4-114">Niezależnie od tego, czy jawnie deklarujesz przestrzeń nazw w pliku źródłowym C#, kompilator dodaje domyślną przestrzeń nazw.</span><span class="sxs-lookup"><span data-stu-id="c22b4-114">Whether or not you explicitly declare a namespace in a C# source file, the compiler adds a default namespace.</span></span> <span data-ttu-id="c22b4-115">NIENAZWANA przestrzeń nazw, czasami określana jako globalna przestrzeń nazw, jest obecna w każdym pliku.</span><span class="sxs-lookup"><span data-stu-id="c22b4-115">This unnamed namespace, sometimes referred to as the global namespace, is present in every file.</span></span> <span data-ttu-id="c22b4-116">Wszystkie identyfikatory w globalnej przestrzeni nazw są dostępne do użycia w nazwanym obszarze nazw.</span><span class="sxs-lookup"><span data-stu-id="c22b4-116">Any identifier in the global namespace is available for use in a named namespace.</span></span>

<span data-ttu-id="c22b4-117">Przestrzenie nazw niejawnie mają dostęp publiczny i nie są modyfikowane.</span><span class="sxs-lookup"><span data-stu-id="c22b4-117">Namespaces implicitly have public access and this is not modifiable.</span></span> <span data-ttu-id="c22b4-118">Aby uzyskać Omówienie modyfikatorów dostępu, które można przypisać do elementów w przestrzeni nazw, zobacz [Modyfikatory dostępu](access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="c22b4-118">For a discussion of the access modifiers you can assign to elements in a namespace, see [Access Modifiers](access-modifiers.md).</span></span>

<span data-ttu-id="c22b4-119">Istnieje możliwość zdefiniowania przestrzeni nazw w dwóch lub większej liczbie deklaracji.</span><span class="sxs-lookup"><span data-stu-id="c22b4-119">It is possible to define a namespace in two or more declarations.</span></span> <span data-ttu-id="c22b4-120">Na przykład poniższy przykład definiuje dwie klasy jako część `MyCompany` przestrzeni nazw:</span><span class="sxs-lookup"><span data-stu-id="c22b4-120">For example, the following example defines two classes as part of the `MyCompany` namespace:</span></span>

[!code-csharp[csrefKeywordsNamespace#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#2)]

## <a name="example"></a><span data-ttu-id="c22b4-121">Przykład</span><span class="sxs-lookup"><span data-stu-id="c22b4-121">Example</span></span>

<span data-ttu-id="c22b4-122">Poniższy przykład pokazuje, jak wywołać metodę statyczną w zagnieżdżonej przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="c22b4-122">The following example shows how to call a static method in a nested namespace.</span></span>

[!code-csharp[csrefKeywordsNamespace#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="c22b4-123">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="c22b4-123">C# language specification</span></span>

<span data-ttu-id="c22b4-124">Aby uzyskać więcej informacji, zobacz sekcję [przestrzenie nazw](~/_csharplang/spec/namespaces.md) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="c22b4-124">For more information, see the [Namespaces](~/_csharplang/spec/namespaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c22b4-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c22b4-125">See also</span></span>

- [<span data-ttu-id="c22b4-126">Dokumentacja języka C#</span><span class="sxs-lookup"><span data-stu-id="c22b4-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="c22b4-127">Słowa kluczowe języka C#</span><span class="sxs-lookup"><span data-stu-id="c22b4-127">C# keywords</span></span>](index.md)
- [<span data-ttu-id="c22b4-128">using</span><span class="sxs-lookup"><span data-stu-id="c22b4-128">using</span></span>](using-directive.md)
- [<span data-ttu-id="c22b4-129">Używanie static</span><span class="sxs-lookup"><span data-stu-id="c22b4-129">using static</span></span>](using-static.md)
- [<span data-ttu-id="c22b4-130">Kwalifikator aliasu przestrzeni nazw `::`</span><span class="sxs-lookup"><span data-stu-id="c22b4-130">Namespace alias qualifier `::`</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="c22b4-131">Namespaces</span><span class="sxs-lookup"><span data-stu-id="c22b4-131">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
