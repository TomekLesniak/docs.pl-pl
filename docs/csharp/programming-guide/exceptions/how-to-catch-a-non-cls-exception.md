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
# <a name="how-to-catch-a-non-cls-exception"></a>Przechwytywanie wyjątku typu non-CLS
Niektóre języki .NET, w tym C++/CLI, umożliwiają obiektom zgłaszanie wyjątków, które nie pochodzą od <xref:System.Exception> . Takie wyjątki są nazywane *wyjątkami* nienależącymi do CLS lub *niewyjątkami*. W języku C# nie można zgłosić wyjątków nienależących do CLS, ale można je przechwycić na dwa sposoby:  
  
- Wewnątrz `catch (RuntimeWrappedException e)` bloku.
  
     Domyślnie zestaw Visual C# przechwytuje wyjątki niebędące CLS jako wyjątki otoczone. Użyj tej metody, jeśli potrzebujesz dostępu do oryginalnego wyjątku, do którego można uzyskać dostęp za pomocą <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> właściwości. Procedura w dalszej części tego tematu wyjaśnia, jak przechwytywać wyjątki w ten sposób.  
  
- W obrębie ogólnego bloku catch (blok catch bez określonego typu wyjątku) jest umieszczany po wszystkich pozostałych `catch` blokach.
  
     Tej metody należy użyć, gdy chcesz wykonać pewne działania (takie jak zapis w pliku dziennika) w odpowiedzi na wyjątki nienależące do CLS i nie potrzebujesz dostępu do informacji o wyjątku. Domyślnie środowisko uruchomieniowe języka wspólnego otacza wszystkie wyjątki. Aby wyłączyć to zachowanie, Dodaj ten atrybut poziomu zestawu do kodu, zazwyczaj w pliku AssemblyInfo.cs: `[assembly: RuntimeCompatibilityAttribute(WrapNonExceptionThrows = false)]` .  
  
### <a name="to-catch-a-non-cls-exception"></a>Aby przechwycić wyjątek niezgodny ze specyfikacją CLS  
  
W `catch(RuntimeWrappedException e)` bloku Uzyskuj dostęp do oryginalnego wyjątku przez <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> Właściwość.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład pokazuje, jak przechwytywać wyjątek niezgodny ze specyfikacją CLS zgłoszoną przez bibliotekę klas zapisaną w języku C++/CLI. Należy zauważyć, że w tym przykładzie kod klienta C# wie z wyprzedzeniem, że zwracany typ wyjątku to <xref:System.String?displayProperty=nameWithType> . Można rzutować właściwość z powrotem na oryginalny typ, o ile <xref:System.Runtime.CompilerServices.RuntimeWrappedException.WrappedException%2A?displayProperty=nameWithType> ten typ jest dostępny z kodu.  
  
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
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Runtime.CompilerServices.RuntimeWrappedException>
- [Wyjątki i obsługa wyjątków](./index.md)
