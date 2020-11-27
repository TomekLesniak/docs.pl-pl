---
title: 'Instrukcje: wykonywanie inicjalizacji obiektów z opóźnieniem'
description: Zobacz, jak wykonać inicjalizację z opóźnieniem obiektów przy użyciu klasy System. Opóźnion <T> . Inicjalizacja z opóźnieniem oznacza, że obiekty nie są tworzone, jeśli nigdy nie są potrzebne.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lazy initialization in .NET, how to perform
ms.assetid: 8cd68620-dcc3-4f20-8835-c728a6820e71
ms.openlocfilehash: 3de0d8ea8266931c2bcda5c59c1fef97602673d5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96278131"
---
# <a name="how-to-perform-lazy-initialization-of-objects"></a><span data-ttu-id="e56fc-104">Instrukcje: wykonywanie inicjalizacji obiektów z opóźnieniem</span><span class="sxs-lookup"><span data-stu-id="e56fc-104">How to: Perform Lazy Initialization of Objects</span></span>

<span data-ttu-id="e56fc-105"><xref:System.Lazy%601?displayProperty=nameWithType>Klasa upraszcza pracę wykonywaną podczas inicjowania z opóźnieniem i tworzenie wystąpienia obiektów.</span><span class="sxs-lookup"><span data-stu-id="e56fc-105">The <xref:System.Lazy%601?displayProperty=nameWithType> class simplifies the work of performing lazy initialization and instantiation of objects.</span></span> <span data-ttu-id="e56fc-106">Inicjując obiekty w sposób opóźniony, można uniknąć konieczności ich tworzenia w ogóle, jeśli nigdy nie są potrzebne, lub można odroczyć ich inicjalizację do momentu pierwszego dostępu do nich.</span><span class="sxs-lookup"><span data-stu-id="e56fc-106">By initializing objects in a lazy manner, you can avoid having to create them at all if they are never needed, or you can postpone their initialization until they are first accessed.</span></span> <span data-ttu-id="e56fc-107">Aby uzyskać więcej informacji, zobacz [Inicjalizacja z opóźnieniem](lazy-initialization.md).</span><span class="sxs-lookup"><span data-stu-id="e56fc-107">For more information, see [Lazy Initialization](lazy-initialization.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e56fc-108">Przykład</span><span class="sxs-lookup"><span data-stu-id="e56fc-108">Example</span></span>  

 <span data-ttu-id="e56fc-109">Poniższy przykład pokazuje, jak zainicjować wartość za pomocą <xref:System.Lazy%601> .</span><span class="sxs-lookup"><span data-stu-id="e56fc-109">The following example shows how to initialize a value with <xref:System.Lazy%601>.</span></span> <span data-ttu-id="e56fc-110">Załóżmy, że zmienna opóźniona może nie być wymagana, w zależności od innego kodu, który ustawia `someCondition` zmienną na wartość true lub false.</span><span class="sxs-lookup"><span data-stu-id="e56fc-110">Assume that the lazy variable might not be needed, depending on some other code that sets the `someCondition` variable to true or false.</span></span>  
  
```vb  
Dim someCondition As Boolean = False  
  
Sub Main()  
    'Initializing a value with a big computation, computed in parallel  
    Dim _data As Lazy(Of Integer) = New Lazy(Of Integer)(Function()  
                                                             Dim result =  
                                                                 ParallelEnumerable.Range(0, 1000).  
                                                                 Aggregate(Function(x, y)  
                                                                               Return x + y  
                                                                           End Function)  
                                                             Return result  
                                                         End Function)  
  
    '  do work that may or may not set someCondition to True  
    ' ...  
    '  Initialize the data only if needed  
    If someCondition = True Then  
  
        If (_data.Value > 100) Then  
  
            Console.WriteLine("Good data")  
        End If  
    End If  
End Sub  
```  
  
```csharp  
  static bool someCondition = false;
  //Initializing a value with a big computation, computed in parallel  
  Lazy<int> _data = new Lazy<int>(delegate  
  {  
      return ParallelEnumerable.Range(0, 1000).  
          Select(i => Compute(i)).Aggregate((x,y) => x + y);  
  }, LazyExecutionMode.EnsureSingleThreadSafeExecution);  
  
  // Do some work that may or may not set someCondition to true.  
  //  ...  
  // Initialize the data only if necessary  
  if (someCondition)  
  {  
    if (_data.Value > 100)  
      {  
          Console.WriteLine("Good data");  
      }  
  }  
```  
  
## <a name="example"></a><span data-ttu-id="e56fc-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="e56fc-111">Example</span></span>  

 <span data-ttu-id="e56fc-112">Poniższy przykład pokazuje, jak używać <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> klasy do inicjowania typu, który jest widoczny tylko dla bieżącego wystąpienia obiektu w bieżącym wątku.</span><span class="sxs-lookup"><span data-stu-id="e56fc-112">The following example shows how to use the <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> class to initialize a type that is visible only to the current object instance on the current thread.</span></span>  
  
 [!code-csharp[CDS#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds2.cs#13)]
 [!code-vb[CDS#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/lazyhowto.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="e56fc-113">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e56fc-113">See also</span></span>

- <xref:System.Threading.LazyInitializer?displayProperty=nameWithType>
- [<span data-ttu-id="e56fc-114">Inicjalizacja z opóźnieniem</span><span class="sxs-lookup"><span data-stu-id="e56fc-114">Lazy Initialization</span></span>](lazy-initialization.md)
