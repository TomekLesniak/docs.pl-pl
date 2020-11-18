---
title: Konwersja typów danych XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
ms.openlocfilehash: d7ee7447ab7a8be1bad0d087dba5fc2afaa878e8
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830977"
---
# <a name="conversion-of-xml-data-types"></a><span data-ttu-id="7b980-102">Konwersja typów danych XML</span><span class="sxs-lookup"><span data-stu-id="7b980-102">Conversion of XML Data Types</span></span>
<span data-ttu-id="7b980-103">Większość metod znalezionych w klasie **XmlConvert** służy do konwertowania danych między ciągami i formatami o jednoznacznie określonym typie.</span><span class="sxs-lookup"><span data-stu-id="7b980-103">The majority of the methods found in an **XmlConvert** class are used to convert data between strings and strongly typed formats.</span></span> <span data-ttu-id="7b980-104">Metody są niezależne od ustawień regionalnych.</span><span class="sxs-lookup"><span data-stu-id="7b980-104">Methods are locale independent.</span></span> <span data-ttu-id="7b980-105">Oznacza to, że nie uwzględniają żadnych ustawień regionalnych podczas konwersji.</span><span class="sxs-lookup"><span data-stu-id="7b980-105">This means that they do not take into account any locale settings when doing conversion.</span></span>  
  
## <a name="reading-string-as-types"></a><span data-ttu-id="7b980-106">Odczytywanie ciągu jako typów</span><span class="sxs-lookup"><span data-stu-id="7b980-106">Reading String as types</span></span>  
 <span data-ttu-id="7b980-107">Poniższy przykład odczytuje ciąg i konwertuje go na typ **DateTime** .</span><span class="sxs-lookup"><span data-stu-id="7b980-107">The following sample reads a string and converts it to a **DateTime** type.</span></span>  
  
 <span data-ttu-id="7b980-108">Uwzględniając następujące dane wejściowe XML:</span><span class="sxs-lookup"><span data-stu-id="7b980-108">Given the following XML input:</span></span>  
  
 <span data-ttu-id="7b980-109">**Dane wejściowe**</span><span class="sxs-lookup"><span data-stu-id="7b980-109">**Input**</span></span>  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 <span data-ttu-id="7b980-110">Ten kod konwertuje ciąg na format **DateTime** :</span><span class="sxs-lookup"><span data-stu-id="7b980-110">This code converts the string to the **DateTime** format:</span></span>  
  
```vb  
reader.ReadStartElement()  
Dim vDateTime As DateTime = XmlConvert.ToDateTime(reader.ReadString())  
Console.WriteLine(vDateTime)  
```  
  
```csharp  
reader.ReadStartElement();  
DateTime vDateTime = XmlConvert.ToDateTime(reader.ReadString());  
Console.WriteLine(vDateTime);  
```  
  
## <a name="writing-strings-as-types"></a><span data-ttu-id="7b980-111">Pisanie ciągów jako typów</span><span class="sxs-lookup"><span data-stu-id="7b980-111">Writing Strings as types</span></span>  
 <span data-ttu-id="7b980-112">Poniższy przykład odczytuje wartość **Int32** i konwertuje ją na ciąg.</span><span class="sxs-lookup"><span data-stu-id="7b980-112">The following sample reads an **Int32** and converts it to a string.</span></span>  
  
 <span data-ttu-id="7b980-113">Uwzględniając następujące dane wejściowe XML:</span><span class="sxs-lookup"><span data-stu-id="7b980-113">Given the following XML input:</span></span>  
  
 <span data-ttu-id="7b980-114">**Dane wejściowe**</span><span class="sxs-lookup"><span data-stu-id="7b980-114">**Input**</span></span>  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 <span data-ttu-id="7b980-115">Ten kod konwertuje wartość **Int32** na **ciąg**:</span><span class="sxs-lookup"><span data-stu-id="7b980-115">This code converts the **Int32** into a **String**:</span></span>  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b980-116">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="7b980-116">See also</span></span>

- [<span data-ttu-id="7b980-117">Konwertowanie ciągów na typy danych programu .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7b980-117">Converting Strings to .NET Framework Data Types</span></span>](converting-strings-to-dotnet-data-types.md)
- [<span data-ttu-id="7b980-118">Konwertowanie typów programu .NET Framework na ciągi</span><span class="sxs-lookup"><span data-stu-id="7b980-118">Converting .NET Framework Types to Strings</span></span>](converting-dotnet-types-to-strings.md)
