---
title: Jak pobrać skróconą wartość elementu (C#)
description: Dowiedz się, jak uzyskać skróconą wartość elementu. Skrócona wartość dotyczy tylko określonego elementu.
ms.date: 07/20/2015
ms.assetid: 924a2699-72f6-4be1-aaa6-de62f8ec73b9
ms.openlocfilehash: 597859e5b66606aa0cff9c1a475e79e6b66c39fc
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301583"
---
# <a name="how-to-retrieve-the-shallow-value-of-an-element-c"></a><span data-ttu-id="eae00-104">Jak pobrać skróconą wartość elementu (C#)</span><span class="sxs-lookup"><span data-stu-id="eae00-104">How to retrieve the shallow value of an element (C#)</span></span>
<span data-ttu-id="eae00-105">W tym temacie pokazano, jak uzyskać skróconą wartość elementu.</span><span class="sxs-lookup"><span data-stu-id="eae00-105">This topic shows how to get the shallow value of an element.</span></span> <span data-ttu-id="eae00-106">Wartość płytki to wartość tylko określonego elementu, a nie wartość Szczegółowa, która obejmuje wartości wszystkich elementów potomnych połączonych w jeden ciąg.</span><span class="sxs-lookup"><span data-stu-id="eae00-106">The shallow value is the value of the specific element only, as opposed to the deep value, which includes the values of all descendent elements concatenated into a single string.</span></span>  
  
 <span data-ttu-id="eae00-107">Po pobraniu wartości elementu przy użyciu funkcji rzutowania lub <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> właściwości, pobierana jest wartość Szczegółowa.</span><span class="sxs-lookup"><span data-stu-id="eae00-107">When you retrieve an element value by using either casting or the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property, you retrieve the deep value.</span></span> <span data-ttu-id="eae00-108">Aby pobrać wartość płytki, można użyć `ShallowValue` metody rozszerzenia, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="eae00-108">To retrieve the shallow value, you can use the `ShallowValue` extension method, as shown in the following example.</span></span> <span data-ttu-id="eae00-109">Pobieranie skróconej wartości jest przydatne, gdy chcesz wybrać elementy na podstawie ich zawartości.</span><span class="sxs-lookup"><span data-stu-id="eae00-109">Retrieving the shallow value is useful when you want to select elements based on their content.</span></span>  
  
 <span data-ttu-id="eae00-110">Poniższy przykład deklaruje metodę rozszerzenia, która pobiera płytki wartość elementu.</span><span class="sxs-lookup"><span data-stu-id="eae00-110">The following example declares an extension method that retrieves the shallow value of an element.</span></span> <span data-ttu-id="eae00-111">Następnie używa metody rozszerzającej w zapytaniu, aby wyświetlić listę wszystkich elementów, które zawierają obliczoną wartość.</span><span class="sxs-lookup"><span data-stu-id="eae00-111">It then uses the extension method in a query to list all elements that contain a calculated value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eae00-112">Przykład</span><span class="sxs-lookup"><span data-stu-id="eae00-112">Example</span></span>  
 <span data-ttu-id="eae00-113">Następujący plik tekstowy, Report.xml, jest źródłem dla tego przykładu.</span><span class="sxs-lookup"><span data-stu-id="eae00-113">The following text file, Report.xml, is the source for this example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<Report>  
  <Section>  
    <Heading>  
      <Column Name="CustomerId">=Customer.CustomerId.Heading</Column>  
      <Column Name="Name">=Customer.Name.Heading</Column>  
    </Heading>  
    <Detail>  
      <Column Name="CustomerId">=Customer.CustomerId</Column>  
      <Column Name="Name">=Customer.Name</Column>  
    </Detail>  
  </Section>  
</Report>  
```  
  
```csharp  
public static class MyExtensions  
{  
    public static string ShallowValue(this XElement xe)  
    {  
        return xe  
               .Nodes()  
               .OfType<XText>()  
               .Aggregate(new StringBuilder(),  
                          (s, c) => s.Append(c),  
                          s => s.ToString());  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement root = XElement.Load("Report.xml");  
  
        IEnumerable<XElement> query = from el in root.Descendants()  
                                      where el.ShallowValue().StartsWith("=")  
                                      select el;  
  
        foreach (var q in query)  
        {  
            Console.WriteLine("{0}{1}{2}",  
                q.Name.ToString().PadRight(8),  
                q.Attribute("Name").ToString().PadRight(20),  
                q.ShallowValue());  
        }  
    }  
}  
```  
  
 <span data-ttu-id="eae00-114">Ten przykład generuje następujące wyniki:</span><span class="sxs-lookup"><span data-stu-id="eae00-114">This example produces the following output:</span></span>  
  
```output  
Column  Name="CustomerId"   =Customer.CustomerId.Heading  
Column  Name="Name"         =Customer.Name.Heading  
Column  Name="CustomerId"   =Customer.CustomerId  
Column  Name="Name"         =Customer.Name  
```  
  
## <a name="see-also"></a><span data-ttu-id="eae00-115">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="eae00-115">See also</span></span>

- [<span data-ttu-id="eae00-116">Osie LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="eae00-116">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
