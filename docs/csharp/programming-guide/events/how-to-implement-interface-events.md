---
title: Jak zaimplementować zdarzenia interfejsu — Przewodnik programowania w języku C#
description: Dowiedz się, jak zaimplementować zdarzenia interfejsu w klasie. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- interfaces [C#], event implementation in classes
- events [C#], in interfaces
ms.assetid: 63527447-9535-4880-8e95-35e2075827df
ms.openlocfilehash: bd86aed4f8d8ac6e291c11fe441f87ac97593b03
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302129"
---
# <a name="how-to-implement-interface-events-c-programming-guide"></a><span data-ttu-id="207d9-104">Jak zaimplementować zdarzenia interfejsu (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="207d9-104">How to implement interface events (C# Programming Guide)</span></span>
<span data-ttu-id="207d9-105">[Interfejs](../../language-reference/keywords/interface.md) może zadeklarować [zdarzenie](../../language-reference/keywords/event.md).</span><span class="sxs-lookup"><span data-stu-id="207d9-105">An [interface](../../language-reference/keywords/interface.md) can declare an [event](../../language-reference/keywords/event.md).</span></span> <span data-ttu-id="207d9-106">Poniższy przykład pokazuje, jak zaimplementować zdarzenia interfejsu w klasie.</span><span class="sxs-lookup"><span data-stu-id="207d9-106">The following example shows how to implement interface events in a class.</span></span> <span data-ttu-id="207d9-107">Zasadniczo reguły są takie same, jak w przypadku implementowania dowolnej metody interfejsu lub właściwości.</span><span class="sxs-lookup"><span data-stu-id="207d9-107">Basically the rules are the same as when you implement any interface method or property.</span></span>  
  
## <a name="to-implement-interface-events-in-a-class"></a><span data-ttu-id="207d9-108">Aby zaimplementować zdarzenia interfejsu w klasie</span><span class="sxs-lookup"><span data-stu-id="207d9-108">To implement interface events in a class</span></span>  
  
<span data-ttu-id="207d9-109">Zadeklaruj zdarzenie w klasie, a następnie Wywołaj je w odpowiednich obszarach.</span><span class="sxs-lookup"><span data-stu-id="207d9-109">Declare the event in your class and then invoke it in the appropriate areas.</span></span>  
  
```csharp
namespace ImplementInterfaceEvents  
{  
    public interface IDrawingObject  
    {  
        event EventHandler ShapeChanged;  
    }  
    public class MyEventArgs : EventArgs
    {  
        // class members  
    }  
    public class Shape : IDrawingObject  
    {  
        public event EventHandler ShapeChanged;  
        void ChangeShape()  
        {  
            // Do something here before the event…  

            OnShapeChanged(new MyEventArgs(/*arguments*/));  

            // or do something here after the event.
        }  
        protected virtual void OnShapeChanged(MyEventArgs e)  
        {  
            ShapeChanged?.Invoke(this, e);  
        }  
    }  

}  
```  
  
## <a name="example"></a><span data-ttu-id="207d9-110">Przykład</span><span class="sxs-lookup"><span data-stu-id="207d9-110">Example</span></span>  
<span data-ttu-id="207d9-111">Poniższy przykład pokazuje, jak obsłużyć mniej typowe sytuacje, w których Klasa dziedziczy z co najmniej dwóch interfejsów, a każdy interfejs ma zdarzenie o tej samej nazwie.</span><span class="sxs-lookup"><span data-stu-id="207d9-111">The following example shows how to handle the less-common situation in which your class inherits from two or more interfaces and each interface has an event with the same name.</span></span> <span data-ttu-id="207d9-112">W takiej sytuacji należy podać jawną implementację interfejsu dla co najmniej jednego zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="207d9-112">In this situation, you must provide an explicit interface implementation for at least one of the events.</span></span> <span data-ttu-id="207d9-113">Podczas pisania jawnej implementacji interfejsu dla zdarzenia należy również napisać metody `add` `remove` dostępu do zdarzeń i.</span><span class="sxs-lookup"><span data-stu-id="207d9-113">When you write an explicit interface implementation for an event, you must also write the `add` and `remove` event accessors.</span></span> <span data-ttu-id="207d9-114">Zwykle są one dostarczane przez kompilator, ale w tym przypadku kompilator nie może ich udostępnić.</span><span class="sxs-lookup"><span data-stu-id="207d9-114">Normally these are provided by the compiler, but in this case the compiler cannot provide them.</span></span>  
  
<span data-ttu-id="207d9-115">Dostarczając własne metody dostępu, można określić, czy dwa zdarzenia są reprezentowane przez to samo zdarzenie w klasie, czy przez różne zdarzenia.</span><span class="sxs-lookup"><span data-stu-id="207d9-115">By providing your own accessors, you can specify whether the two events are represented by the same event in your class, or by different events.</span></span> <span data-ttu-id="207d9-116">Na przykład jeśli zdarzenia powinny być zgłaszane w różnych terminach zgodnie ze specyfikacją interfejsu, można skojarzyć każde zdarzenie z oddzielną implementacją w klasie.</span><span class="sxs-lookup"><span data-stu-id="207d9-116">For example, if the events should be raised at different times according to the interface specifications, you can associate each event with a separate implementation in your class.</span></span> <span data-ttu-id="207d9-117">W poniższym przykładzie Subskrybenci określają, które `OnDraw` zdarzenie będzie odbierane przez wyrzucanie odwołania kształtu do albo `IShape` `IDrawingObject` .</span><span class="sxs-lookup"><span data-stu-id="207d9-117">In the following example, subscribers determine which `OnDraw` event they will receive by casting the shape reference to either an `IShape` or an `IDrawingObject`.</span></span>  
  
 [!code-csharp[csProgGuideEvents#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#10)]
  
## <a name="see-also"></a><span data-ttu-id="207d9-118">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="207d9-118">See also</span></span>

- [<span data-ttu-id="207d9-119">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="207d9-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="207d9-120">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="207d9-120">Events</span></span>](./index.md)
- [<span data-ttu-id="207d9-121">Delegaci</span><span class="sxs-lookup"><span data-stu-id="207d9-121">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="207d9-122">Implementacja interfejsu jawnego</span><span class="sxs-lookup"><span data-stu-id="207d9-122">Explicit Interface Implementation</span></span>](../interfaces/explicit-interface-implementation.md)
- [<span data-ttu-id="207d9-123">Wywoływanie zdarzeń klasy podstawowej w klasach pochodnych</span><span class="sxs-lookup"><span data-stu-id="207d9-123">How to raise base class events in derived classes</span></span>](./how-to-raise-base-class-events-in-derived-classes.md)
