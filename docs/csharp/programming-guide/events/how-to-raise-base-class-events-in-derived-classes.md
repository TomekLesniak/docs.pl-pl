---
title: Jak wywoływać zdarzenia klasy podstawowej w klasach pochodnych — Przewodnik programowania w języku C#
description: Dowiedz się, jak wywoływać zdarzenia klasy podstawowej w klasach pochodnych. Zobacz przykładowy kod i Wyświetl dodatkowe dostępne zasoby.
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: b0b0a16a1fd165e437fc79ccacb20d406f5cff63
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302103"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="bccfc-104">Jak wywoływać zdarzenia klasy podstawowej w klasach pochodnych (Przewodnik programowania w języku C#)</span><span class="sxs-lookup"><span data-stu-id="bccfc-104">How to raise base class events in derived classes (C# Programming Guide)</span></span>
<span data-ttu-id="bccfc-105">Poniższy prosty przykład pokazuje standardowy sposób deklarowania zdarzeń w klasie bazowej, aby mogły być również wywoływane z klas pochodnych.</span><span class="sxs-lookup"><span data-stu-id="bccfc-105">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="bccfc-106">Ten wzorzec jest szeroko używany w Windows Forms klasach w bibliotekach klas .NET.</span><span class="sxs-lookup"><span data-stu-id="bccfc-106">This pattern is used extensively in Windows Forms classes in the .NET class libraries.</span></span>  
  
 <span data-ttu-id="bccfc-107">Podczas tworzenia klasy, która może być używana jako klasa bazowa dla innych klas, należy wziąć pod uwagę fakt, że zdarzenia są specjalnym typem delegata, który może być wywoływany tylko z klasy, która je zadeklaruje.</span><span class="sxs-lookup"><span data-stu-id="bccfc-107">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="bccfc-108">Klasy pochodne nie mogą bezpośrednio wywoływać zdarzeń, które są zadeklarowane w klasie bazowej.</span><span class="sxs-lookup"><span data-stu-id="bccfc-108">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="bccfc-109">Chociaż czasami można chcieć, aby zdarzenie, które może zostać wywołane tylko przez klasę bazową, w większości przypadków należy włączyć klasę pochodną, aby wywoływać zdarzenia klasy bazowej.</span><span class="sxs-lookup"><span data-stu-id="bccfc-109">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="bccfc-110">W tym celu można utworzyć chronioną metodę wywołującą w klasie bazowej, która otacza zdarzenie.</span><span class="sxs-lookup"><span data-stu-id="bccfc-110">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="bccfc-111">Wywołując lub zastępując tę metodę wywołującą, klasy pochodne mogą wywołać zdarzenie pośrednio.</span><span class="sxs-lookup"><span data-stu-id="bccfc-111">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bccfc-112">Nie deklaruj zdarzeń wirtualnych w klasie podstawowej i zastąp je w klasie pochodnej.</span><span class="sxs-lookup"><span data-stu-id="bccfc-112">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="bccfc-113">Kompilator języka C# nie obsługuje tych poprawnie i jest nieprzewidywalne, czy subskrybent zdarzenia pochodnego rzeczywiście zasubskrybuje zdarzenie klasy bazowej.</span><span class="sxs-lookup"><span data-stu-id="bccfc-113">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bccfc-114">Przykład</span><span class="sxs-lookup"><span data-stu-id="bccfc-114">Example</span></span>  
 [!code-csharp[csProgGuideEvents#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#1)]  
  
## <a name="see-also"></a><span data-ttu-id="bccfc-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="bccfc-115">See also</span></span>

- [<span data-ttu-id="bccfc-116">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="bccfc-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bccfc-117">Zdarzenia</span><span class="sxs-lookup"><span data-stu-id="bccfc-117">Events</span></span>](./index.md)
- [<span data-ttu-id="bccfc-118">Delegaci</span><span class="sxs-lookup"><span data-stu-id="bccfc-118">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="bccfc-119">Modyfikatory dostępu</span><span class="sxs-lookup"><span data-stu-id="bccfc-119">Access Modifiers</span></span>](../classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="bccfc-120">Tworzenie programów obsługi zdarzeń w formularzach systemu Windows</span><span class="sxs-lookup"><span data-stu-id="bccfc-120">Creating Event Handlers in Windows Forms</span></span>](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
