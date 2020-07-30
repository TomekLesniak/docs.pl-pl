---
title: Przechwytywanie wyjątku typu non-CLS
description: Dowiedz się, jak przechwytywać wyjątek niebędący specyfikacją CLS. Zobacz przykładowy kod i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions [C#], non-CLS
ms.assetid: db4630b3-5240-471a-b3a7-c7ff6ab31e8d
ms.openlocfilehash: 255de4cab9a72491eb3b9624d968539d432e0442
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302012"
---
# <a name="how-to-catch-a-non-cls-exception"></a><span data-ttu-id="23b44-104">Przechwytywanie wyjątku typu non-CLS</span><span class="sxs-lookup"><span data-stu-id="23b44-104">How to catch a non-CLS exception</span></span>
<span data-ttu-id="23b44-105">Niektóre języki .NET, w tym C++/CLI, umożliwiają obiektom zgłaszanie wyjątków, które nie pochodzą od <xref:System.Exception> .</span><span class="sxs-lookup"><span data-stu-id="23b44-105">Some .NET languages, including C++/CLI, allow objects to throw exceptions that do not derive from <xref:System.Exception>.</span></span> <span data-ttu-id="23b44-106">Takie wyjątki są nazywane *wyjątkami* nienależącymi do CLS lub *niewyjątkami*.</span><span class="sxs-lookup"><span data-stu-id="23b44-106">Such exceptions are called *non-CLS exceptions* or *non-Exceptions*.</span></span> <span data-ttu-id="23b44-107">W języku C# nie można zgłosić wyjątków nienależących do CLS, ale można je przechwycić na dwa sposoby:</span><span class="sxs-lookup"><span data-stu-id="23b44-107">In C# you cannot throw non-CLS exceptions, but you can catch them in two ways:</span></span>  
  
- <span data-ttu-id="23b44-108">Wewnątrz `catch (RuntimeWrappedException e)` bloku.</span><span class="sxs-lookup"><span data-stu-id="23b44-108">Within a `catch (RuntimeWrappedException e)` block.</span></span>
  
     <span data-ttu-id="23b44-109">Domyślnie zestaw Visual C# przechwytuje wyjątki niebędące CLS jako wyjątki otoczone.</span><span class="sxs-lookup"><span data-stu-id="23b44-109">By default, a Visual C# assembly catches non-CLS exceptions as wrapped exceptions.</span></span> <span data-ttu-id="23b44-110">Użyj tej metody, jeśli potrzebujesz dostępu do oryginalnego wyjątku, do którego można uzyskać dostęp za pomocą <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> właściwości.</span><span class="sxs-lookup"><span data-stu-id="23b44-110">Use this method if you need access to the original exception, which can be accessed through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="23b44-111">Procedura w dalszej części tego tematu wyjaśnia, jak przechwytywać wyjątki w ten sposób.</span><span class="sxs-lookup"><span data-stu-id="23b44-111">The procedure later in this topic explains how to catch exceptions in this manner.</span></span>  
  
- <span data-ttu-id="23b44-112">W obrębie ogólnego bloku catch (blok catch bez określonego typu wyjątku) jest umieszczany po wszystkich pozostałych `catch` blokach.</span><span class="sxs-lookup"><span data-stu-id="23b44-112">Within a general catch block (a catch block without an exception type specified) that is put after all other `catch` blocks.</span></span>
  
     <span data-ttu-id="23b44-113">Tej metody należy użyć, gdy chcesz wykonać pewne działania (takie jak zapis w pliku dziennika) w odpowiedzi na wyjątki nienależące do CLS i nie potrzebujesz dostępu do informacji o wyjątku.</span><span class="sxs-lookup"><span data-stu-id="23b44-113">Use this method when you want to perform some action (such as writing to a log file) in response to non-CLS exceptions, and you do not need access to the exception information.</span></span> <span data-ttu-id="23b44-114">Domyślnie środowisko uruchomieniowe języka wspólnego otacza wszystkie wyjątki.</span><span class="sxs-lookup"><span data-stu-id="23b44-114">By default the common language runtime wraps all exceptions.</span></span> <span data-ttu-id="23b44-115">Aby wyłączyć to zachowanie, Dodaj ten atrybut poziomu zestawu do kodu, zazwyczaj w pliku AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]` .</span><span class="sxs-lookup"><span data-stu-id="23b44-115">To disable this behavior, add this assembly-level attribute to your code, typically in the AssemblyInfo.cs file: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]`.</span></span>  
  
### <a name="to-catch-a-non-cls-exception"></a><span data-ttu-id="23b44-116">Aby przechwycić wyjątek niezgodny ze specyfikacją CLS</span><span class="sxs-lookup"><span data-stu-id="23b44-116">To catch a non-CLS exception</span></span>  
  
<span data-ttu-id="23b44-117">W `catch(RuntimeWrappedException e)` bloku Uzyskuj dostęp do oryginalnego wyjątku przez <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> Właściwość.</span><span class="sxs-lookup"><span data-stu-id="23b44-117">Within a `catch(RuntimeWrappedException e)` block, access the original exception through the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23b44-118">Przykład</span><span class="sxs-lookup"><span data-stu-id="23b44-118">Example</span></span>  
 <span data-ttu-id="23b44-119">Poniższy przykład pokazuje, jak przechwytywać wyjątek niezgodny ze specyfikacją CLS zgłoszoną przez bibliotekę klas zapisaną w języku C++/CLI.</span><span class="sxs-lookup"><span data-stu-id="23b44-119">The following example shows how to catch a non-CLS exception that was thrown from a class library written in C++/CLI.</span></span> <span data-ttu-id="23b44-120">Należy zauważyć, że w tym przykładzie kod klienta C# wie z wyprzedzeniem, że zwracany typ wyjątku to <xref:System.String?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="23b44-120">Note that in this example, the C# client code knows in advance that the exception type being thrown is a <xref:System.String?displayProperty=nameWithType>.</span></span> <span data-ttu-id="23b44-121">Można rzutować właściwość z powrotem na oryginalny typ, o ile <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> ten typ jest dostępny z kodu.</span><span class="sxs-lookup"><span data-stu-id="23b44-121">You can cast the <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> property back its original type as long as that type is accessible from your code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="23b44-122">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="23b44-122">See also</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeWrappedException>
- [<span data-ttu-id="23b44-123">Wyjątki i obsługa wyjątków</span><span class="sxs-lookup"><span data-stu-id="23b44-123">Exceptions and Exception Handling</span></span>](./index.md)
