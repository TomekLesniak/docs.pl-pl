---
title: Niebezpieczny kod i wskaźniki — Przewodnik programowania w języku C#
Description: Poznaj niebezpieczny kod i wskaźniki. Język C# nie obsługuje wskaźników, ale można zdefiniować niebezpieczny kontekst, w którym wskaźniki mogą być używane ze słowem kluczowym "UNSAFE".
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: 5684a97ed6f7b6632d8fe3d52747d9187c4b8cbc
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381778"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="e6541-104">Niebezpieczny kod i wskaźniki (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="e6541-104">Unsafe code and pointers (C# Programming Guide)</span></span>

<span data-ttu-id="e6541-105">Aby zachować bezpieczeństwo typu i zabezpieczenia, język C# nie obsługuje domyślnie arytmetycznego wskaźnika.</span><span class="sxs-lookup"><span data-stu-id="e6541-105">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="e6541-106">Jednak za pomocą słowa kluczowego [UNSAFE](../../language-reference/keywords/unsafe.md) można zdefiniować niebezpieczny kontekst, w którym można używać wskaźników.</span><span class="sxs-lookup"><span data-stu-id="e6541-106">However, by using the [unsafe](../../language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="e6541-107">Aby uzyskać więcej informacji na temat wskaźników, zobacz [typy wskaźnika](pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="e6541-107">For more information about pointers, see [Pointer types](pointer-types.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6541-108">W środowisku uruchomieniowym języka wspólnego (CLR) kod niebezpieczny jest określany jako kod niemożliwy do zweryfikowania.</span><span class="sxs-lookup"><span data-stu-id="e6541-108">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="e6541-109">Kod niebezpieczny w języku C# nie musi być niebezpieczny; jest to tylko kod, którego bezpieczeństwo nie może być zweryfikowane przez środowisko CLR.</span><span class="sxs-lookup"><span data-stu-id="e6541-109">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="e6541-110">W związku z tym środowisko CLR wykona tylko niebezpieczny kod, jeśli znajduje się w w pełni zaufanym zestawie.</span><span class="sxs-lookup"><span data-stu-id="e6541-110">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="e6541-111">Jeśli używasz niebezpiecznego kodu, jest odpowiedzialny za upewnienie się, że Twój kod nie wprowadza zagrożeń bezpieczeństwa lub błędy wskaźników.</span><span class="sxs-lookup"><span data-stu-id="e6541-111">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="e6541-112">Przegląd niebezpiecznego kodu</span><span class="sxs-lookup"><span data-stu-id="e6541-112">Unsafe code overview</span></span>

<span data-ttu-id="e6541-113">Kod niebezpieczny ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="e6541-113">Unsafe code has the following properties:</span></span>

- <span data-ttu-id="e6541-114">Metody, typy i bloki kodu można definiować jako niebezpieczne.</span><span class="sxs-lookup"><span data-stu-id="e6541-114">Methods, types, and code blocks can be defined as unsafe.</span></span>

- <span data-ttu-id="e6541-115">W niektórych przypadkach niebezpieczny kod może zwiększyć wydajność aplikacji przez usunięcie kontroli granic tablicy.</span><span class="sxs-lookup"><span data-stu-id="e6541-115">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>

- <span data-ttu-id="e6541-116">Kod niebezpieczny jest wymagany po wywołaniu funkcji natywnych, które wymagają wskaźników.</span><span class="sxs-lookup"><span data-stu-id="e6541-116">Unsafe code is required when you call native functions that require pointers.</span></span>

- <span data-ttu-id="e6541-117">Użycie niebezpiecznego kodu wprowadza zagrożenia bezpieczeństwa i stabilności.</span><span class="sxs-lookup"><span data-stu-id="e6541-117">Using unsafe code introduces security and stability risks.</span></span>

- <span data-ttu-id="e6541-118">Kod, który zawiera niebezpieczne bloki, musi być skompilowany przy użyciu opcji [niebezpiecznego](../../language-reference/compiler-options/unsafe-compiler-option.md) kompilatora.</span><span class="sxs-lookup"><span data-stu-id="e6541-118">The code that contains unsafe blocks must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="e6541-119">Sekcje pokrewne</span><span class="sxs-lookup"><span data-stu-id="e6541-119">Related sections</span></span>

<span data-ttu-id="e6541-120">Aby uzyskać więcej informacji, zobacz:</span><span class="sxs-lookup"><span data-stu-id="e6541-120">For more information, see:</span></span>

- [<span data-ttu-id="e6541-121">Typy wskaźnika</span><span class="sxs-lookup"><span data-stu-id="e6541-121">Pointer types</span></span>](pointer-types.md)

- [<span data-ttu-id="e6541-122">Bufory o ustalonym rozmiarze</span><span class="sxs-lookup"><span data-stu-id="e6541-122">Fixed size buffers</span></span>](fixed-size-buffers.md)

## <a name="c-language-specification"></a><span data-ttu-id="e6541-123">specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="e6541-123">C# language specification</span></span>

<span data-ttu-id="e6541-124">Aby uzyskać więcej informacji, zobacz temat [niebezpieczny kod](~/_csharplang/spec/unsafe-code.md) w [specyfikacji języka C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="e6541-124">For more information, see the [Unsafe code](~/_csharplang/spec/unsafe-code.md) topic of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e6541-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e6541-125">See also</span></span>

- [<span data-ttu-id="e6541-126">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="e6541-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="e6541-127">niebezpieczne</span><span class="sxs-lookup"><span data-stu-id="e6541-127">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
