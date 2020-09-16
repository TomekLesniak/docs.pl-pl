---
title: Zagadnienia dotyczące wersji i aktualizacji dla deweloperów języka C#
description: Wprowadzenie nowych funkcji języków w bibliotece może mieć wpływ na kod, który go używa.
ms.topic: reference
ms.date: 09/19/2018
ms.openlocfilehash: 6de0e3ba33af34edba73819dcb9268f40f8a5ea4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552430"
---
# <a name="version-and-update-considerations-for-c-developers"></a><span data-ttu-id="3c0d1-103">Zagadnienia dotyczące wersji i aktualizacji dla deweloperów języka C#</span><span class="sxs-lookup"><span data-stu-id="3c0d1-103">Version and update considerations for C# developers</span></span>

<span data-ttu-id="3c0d1-104">Zgodność to istotny cel, ponieważ nowe funkcje są dodawane do języka C#.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-104">Compatibility is a very important goal as new features are added to the C# language.</span></span> <span data-ttu-id="3c0d1-105">W prawie wszystkich przypadkach istniejący kod można ponownie skompilować przy użyciu nowej wersji kompilatora bez jakiegokolwiek problemu.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-105">In almost all cases, existing code can be recompiled with a new compiler version without any issue.</span></span>

<span data-ttu-id="3c0d1-106">W przypadku przyjmowania nowych funkcji języka w bibliotece może być wymagana większa ostrożność.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-106">More care may be required when you adopt new language features in a library.</span></span> <span data-ttu-id="3c0d1-107">Być może tworzysz nową bibliotekę z funkcjami znajdującymi się w najnowszej wersji i musisz upewnić się, że aplikacje skompilowane przy użyciu poprzednich wersji kompilatora mogą go używać.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-107">You may be creating a new library with features found in the latest version and need to ensure apps built using previous versions of the compiler can use it.</span></span> <span data-ttu-id="3c0d1-108">Może też być uaktualniana istniejąca biblioteka, a wielu użytkowników może nie mieć jeszcze uaktualnionych wersji.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-108">Or you may be upgrading an existing library and many of your users may not have upgraded versions yet.</span></span> <span data-ttu-id="3c0d1-109">Podczas podejmowania decyzji o przyjęciu nowych funkcji należy wziąć pod uwagę dwie zmiany zgodności: zgodne ze źródłem i dane binarne.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-109">As you make decisions on adopting new features, you'll need to consider two variations of compatibility: source compatible and binary compatible.</span></span>

## <a name="binary-compatible-changes"></a><span data-ttu-id="3c0d1-110">Zgodne zmiany binarne</span><span class="sxs-lookup"><span data-stu-id="3c0d1-110">Binary compatible changes</span></span>

<span data-ttu-id="3c0d1-111">Zmiany w bibliotece są **zgodne ze standardami binarnymi** , gdy zaktualizowana biblioteka może być używana bez konieczności ponownego kompilowania aplikacji i bibliotek, które go używają.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-111">Changes to your library are **binary compatible** when your updated library can be used without rebuilding applications and libraries that use it.</span></span> <span data-ttu-id="3c0d1-112">Zestawy zależne nie są wymagane do odbudowania ani nie są wymagane żadne zmiany kodu źródłowego.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-112">Dependent assemblies are not required to be rebuilt, nor are any source code changes required.</span></span> <span data-ttu-id="3c0d1-113">Zmiany zgodne z binarnymi są również zgodnymi ze źródłami.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-113">Binary compatible changes are also source compatible changes.</span></span>

## <a name="source-compatible-changes"></a><span data-ttu-id="3c0d1-114">Zmiany zgodne ze źródłem</span><span class="sxs-lookup"><span data-stu-id="3c0d1-114">Source compatible changes</span></span>

<span data-ttu-id="3c0d1-115">Zmiany w bibliotece są **zgodne ze źródłem** , gdy aplikacje i biblioteki korzystające z biblioteki nie wymagają zmian w kodzie źródłowym, ale źródło musi zostać ponownie skompilowane w celu poprawnego działania.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-115">Changes to your library are **source compatible** when applications and libraries that use your library do not require source code changes, but the source must be recompiled against the new version to work correctly.</span></span>

## <a name="incompatible-changes"></a><span data-ttu-id="3c0d1-116">Niezgodne zmiany</span><span class="sxs-lookup"><span data-stu-id="3c0d1-116">Incompatible changes</span></span>

<span data-ttu-id="3c0d1-117">Jeśli zmiana nie jest **zgodna ze źródłem** ani za pomocą elementów **binarnych**, zmiany kodu źródłowego wraz z ponowną kompilacją są wymagane w bibliotekach zależnych i aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-117">If a change is neither **source compatible** nor **binary compatible**, source code changes along with recompilation are required in dependent libraries and applications.</span></span>

## <a name="evaluate-your-library"></a><span data-ttu-id="3c0d1-118">Oceń bibliotekę</span><span class="sxs-lookup"><span data-stu-id="3c0d1-118">Evaluate your library</span></span>

<span data-ttu-id="3c0d1-119">Te koncepcje zgodności mają wpływ na publiczną i chronioną deklarację biblioteki, a nie jej wewnętrzną implementację.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-119">These compatibility concepts affect the public and protected declarations for your library, not its internal implementation.</span></span> <span data-ttu-id="3c0d1-120">Stosowanie wszystkich nowych funkcji wewnętrznie jest zawsze **zgodne ze standardem binarnym**.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-120">Adopting any new features internally are always **binary compatible**.</span></span>  

<span data-ttu-id="3c0d1-121">**Zgodne zmiany binarne** zawierają nową składnię, która generuje ten sam skompilowany kod dla deklaracji publicznych jako starszą składnię.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-121">**Binary compatible** changes provide new syntax that generates the same compiled code for public declarations as the older syntax.</span></span> <span data-ttu-id="3c0d1-122">Na przykład zmiana metody do elementu członkowskiego z wyrażeniem jest **zgodna z binarną** zmianą:</span><span class="sxs-lookup"><span data-stu-id="3c0d1-122">For example, changing a method to an expression-bodied member is a **binary compatible** change:</span></span>

<span data-ttu-id="3c0d1-123">Oryginalny kod:</span><span class="sxs-lookup"><span data-stu-id="3c0d1-123">Original code:</span></span>

```csharp
public double CalculateSquare(double value)
{
    return value * value;
}
```

<span data-ttu-id="3c0d1-124">Nowy kod:</span><span class="sxs-lookup"><span data-stu-id="3c0d1-124">New code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="3c0d1-125">Zmiany **zgodne ze źródłem** wprowadzają składnię, która zmienia skompilowany kod dla publicznej składowej, ale w sposób zgodny z istniejącymi lokacjami wywołań.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-125">**Source compatible** changes introduce syntax that changes the compiled code for a public member, but in a way that is compatible with existing call sites.</span></span> <span data-ttu-id="3c0d1-126">Na przykład zmiana sygnatury metody z parametru przez wartość na `in` parametr przez odwołanie jest zgodne ze źródłem, ale nie jest zgodne z binarną:</span><span class="sxs-lookup"><span data-stu-id="3c0d1-126">For example, changing a method signature from a by value parameter to an `in` by reference parameter is source compatible, but not binary compatible:</span></span>

<span data-ttu-id="3c0d1-127">Oryginalny kod:</span><span class="sxs-lookup"><span data-stu-id="3c0d1-127">Original code:</span></span>

```csharp
public double CalculateSquare(double value) => value * value;
```

<span data-ttu-id="3c0d1-128">Nowy kod:</span><span class="sxs-lookup"><span data-stu-id="3c0d1-128">New code:</span></span>

```csharp
public double CalculateSquare(in double value) => value * value;
```

<span data-ttu-id="3c0d1-129">W [artykułach nowości należy](./csharp-9.md) zauważyć, że wprowadzenie funkcji, która ma wpływ na deklaracje publiczne jest zgodne ze źródłem lub plikiem binarnym.</span><span class="sxs-lookup"><span data-stu-id="3c0d1-129">The [What's new](./csharp-9.md) articles note if introducing a feature that affects public declarations is source compatible or binary compatible.</span></span>
