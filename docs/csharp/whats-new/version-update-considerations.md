---
title: Zagadnienia dotyczące wersji i aktualizacji dla deweloperów języka C#
description: Wprowadzenie nowych funkcji języków w bibliotece może mieć wpływ na kod, który go używa.
ms.topic: reference
ms.date: 09/19/2018
ms.openlocfilehash: f7db7c79792d04bcf592bc1858e1f0f05cb34402
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/17/2020
ms.locfileid: "88268130"
---
# <a name="version-and-update-considerations-for-c-developers"></a><span data-ttu-id="52f22-103">Zagadnienia dotyczące wersji i aktualizacji dla deweloperów języka C#</span><span class="sxs-lookup"><span data-stu-id="52f22-103">Version and update considerations for C# developers</span></span>

<span data-ttu-id="52f22-104">Zgodność to istotny cel, ponieważ nowe funkcje są dodawane do języka C#.</span><span class="sxs-lookup"><span data-stu-id="52f22-104">Compatibility is a very important goal as new features are added to the C# language.</span></span> <span data-ttu-id="52f22-105">W prawie wszystkich przypadkach istniejący kod można ponownie skompilować przy użyciu nowej wersji kompilatora bez jakiegokolwiek problemu.</span><span class="sxs-lookup"><span data-stu-id="52f22-105">In almost all cases, existing code can be recompiled with a new compiler version without any issue.</span></span>

<span data-ttu-id="52f22-106">W przypadku przyjmowania nowych funkcji języka w bibliotece może być wymagana większa ostrożność.</span><span class="sxs-lookup"><span data-stu-id="52f22-106">More care may be required when you adopt new language features in a library.</span></span> <span data-ttu-id="52f22-107">Być może tworzysz nową bibliotekę z funkcjami znajdującymi się w najnowszej wersji i musisz upewnić się, że aplikacje skompilowane przy użyciu poprzednich wersji kompilatora mogą go używać.</span><span class="sxs-lookup"><span data-stu-id="52f22-107">You may be creating a new library with features found in the latest version and need to ensure apps built using previous versions of the compiler can use it.</span></span> <span data-ttu-id="52f22-108">Może też być uaktualniana istniejąca biblioteka, a wielu użytkowników może nie mieć jeszcze uaktualnionych wersji.</span><span class="sxs-lookup"><span data-stu-id="52f22-108">Or you may be upgrading an existing library and many of your users may not have upgraded versions yet.</span></span> <span data-ttu-id="52f22-109">Podczas podejmowania decyzji o przyjęciu nowych funkcji należy wziąć pod uwagę dwie zmiany zgodności: zgodne ze źródłem i dane binarne.</span><span class="sxs-lookup"><span data-stu-id="52f22-109">As you make decisions on adopting new features, you'll need to consider two variations of compatibility: source compatible and binary compatible.</span></span>

## <a name="binary-compatible-changes"></a><span data-ttu-id="52f22-110">Zgodne zmiany binarne</span><span class="sxs-lookup"><span data-stu-id="52f22-110">Binary compatible changes</span></span>

<span data-ttu-id="52f22-111">Zmiany w bibliotece są **zgodne ze standardami binarnymi** , gdy zaktualizowana biblioteka może być używana bez konieczności ponownego kompilowania aplikacji i bibliotek, które go używają.</span><span class="sxs-lookup"><span data-stu-id="52f22-111">Changes to your library are **binary compatible** when your updated library can be used without rebuilding applications and libraries that use it.</span></span> <span data-ttu-id="52f22-112">Zestawy zależne nie są wymagane do odbudowania ani nie są wymagane żadne zmiany kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="52f22-112">Dependent assemblies are not required to be rebuilt, nor are any source code changes required.</span></span> <span data-ttu-id="52f22-113">Zmiany zgodne z binarnymi są również zgodnymi ze źródłami.</span><span class="sxs-lookup"><span data-stu-id="52f22-113">Binary compatible changes are also source compatible changes.</span></span>

## <a name="source-compatible-changes"></a><span data-ttu-id="52f22-114">Zmiany zgodne ze źródłem</span><span class="sxs-lookup"><span data-stu-id="52f22-114">Source compatible changes</span></span>

<span data-ttu-id="52f22-115">Zmiany w bibliotece są **zgodne ze źródłem** , gdy aplikacje i biblioteki korzystające z biblioteki nie wymagają zmian w kodzie źródłowym, ale źródło musi zostać ponownie skompilowane w celu poprawnego działania.</span><span class="sxs-lookup"><span data-stu-id="52f22-115">Changes to your library are **source compatible** when applications and libraries that use your library do not require source code changes, but the source must be recompiled against the new version to work correctly.</span></span>

## <a name="incompatible-changes"></a><span data-ttu-id="52f22-116">Niezgodne zmiany</span><span class="sxs-lookup"><span data-stu-id="52f22-116">Incompatible changes</span></span>

<span data-ttu-id="52f22-117">Jeśli zmiana nie jest **zgodna ze źródłem** ani za pomocą elementów **binarnych**, zmiany kodu źródłowego wraz z ponowną kompilacją są wymagane w bibliotekach zależnych i aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="52f22-117">If a change is neither **source compatible** nor **binary compatible**, source code changes along with recompilation are required in dependent libraries and applications.</span></span>

## <a name="evaluate-your-library"></a><span data-ttu-id="52f22-118">Oceń bibliotekę</span><span class="sxs-lookup"><span data-stu-id="52f22-118">Evaluate your library</span></span>

<span data-ttu-id="52f22-119">Te koncepcje zgodności mają wpływ na publiczną i chronioną deklarację biblioteki, a nie jej wewnętrzną implementację.</span><span class="sxs-lookup"><span data-stu-id="52f22-119">These compatibility concepts affect the public and protected declarations for your library, not its internal implementation.</span></span> <span data-ttu-id="52f22-120">Stosowanie wszystkich nowych funkcji wewnętrznie jest zawsze **zgodne ze standardem binarnym**.</span><span class="sxs-lookup"><span data-stu-id="52f22-120">Adopting any new features internally are always **binary compatible**.</span></span>  

<span data-ttu-id="52f22-121">**Zgodne zmiany binarne** zawierają nową składnię, która generuje ten sam skompilowany kod dla deklaracji publicznych jako starszą składnię.</span><span class="sxs-lookup"><span data-stu-id="52f22-121">**Binary compatible** changes provide new syntax that generates the same compiled code for public declarations as the older syntax.</span></span> <span data-ttu-id="52f22-122">Na przykład zmiana metody do elementu członkowskiego z wyrażeniem jest **zgodna z binarną** zmianą:</span><span class="sxs-lookup"><span data-stu-id="52f22-122">For example, changing a method to an expression-bodied member is a **binary compatible** change:</span></span>

<span data-ttu-id="52f22-123">Oryginalny kod:</span><span class="sxs-lookup"><span data-stu-id="52f22-123">Original code:</span></span>

```csharp
public double CalculateSquare(double value)
{
    return value * value;
}
```

<span data-ttu-id="52f22-124">Nowy kod:</span><span class="sxs-lookup"><span data-stu-id="52f22-124">New code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="52f22-125">Zmiany **zgodne ze źródłem** wprowadzają składnię, która zmienia skompilowany kod dla publicznej składowej, ale w sposób zgodny z istniejącymi lokacjami wywołań.</span><span class="sxs-lookup"><span data-stu-id="52f22-125">**Source compatible** changes introduce syntax that changes the compiled code for a public member, but in a way that is compatible with existing call sites.</span></span> <span data-ttu-id="52f22-126">Na przykład zmiana sygnatury metody z parametru przez wartość na `in` parametr przez odwołanie jest zgodne ze źródłem, ale nie jest zgodne z binarną:</span><span class="sxs-lookup"><span data-stu-id="52f22-126">For example, changing a method signature from a by value parameter to an `in` by reference parameter is source compatible, but not binary compatible:</span></span>

<span data-ttu-id="52f22-127">Oryginalny kod:</span><span class="sxs-lookup"><span data-stu-id="52f22-127">Original code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="52f22-128">Nowy kod:</span><span class="sxs-lookup"><span data-stu-id="52f22-128">New code:</span></span>

```csharp
public double CalculateSquare(in double value) => value * value;
```

<span data-ttu-id="52f22-129">W [artykułach nowości należy](index.md) zauważyć, że wprowadzenie funkcji, która ma wpływ na deklaracje publiczne jest zgodne ze źródłem lub plikiem binarnym.</span><span class="sxs-lookup"><span data-stu-id="52f22-129">The [What's new](index.md) articles note if introducing a feature that affects public declarations is source compatible or binary compatible.</span></span>
