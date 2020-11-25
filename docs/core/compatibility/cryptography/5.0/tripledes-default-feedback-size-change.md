---
title: 'Zmiana podziału: domyślna wartość FeedbackSize dla wystąpień utworzonych przez TripleDES. Create zmieniony'
description: Zapoznaj się z istotną zmianą w programie .NET 5,0, gdzie wartość domyślna właściwości FeedbackSize w wystąpieniu TripleDES zwrócona z TripleDES. Create () zmieniła się z 64 na 8..
ms.date: 10/16/2020
ms.openlocfilehash: 4179da17bf2e5cc5fcc7d64d83ba92119f912042
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95761600"
---
# <a name="default-feedbacksize-value-for-instances-created-by-tripledescreate-changed"></a><span data-ttu-id="917d8-103">Domyślna wartość FeedbackSize dla wystąpień utworzonych przez TripleDES. Create zmieniony</span><span class="sxs-lookup"><span data-stu-id="917d8-103">Default FeedbackSize value for instances created by TripleDES.Create changed</span></span>

<span data-ttu-id="917d8-104">Wartość domyślna <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=nameWithType> właściwości <xref:System.Security.Cryptography.TripleDES> wystąpienia zwróconego z <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> został zmieniony z 64 na 8, aby ułatwić migrację z .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="917d8-104">The default value for the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=nameWithType> property on the <xref:System.Security.Cryptography.TripleDES> instance returned from <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> has changed from 64 to 8 to make migration from .NET Framework easier.</span></span> <span data-ttu-id="917d8-105">Ta właściwość, chyba że jest używana bezpośrednio w kodzie wywołującym, jest używana tylko wtedy, gdy <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> Właściwość jest <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="917d8-105">This property, unless used directly in caller code, is used only when the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> property is <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="917d8-106">Obsługa <xref:System.Security.Cryptography.CipherMode.CFB> tego trybu została najpierw dodana do platformy .NET dla wersji 5,0 RC1, dlatego ta zmiana powinna mieć wpływ tylko na aplikacje .net 5,0 RC1 i .net 5,0 RC2.</span><span class="sxs-lookup"><span data-stu-id="917d8-106">Support for the <xref:System.Security.Cryptography.CipherMode.CFB> mode was first added to .NET for the 5.0 RC1 release, so only .NET 5.0 RC1 and .NET 5.0 RC2 applications should be impacted by this change.</span></span>

## <a name="change-description"></a><span data-ttu-id="917d8-107">Zmień opis</span><span class="sxs-lookup"><span data-stu-id="917d8-107">Change description</span></span>

<span data-ttu-id="917d8-108">W programie .NET Core i starszych wersjach wstępnych programu .NET 5,0 `TripleDES.Create().FeedbackSize` ma wartość domyślną 64.</span><span class="sxs-lookup"><span data-stu-id="917d8-108">In .NET Core and previous pre-release versions of .NET 5.0, `TripleDES.Create().FeedbackSize` has a default value of 64.</span></span> <span data-ttu-id="917d8-109">Począwszy od wersji RTM programu .NET 5,0, `TripleDES.Create().FeedbackSize` ma wartość domyślną 8.</span><span class="sxs-lookup"><span data-stu-id="917d8-109">Starting in the RTM version of .NET 5.0, `TripleDES.Create().FeedbackSize` has a default value of 8.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="917d8-110">Przyczyna zmiany</span><span class="sxs-lookup"><span data-stu-id="917d8-110">Reason for change</span></span>

<span data-ttu-id="917d8-111">W .NET Framework <xref:System.Security.Cryptography.TripleDES> Klasa bazowa domyślnie przyjmuje wartość <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> do 64, ale <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> Klasa zastępuje domyślnie 8.</span><span class="sxs-lookup"><span data-stu-id="917d8-111">In .NET Framework, the <xref:System.Security.Cryptography.TripleDES> base class defaults the value of <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> to 64, but the <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> class overwrites the default to 8.</span></span> <span data-ttu-id="917d8-112">Gdy <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> Właściwość została wprowadzona do programu .NET Core w wersji 2,0, takie samo zachowanie zostało zachowane.</span><span class="sxs-lookup"><span data-stu-id="917d8-112">When the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property was introduced to .NET Core in version 2.0, this same behavior was preserved.</span></span> <span data-ttu-id="917d8-113">Jednak w .NET Framework <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> zwraca wystąpienie <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> , dlatego wartość domyślna z fabryki algorytmów wynosi 8.</span><span class="sxs-lookup"><span data-stu-id="917d8-113">However, in .NET Framework, <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> returns an instance of <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider>, so the default value from the algorithm factory is 8.</span></span> <span data-ttu-id="917d8-114">W przypadku platformy .NET Core i .NET 5 + fabryka algorytmów zwraca niepubliczną implementację, która w razie potrzeby miała wartość domyślną 64.</span><span class="sxs-lookup"><span data-stu-id="917d8-114">For .NET Core and .NET 5+, the algorithm factory returns a non-public implementation, which, until now, had a default value of 64.</span></span>

<span data-ttu-id="917d8-115">Zmiana <xref:System.Security.Cryptography.TripleDES> klasy implementacji " <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> value to 8" umożliwia aplikacjom napisanym dla .NET Framework, które określiły tryb szyfru <xref:System.Security.Cryptography.CipherMode.CFB> , ale niejawnie przypisanie <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> właściwości, w celu kontynuowania działania w programie .NET 5.</span><span class="sxs-lookup"><span data-stu-id="917d8-115">Changing the <xref:System.Security.Cryptography.TripleDES> implementation class' <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> value to 8 allows for applications written for .NET Framework that specified the cipher mode as <xref:System.Security.Cryptography.CipherMode.CFB> but didn't explicitly assign the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property, to continue to function on .NET 5.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="917d8-116">Wprowadzona wersja</span><span class="sxs-lookup"><span data-stu-id="917d8-116">Version introduced</span></span>

<span data-ttu-id="917d8-117">5,0</span><span class="sxs-lookup"><span data-stu-id="917d8-117">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="917d8-118">Zalecana akcja</span><span class="sxs-lookup"><span data-stu-id="917d8-118">Recommended action</span></span>

<span data-ttu-id="917d8-119">Aplikacje, które szyfrują lub odszyfrowują dane w wersji RC1 lub RC2 programu .NET 5,0, to CFB64, gdy spełnione są następujące warunki:</span><span class="sxs-lookup"><span data-stu-id="917d8-119">Applications that encrypt or decrypt data in the RC1 or RC2 versions of .NET 5.0 do so with CFB64, when the following conditions are met:</span></span>

- <span data-ttu-id="917d8-120">Z <xref:System.Security.Cryptography.TripleDES> wystąpieniem <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="917d8-120">With a <xref:System.Security.Cryptography.TripleDES> instance from <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=nameWithType>.</span></span>
- <span data-ttu-id="917d8-121">Używanie wartości domyślnej dla <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> .</span><span class="sxs-lookup"><span data-stu-id="917d8-121">Using the default value for <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>.</span></span>
- <span data-ttu-id="917d8-122">Z <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> właściwością ustawioną na <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="917d8-122">With the <xref:System.Security.Cryptography.SymmetricAlgorithm.Mode> property set to <xref:System.Security.Cryptography.CipherMode.CFB?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="917d8-123">Aby zachować to zachowanie, przypisz <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> Właściwość do `64` .</span><span class="sxs-lookup"><span data-stu-id="917d8-123">To maintain this behavior, assign the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property to `64`.</span></span>

<span data-ttu-id="917d8-124">Nie wszystkie `TripleDES` implementacje używają tego samego ustawienia domyślnego dla programu <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> .</span><span class="sxs-lookup"><span data-stu-id="917d8-124">Not all `TripleDES` implementations use the same default for <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize>.</span></span> <span data-ttu-id="917d8-125">Zaleca się, aby w przypadku użycia <xref:System.Security.Cryptography.CipherMode.CFB> trybu szyfru w <xref:System.Security.Cryptography.TripleDES> wystąpieniach zawsze jawnie przypisać <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> wartość właściwości.</span><span class="sxs-lookup"><span data-stu-id="917d8-125">We recommend that if you use the <xref:System.Security.Cryptography.CipherMode.CFB> cipher mode on <xref:System.Security.Cryptography.TripleDES> instances, you should always explicitly assign the <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize> property value.</span></span>

```csharp
TripleDES cipher = TripleDES.Create();
cipher.Mode = CipherMode.CFB;
// Explicitly set the FeedbackSize for CFB to control between CFB8 and CFB64.
cipher.FeedbackSize = 8;
```

## <a name="affected-apis"></a><span data-ttu-id="917d8-126">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="917d8-126">Affected APIs</span></span>

- <xref:System.Security.Cryptography.TripleDES.Create?displayProperty=fullName>
- <xref:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Security.Cryptography.TripleDES.Create`
- `P:System.Security.Cryptography.SymmetricAlgorithm.FeedbackSize`

### Category

- Cryptography

-->
