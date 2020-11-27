---
title: Wyrażenia — WF
ms.date: 03/30/2017
ms.assetid: c42341a9-43a1-462c-bffb-c5de004aa428
ms.openlocfilehash: 1dca2090dda981fabb27d3e5f2dff78051d7af24
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280224"
---
# <a name="expressions"></a><span data-ttu-id="32cd0-102">Wyrażenia</span><span class="sxs-lookup"><span data-stu-id="32cd0-102">Expressions</span></span>

<span data-ttu-id="32cd0-103">Wyrażenie Windows Workflow Foundation (WF) to wszelkie działania zwracające wynik.</span><span class="sxs-lookup"><span data-stu-id="32cd0-103">A Windows Workflow Foundation (WF) expression is any activity that returns a result.</span></span> <span data-ttu-id="32cd0-104">Wszystkie działania wyrażeń są wyprowadzane pośrednio z <xref:System.Activities.Activity%601> , która zawiera <xref:System.Activities.OutArgument> Właściwość o nazwie <xref:System.Activities.Activity%601.Result%2A> jako wartość zwracana działania.</span><span class="sxs-lookup"><span data-stu-id="32cd0-104">All expression activities derive indirectly from <xref:System.Activities.Activity%601>, which contains an <xref:System.Activities.OutArgument> property named <xref:System.Activities.Activity%601.Result%2A> as the activity’s return value.</span></span> [!INCLUDE[wf1](../../../includes/wf1-md.md)] <span data-ttu-id="32cd0-105">jest dostarczany z szerokim zakresem działań związanych z wyrażeniami prostymi, <xref:System.Activities.Expressions.VariableValue%601> <xref:System.Activities.Expressions.VariableReference%601> takimi jak i, które zapewniają dostęp do zmiennej pojedynczego przepływu pracy przez działania operatorów, do złożonych działań, takich jak <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> i <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> oferujących dostęp do pełnej gamy Visual Basic języka w celu uzyskania wyniku.</span><span class="sxs-lookup"><span data-stu-id="32cd0-105">ships with a wide range of expression activities from simple ones like <xref:System.Activities.Expressions.VariableValue%601> and <xref:System.Activities.Expressions.VariableReference%601>, which provide access to single workflow variable through operator activities, to complex activities such as <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> and <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> that offer access to the full breadth of Visual Basic language to produce the result.</span></span> <span data-ttu-id="32cd0-106">Dodatkowe działania dotyczące wyrażeń można tworzyć poprzez wyprowadzanie z <xref:System.Activities.CodeActivity%601> lub <xref:System.Activities.NativeActivity%601> .</span><span class="sxs-lookup"><span data-stu-id="32cd0-106">Additional expression activities can be created by deriving from <xref:System.Activities.CodeActivity%601> or <xref:System.Activities.NativeActivity%601>.</span></span>

## <a name="using-expressions"></a><span data-ttu-id="32cd0-107">Używanie wyrażeń</span><span class="sxs-lookup"><span data-stu-id="32cd0-107">Using Expressions</span></span>

 <span data-ttu-id="32cd0-108">Projektant przepływu pracy używa <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> i <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> dla wszystkich wyrażeń w projektach Visual Basic i <xref:Microsoft.CSharp.Activities.CSharpValue%601> i <xref:Microsoft.CSharp.Activities.CSharpReference%601> dla wyrażeń w projektach przepływu pracy w języku C#.</span><span class="sxs-lookup"><span data-stu-id="32cd0-108">Workflow designer uses <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> and <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> for all expressions in Visual Basic projects, and <xref:Microsoft.CSharp.Activities.CSharpValue%601> and <xref:Microsoft.CSharp.Activities.CSharpReference%601> for expressions in C# workflow projects.</span></span>

> [!NOTE]
> <span data-ttu-id="32cd0-109">Obsługa wyrażeń języka C# w projektach przepływu pracy została wprowadzona w .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="32cd0-109">Support for C# expressions in workflow projects was introduced in .NET Framework 4.5.</span></span> <span data-ttu-id="32cd0-110">Aby uzyskać więcej informacji, zobacz [wyrażenia języka C#](csharp-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="32cd0-110">For more information, see [C# Expressions](csharp-expressions.md).</span></span>

 <span data-ttu-id="32cd0-111">Przepływy pracy utworzone przez projektanta są zapisywane w języku XAML, gdzie wyrażenia są ujęte w nawiasy kwadratowe, jak w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="32cd0-111">Workflows produced by designer are saved in XAML, where expressions appear enclosed in square brackets, as in the following example.</span></span>

```xml
<Sequence xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
  <Sequence.Variables>
    <Variable x:TypeArguments="x:Int32" Default="1" Name="a" />
    <Variable x:TypeArguments="x:Int32" Default="2" Name="b" />
    <Variable x:TypeArguments="x:Int32" Default="3" Name="c" />
    <Variable x:TypeArguments="x:Int32" Default="0" Name="r" />
  </Sequence.Variables>
  <Assign>
    <Assign.To>
      <OutArgument x:TypeArguments="x:Int32">[r]</OutArgument>
    </Assign.To>
    <Assign.Value>
      <InArgument x:TypeArguments="x:Int32">[a + b + c]</InArgument>
    </Assign.Value>
  </Assign>
</Sequence>
```

 <span data-ttu-id="32cd0-112">Podczas definiowania przepływu pracy w kodzie, można użyć dowolnego działania wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="32cd0-112">When defining a workflow in code, any expression activities can be used.</span></span> <span data-ttu-id="32cd0-113">W poniższym przykładzie pokazano sposób użycia kompozycji działań operatora w celu dodania trzech liczb:</span><span class="sxs-lookup"><span data-stu-id="32cd0-113">The following example shows the usage of a composition of operator activities to add three numbers:</span></span>

```csharp
Variable<int> a = new Variable<int>("a", 1);
Variable<int> b = new Variable<int>("b", 2);
Variable<int> c = new Variable<int>("c", 3);
Variable<int> r = new Variable<int>("r", 0);

Sequence w = new Sequence
{
    Variables = { a, b, c, r },
    Activities =
    {
        new Assign {
            To = new OutArgument<int>(r),
            Value = new InArgument<int> {
                Expression = new Add<int, int, int> {
                    Left = new Add<int, int, int> {
                        Left = new InArgument<int>(a),
                        Right = new InArgument<int>(b)
                    },
                    Right = new InArgument<int>(c)
                }
            }
        }
    }
};
```

 <span data-ttu-id="32cd0-114">Ten sam przepływ pracy można wyrazić bardziej kompaktowo, używając wyrażeń lambda języka C#, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="32cd0-114">The same workflow can be expressed more compactly by using C# lambda expressions, as shown in the following example:</span></span>
  
```csharp
Variable<int> a = new Variable<int>("a", 1);
Variable<int> b = new Variable<int>("b", 2);
Variable<int> c = new Variable<int>("c", 3);
Variable<int> r = new Variable<int>("r", 0);

Sequence w = new Sequence
{
    Variables = { a, b, c, r },
    Activities =
    {
        new Assign {
            To = new OutArgument<int>(r),
            Value = new InArgument<int>((ctx) => a.Get(ctx) + b.Get(ctx) + c.Get(ctx))
        }
    }
};
```

## <a name="extending-available-expressions-with-custom-expression-activities"></a><span data-ttu-id="32cd0-115">Rozszerzanie dostępnych wyrażeń z niestandardowymi działaniami wyrażeń</span><span class="sxs-lookup"><span data-stu-id="32cd0-115">Extending Available Expressions with Custom Expression Activities</span></span>

 <span data-ttu-id="32cd0-116">Wyrażenia w programie [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] mają rozszerzalny Zezwalanie na tworzenie dodatkowych działań wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="32cd0-116">Expressions in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] are extensible allowing for additional expression activities to be created.</span></span> <span data-ttu-id="32cd0-117">Poniższy przykład pokazuje działanie zwracające sumę trzech wartości całkowitych.</span><span class="sxs-lookup"><span data-stu-id="32cd0-117">The following example shows an activity that returns a sum of three integer values.</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Activities;

namespace ExpressionsDemo
{
    public sealed class AddThreeValues : CodeActivity<int>
    {
        public InArgument<int> Value1 { get; set; }
        public InArgument<int> Value2 { get; set; }
        public InArgument<int> Value3 { get; set; }

        protected override int Execute(CodeActivityContext context)
        {
            return Value1.Get(context) +
                   Value2.Get(context) +
                   Value3.Get(context);
        }
    }
}
```

 <span data-ttu-id="32cd0-118">Przy użyciu tego nowego działania można ponownie napisać poprzedni przepływ pracy, który dodał trzy wartości, jak pokazano w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="32cd0-118">With this new activity you can rewrite the previous workflow that added three values as shown in the following example:</span></span>

```csharp
Variable<int> a = new Variable<int>("a", 1);
Variable<int> b = new Variable<int>("b", 2);
Variable<int> c = new Variable<int>("c", 3);
Variable<int> r = new Variable<int>("r", 0);

Sequence w = new Sequence
{
    Variables = { a, b, c, r },
    Activities =
    {
        new Assign {
            To = new OutArgument<int>(r),
            Value = new InArgument<int> {
                Expression = new AddThreeValues() {
                    Value1 = new InArgument<int>(a),
                    Value2 = new InArgument<int>(b),
                    Value3 = new InArgument<int>(c)
                }
            }
        }
    }
};
```

 <span data-ttu-id="32cd0-119">Aby uzyskać więcej informacji na temat używania wyrażeń w kodzie, zobacz [Tworzenie przepływów pracy, działań i wyrażeń przy użyciu kodu](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span><span class="sxs-lookup"><span data-stu-id="32cd0-119">For more information about using expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>
