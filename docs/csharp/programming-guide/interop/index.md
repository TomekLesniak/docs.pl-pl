---
title: Współdziałanie — Przewodnik programowania w języku C#
description: Współdziałanie obsługuje kod niezarządzany obok kodu, który jest uruchamiany w środowisku uruchomieniowym języka wspólnego. Użyj tych zasobów, aby zrozumieć opcje międzyoperacyjności.
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
ms.openlocfilehash: 84cdc16ccda7a5c629a90b0752071a98de81a9b4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178479"
---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="43be3-104">Współdziałanie (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="43be3-104">Interoperability (C# Programming Guide)</span></span>

<span data-ttu-id="43be3-105">Współdziałanie pozwala zachować istniejące inwestycje w kodzie niezarządzanym i korzystać z nich.</span><span class="sxs-lookup"><span data-stu-id="43be3-105">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="43be3-106">Kod, który jest uruchamiany pod kontrolą środowiska uruchomieniowego języka wspólnego (CLR) jest nazywany *kodem zarządzanym*, a kod, który jest URUCHAMIANY poza środowiskiem CLR, jest nazywany *kodem niezarządzanym*.</span><span class="sxs-lookup"><span data-stu-id="43be3-106">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="43be3-107">Przykłady kodu niezarządzanego modelu COM, COM+, C++, Components, ActiveX i Microsoft Windows API.</span><span class="sxs-lookup"><span data-stu-id="43be3-107">COM, COM+, C++ components, ActiveX components, and Microsoft Windows API are examples of unmanaged code.</span></span>  
  
<span data-ttu-id="43be3-108">Platforma .NET umożliwia współdziałanie z kodem niezarządzanym za pomocą usług wywołania platformy, <xref:System.Runtime.InteropServices> przestrzeni nazw, współdziałania C++ i współdziałania modelu COM (międzyoperacyjna com)</span><span class="sxs-lookup"><span data-stu-id="43be3-108">.NET enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="43be3-109">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="43be3-109">In This Section</span></span>  

 [<span data-ttu-id="43be3-110">Przegląd współdziałania</span><span class="sxs-lookup"><span data-stu-id="43be3-110">Interoperability Overview</span></span>](./interoperability-overview.md)  
 <span data-ttu-id="43be3-111">Opisuje metody współpracy między kodem zarządzanym C# i niezarządzanym kodem.</span><span class="sxs-lookup"><span data-stu-id="43be3-111">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="43be3-112">Uzyskiwanie dostępu do obiektów międzyoperacyjności pakietu Office za pomocą funkcji języka C#</span><span class="sxs-lookup"><span data-stu-id="43be3-112">How to access Office interop objects by using C# features</span></span>](./how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="43be3-113">Zawiera opis funkcji wprowadzonych w Visual C# w celu ułatwienia programowania pakietu Office.</span><span class="sxs-lookup"><span data-stu-id="43be3-113">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="43be3-114">Używanie właściwości indeksowanych w programowaniu usługi międzyoperacyjnej modelu COM</span><span class="sxs-lookup"><span data-stu-id="43be3-114">How to use indexed properties in COM interop programming</span></span>](./how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="43be3-115">Opisuje sposób używania właściwości indeksowanych w celu uzyskania dostępu do właściwości COM, które mają parametry.</span><span class="sxs-lookup"><span data-stu-id="43be3-115">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="43be3-116">Używanie wywołania platformy do odtwarzania pliku WAV</span><span class="sxs-lookup"><span data-stu-id="43be3-116">How to use platform invoke to play a WAV file</span></span>](./how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="43be3-117">Opisuje, jak używać usług wywołania platformy do odtwarzania pliku dźwiękowego WAV w systemie operacyjnym Windows.</span><span class="sxs-lookup"><span data-stu-id="43be3-117">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 [<span data-ttu-id="43be3-118">Przewodnik: Programowanie Office</span><span class="sxs-lookup"><span data-stu-id="43be3-118">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)  
 <span data-ttu-id="43be3-119">Pokazuje, jak utworzyć skoroszyt programu Excel i dokument programu Word, który zawiera link do skoroszytu.</span><span class="sxs-lookup"><span data-stu-id="43be3-119">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="43be3-120">Klasa COM — Przykład</span><span class="sxs-lookup"><span data-stu-id="43be3-120">Example COM Class</span></span>](./example-com-class.md)  
 <span data-ttu-id="43be3-121">Pokazuje, jak uwidocznić klasę języka C# jako obiekt COM.</span><span class="sxs-lookup"><span data-stu-id="43be3-121">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="43be3-122">Specyfikacja języka C#</span><span class="sxs-lookup"><span data-stu-id="43be3-122">C# Language Specification</span></span>  

<span data-ttu-id="43be3-123">Aby uzyskać więcej informacji, zobacz [podstawowe pojęcia](~/_csharplang/spec/unsafe-code.md) w [specyfikacji języka C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="43be3-123">For more information, see [Basic concepts](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="43be3-124">Specyfikacja języka jest ostatecznym źródłem informacji o składni i użyciu języka C#.</span><span class="sxs-lookup"><span data-stu-id="43be3-124">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="43be3-125">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="43be3-125">See also</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>
- [<span data-ttu-id="43be3-126">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="43be3-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="43be3-127">Współdziałanie z kodem niezarządzanym</span><span class="sxs-lookup"><span data-stu-id="43be3-127">Interoperating with Unmanaged Code</span></span>](../../../framework/interop/index.md)
- [<span data-ttu-id="43be3-128">Przewodnik: Programowanie Office</span><span class="sxs-lookup"><span data-stu-id="43be3-128">Walkthrough: Office Programming</span></span>](./walkthrough-office-programming.md)
