---
title: Przechwytywanie wyjątku typu non-CLS
description: Dowiedz się, jak przechwytywać wyjątek niebędący specyfikacją CLS. Zobacz przykładowy kod i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
ms.openlocfilehash: db723cb1e29181e9462c5b423c66cdf8de659259
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178674"
---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="dc9c2-104">Przechwytywanie wyjątku typu non-CLS</span><span class="sxs-lookup"><span data-stu-id="dc9c2-104">How to catch a non-CLS exception</span></span>

<span data-ttu-id="dc9c2-105">Niektóre języki .NET, w tym C++/CLI, umożliwiają obiektom zgłaszanie wyjątków, które nie pochodzą od <xref:System.Exception> .</span><span class="sxs-lookup"><span data-stu-id="dc9c2-105">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="dc9c2-106">Takie wyjątki są nazywane *wyjątkami* nienależącymi do CLS lub *niewyjątkami*.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-106">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="dc9c2-107">W języku C# nie można zgłosić wyjątków nienależących do CLS, ale można je przechwycić na dwa sposoby:</span><span class="sxs-lookup"><span data-stu-id="dc9c2-107">In C# you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
- <span data-ttu-id="dc9c2-108">Wewnątrz `catch (RuntimeWrappedException e)` bloku.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-108">Within a `catch (RuntimeWrappedException e)` block.</span></span>
  
     <span data-ttu-id="dc9c2-109">Domyślnie zestaw Visual C# przechwytuje wyjątki niebędące CLS jako wyjątki otoczone.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-109">By default, a Visual C# assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="dc9c2-110">Użyj tej metody, jeśli potrzebujesz dostępu do oryginalnego wyjątku, do którego można uzyskać dostęp za pomocą <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-110">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="dc9c2-111">Procedura w dalszej części tego tematu wyjaśnia, jak przechwytywać wyjątki w ten sposób.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-111">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
- <span data-ttu-id="dc9c2-112">W obrębie ogólnego bloku catch (blok catch bez określonego typu wyjątku) jest umieszczany po wszystkich pozostałych `catch` blokach.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-112">Within a general catch block (a catch block without an exception type specified) that is put after all other `catch` blocks.</span></span>
  
     <span data-ttu-id="dc9c2-113">Tej metody należy użyć, gdy chcesz wykonać pewne działania (takie jak zapis w pliku dziennika) w odpowiedzi na wyjątki nienależące do CLS i nie potrzebujesz dostępu do informacji o wyjątku.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-113">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="dc9c2-114">Domyślnie środowisko uruchomieniowe języka wspólnego otacza wszystkie wyjątki.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-114">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="dc9c2-115">Aby wyłączyć to zachowanie, Dodaj ten atrybut poziomu zestawu do kodu, zazwyczaj w pliku AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]` .</span><span class="sxs-lookup"><span data-stu-id="dc9c2-115">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="dc9c2-116">Aby przechwycić wyjątek niezgodny ze specyfikacją CLS</span><span class="sxs-lookup"><span data-stu-id="dc9c2-116">To catch a non-CLS exception</span></span>  
  
<span data-ttu-id="dc9c2-117">W `catch(RuntimeWrappedException e)` bloku Uzyskuj dostęp do oryginalnego wyjątku przez <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> Właściwość.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-117">Within a `catch(RuntimeWrappedException e)` block, access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc9c2-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="dc9c2-118">Example</span></span>  

 <span data-ttu-id="dc9c2-119">Poniższy przykład pokazuje, jak przechwytywać wyjątek niezgodny ze specyfikacją CLS zgłoszoną przez bibliotekę klas zapisaną w języku C++/CLI.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-119">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLI.</span></span> <span data-ttu-id="dc9c2-120">Należy zauważyć, że w tym przykładzie kod klienta C# wie z wyprzedzeniem, że zwracany typ wyjątku to <xref:System.String?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="dc9c2-120">Note that in this example, the C# client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="dc9c2-121">Można rzutować właściwość z powrotem na oryginalny typ, o ile <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> ten typ jest dostępny z kodu.</span><span class="sxs-lookup"><span data-stu-id="dc9c2-121">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property back its original type as long as that type is accessible from your code.</span></span>  
  
```csharp
// Class library written in C++/CLI.
var myClass = new ThrowNonCLS.Class1();

try
{
    // throws gcnew System::String(  
    // "I do not derive from System.Exception!");  
    myClass.TestThrow();
}
catch (RuntimeWrappedException e)
{
    String s = e.WrappedException as String;
    if (s != null)
    {
        Console.WriteLine(s);
    }
}
```  
  
## <a name="see-also"></a><span data-ttu-id="dc9c2-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="dc9c2-122">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeWrappedException>
- [<span data-ttu-id="dc9c2-123">Wyjątki i obsługa wyjątków</span><span class="sxs-lookup"><span data-stu-id="dc9c2-123">Exceptions and Exception Handling</span></span>](./index.md)
