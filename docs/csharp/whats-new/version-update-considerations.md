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
# <a name="version-and-update-considerations-for-c-developers"></a>Zagadnienia dotyczące wersji i aktualizacji dla deweloperów języka C#

Zgodność to istotny cel, ponieważ nowe funkcje są dodawane do języka C#. W prawie wszystkich przypadkach istniejący kod można ponownie skompilować przy użyciu nowej wersji kompilatora bez jakiegokolwiek problemu.

W przypadku przyjmowania nowych funkcji języka w bibliotece może być wymagana większa ostrożność. Być może tworzysz nową bibliotekę z funkcjami znajdującymi się w najnowszej wersji i musisz upewnić się, że aplikacje skompilowane przy użyciu poprzednich wersji kompilatora mogą go używać. Może też być uaktualniana istniejąca biblioteka, a wielu użytkowników może nie mieć jeszcze uaktualnionych wersji. Podczas podejmowania decyzji o przyjęciu nowych funkcji należy wziąć pod uwagę dwie zmiany zgodności: zgodne ze źródłem i dane binarne.

## <a name="binary-compatible-changes"></a>Zgodne zmiany binarne

Zmiany w bibliotece są **zgodne ze standardami binarnymi** , gdy zaktualizowana biblioteka może być używana bez konieczności ponownego kompilowania aplikacji i bibliotek, które go używają. Zestawy zależne nie są wymagane do odbudowania ani nie są wymagane żadne zmiany kodu źródłowego. Zmiany zgodne z binarnymi są również zgodnymi ze źródłami.

## <a name="source-compatible-changes"></a>Zmiany zgodne ze źródłem

Zmiany w bibliotece są **zgodne ze źródłem** , gdy aplikacje i biblioteki korzystające z biblioteki nie wymagają zmian w kodzie źródłowym, ale źródło musi zostać ponownie skompilowane w celu poprawnego działania.

## <a name="incompatible-changes"></a>Niezgodne zmiany

Jeśli zmiana nie jest **zgodna ze źródłem** ani za pomocą elementów **binarnych**, zmiany kodu źródłowego wraz z ponowną kompilacją są wymagane w bibliotekach zależnych i aplikacjach.

## <a name="evaluate-your-library"></a>Oceń bibliotekę

Te koncepcje zgodności mają wpływ na publiczną i chronioną deklarację biblioteki, a nie jej wewnętrzną implementację. Stosowanie wszystkich nowych funkcji wewnętrznie jest zawsze **zgodne ze standardem binarnym**.  

**Zgodne zmiany binarne** zawierają nową składnię, która generuje ten sam skompilowany kod dla deklaracji publicznych jako starszą składnię. Na przykład zmiana metody do elementu członkowskiego z wyrażeniem jest **zgodna z binarną** zmianą:

Oryginalny kod:

```csharp
public double CalculateSquare(double value)
{
    return value * value;
}
```

Nowy kod:

```csharp
public double CalculateSquare(double value) => value * value;
```

Zmiany **zgodne ze źródłem** wprowadzają składnię, która zmienia skompilowany kod dla publicznej składowej, ale w sposób zgodny z istniejącymi lokacjami wywołań. Na przykład zmiana sygnatury metody z parametru przez wartość na `in` parametr przez odwołanie jest zgodne ze źródłem, ale nie jest zgodne z binarną:

Oryginalny kod:

```csharp
public double CalculateSquare(double value) => value * value;
```

Nowy kod:

```csharp
public double CalculateSquare(in double value) => value * value;
```

W [artykułach nowości należy](index.md) zauważyć, że wprowadzenie funkcji, która ma wpływ na deklaracje publiczne jest zgodne ze źródłem lub plikiem binarnym.
