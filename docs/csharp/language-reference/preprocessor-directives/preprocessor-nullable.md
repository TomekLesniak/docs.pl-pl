---
description: '#Odwołanie do kodu w języku C#'
title: '#Odwołanie do kodu w języku C#'
ms.date: 11/18/2020
f1_keywords:
- '#nullable'
helpviewer_keywords:
- '#nullable directive [C#]'
ms.openlocfilehash: 4c114a09f29769fcc824bcdabdc1d523e33f199d
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099464"
---
# <a name="nullable-c-reference"></a><span data-ttu-id="50f6d-103">#nullable (odwołanie w C#)</span><span class="sxs-lookup"><span data-stu-id="50f6d-103">#nullable (C# Reference)</span></span>

<span data-ttu-id="50f6d-104">`#nullable`Dyrektywa preprocesora ustawia *kontekst adnotacji dopuszczający wartość null* i *kontekst ostrzeżenia o wartości null*.</span><span class="sxs-lookup"><span data-stu-id="50f6d-104">The `#nullable` preprocessor directive sets the *nullable annotation context* and *nullable warning context*.</span></span> <span data-ttu-id="50f6d-105">Ta dyrektywa kontroluje, czy adnotacje dopuszczające wartość null mają wpływ, oraz czy są określone ostrzeżenia o wartości null.</span><span class="sxs-lookup"><span data-stu-id="50f6d-105">This directive controls whether nullable annotations have effect, and whether nullability warnings are given.</span></span> <span data-ttu-id="50f6d-106">Każdy kontekst jest *wyłączony* lub *włączony*.</span><span class="sxs-lookup"><span data-stu-id="50f6d-106">Each context is either *disabled* or *enabled*.</span></span>

<span data-ttu-id="50f6d-107">Oba konteksty można określić na poziomie projektu (poza kodem źródłowym C#).</span><span class="sxs-lookup"><span data-stu-id="50f6d-107">Both contexts can be specified at the project level (outside of C# source code).</span></span> <span data-ttu-id="50f6d-108">`#nullable`Dyrektywa kontroluje konteksty adnotacji i ostrzeżeń i ma pierwszeństwo przed ustawieniami na poziomie projektu.</span><span class="sxs-lookup"><span data-stu-id="50f6d-108">The `#nullable` directive controls the annotation and warning contexts and takes precedence over the project-level settings.</span></span> <span data-ttu-id="50f6d-109">Dyrektywa ustawia konteksty, które kontroluje, dopóki inna dyrektywa przesłoni ją lub do końca pliku źródłowego.</span><span class="sxs-lookup"><span data-stu-id="50f6d-109">A directive sets the context(s) it controls until another directive overrides it, or until the end of the source file.</span></span>

<span data-ttu-id="50f6d-110">Efekty dyrektyw są następujące:</span><span class="sxs-lookup"><span data-stu-id="50f6d-110">The effect of the directives is as follows:</span></span>

- <span data-ttu-id="50f6d-111">`#nullable disable`: Ustawia adnotacje dopuszczające wartość null i konteksty ostrzeżeń do *wyłączania*.</span><span class="sxs-lookup"><span data-stu-id="50f6d-111">`#nullable disable`: Sets the nullable annotation and warning contexts to *disabled*.</span></span>
- <span data-ttu-id="50f6d-112">`#nullable enable`: Ustawia do *włączenia* adnotację z dopuszczaniem wartości null i kontekstów ostrzeżeń.</span><span class="sxs-lookup"><span data-stu-id="50f6d-112">`#nullable enable`: Sets the nullable annotation and warning contexts to *enabled*.</span></span>
- <span data-ttu-id="50f6d-113">`#nullable restore`: Przywraca w ustawieniach projektu adnotację dopuszczającą wartość null i konteksty ostrzeżenia.</span><span class="sxs-lookup"><span data-stu-id="50f6d-113">`#nullable restore`: Restores the nullable annotation and warning contexts to project settings.</span></span>
- <span data-ttu-id="50f6d-114">`#nullable disable annotations`: Ustawia kontekst adnotacji dopuszczającej wartość null na *wyłączony*.</span><span class="sxs-lookup"><span data-stu-id="50f6d-114">`#nullable disable annotations`: Sets the nullable annotation context to *disabled*.</span></span>
- <span data-ttu-id="50f6d-115">`#nullable enable annotations`: Ustawia kontekst adnotacji dopuszczający wartość *null.*</span><span class="sxs-lookup"><span data-stu-id="50f6d-115">`#nullable enable annotations`: Sets the nullable annotation context to *enabled*.</span></span>
- <span data-ttu-id="50f6d-116">`#nullable restore annotations`: Przywraca kontekst adnotacji dopuszczający wartość null do ustawień projektu.</span><span class="sxs-lookup"><span data-stu-id="50f6d-116">`#nullable restore annotations`: Restores the nullable annotation context to project settings.</span></span>
- <span data-ttu-id="50f6d-117">`#nullable disable warnings`: Ustawia kontekst ostrzeżenia wartości null na *wyłączony*.</span><span class="sxs-lookup"><span data-stu-id="50f6d-117">`#nullable disable warnings`: Sets the nullable warning context to *disabled*.</span></span>
- <span data-ttu-id="50f6d-118">`#nullable enable warnings`: Ustawia kontekst ostrzegawczy dopuszczający wartość *null.*</span><span class="sxs-lookup"><span data-stu-id="50f6d-118">`#nullable enable warnings`: Sets the nullable warning context to *enabled*.</span></span>
- <span data-ttu-id="50f6d-119">`#nullable restore warnings`: Przywraca kontekst ostrzegawczy dopuszczający wartość null do ustawień projektu.</span><span class="sxs-lookup"><span data-stu-id="50f6d-119">`#nullable restore warnings`: Restores the nullable warning context to project settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="50f6d-120">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="50f6d-120">See also</span></span>

- [<span data-ttu-id="50f6d-121">Odwołanie w C#</span><span class="sxs-lookup"><span data-stu-id="50f6d-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="50f6d-122">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="50f6d-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="50f6d-123">Dyrektywy preprocesora języka C#</span><span class="sxs-lookup"><span data-stu-id="50f6d-123">C# Preprocessor Directives</span></span>](./index.md)
