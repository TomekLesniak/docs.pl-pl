---
title: Konwertowanie ciągów na typy danych .NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
ms.openlocfilehash: 2eee3ff905473d8fd520929c0fe5abfb5d5c42da
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830964"
---
# <a name="convert-strings-to-net-data-types"></a><span data-ttu-id="0f18a-102">Konwertowanie ciągów na typy danych .NET</span><span class="sxs-lookup"><span data-stu-id="0f18a-102">Convert strings to .NET data types</span></span>

<span data-ttu-id="0f18a-103">Jeśli chcesz przekonwertować ciąg na typ danych .NET, użyj metody **XmlConvert** , która pasuje do wymagań aplikacji.</span><span class="sxs-lookup"><span data-stu-id="0f18a-103">If you want to convert a string to a .NET data type, use the **XmlConvert** method that fits the application requirements.</span></span> <span data-ttu-id="0f18a-104">Aby uzyskać listę wszystkich metod konwersji dostępnych w klasie **XmlConvert** , zobacz <xref:System.Xml.XmlConvert> .</span><span class="sxs-lookup"><span data-stu-id="0f18a-104">For a list of all conversion methods available in the **XmlConvert** class, see <xref:System.Xml.XmlConvert>.</span></span>  
  
 <span data-ttu-id="0f18a-105">Ciąg zwracany przez metodę **ToString** jest ciągiem wersji, która została przekazana.</span><span class="sxs-lookup"><span data-stu-id="0f18a-105">The string returned from the **ToString** method is a string version of the data that is passed in.</span></span> <span data-ttu-id="0f18a-106">Ponadto istnieje kilka typów platformy .NET, które konwertują się przy użyciu klasy **XmlConvert** , ale nie używają metod w klasie **System. Convert** .</span><span class="sxs-lookup"><span data-stu-id="0f18a-106">Additionally, there are several .NET types that convert using the **XmlConvert** class yet they do not use the methods in the **System.Convert** class.</span></span> <span data-ttu-id="0f18a-107">Klasa **XmlConvert** jest zgodna ze specyfikacją typu danych schematu XML (XSD) i ma typ danych, na który mapowanie **XmlConvert** może być mapowane.</span><span class="sxs-lookup"><span data-stu-id="0f18a-107">The **XmlConvert** class follows the XML Schema (XSD) data type specification and has a data type that the **XmlConvert** can map to.</span></span>  
  
 <span data-ttu-id="0f18a-108">Poniższa tabela zawiera listę typów danych .NET i typów ciągów, które są zwracane przy użyciu mapowania typu danych schematu XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="0f18a-108">The following table lists .NET data types and the string types that are returned using XML Schema (XSD) data type mapping.</span></span> <span data-ttu-id="0f18a-109">Te typy .NET nie mogą być przetwarzane przy użyciu **System. Convert**.</span><span class="sxs-lookup"><span data-stu-id="0f18a-109">These .NET types cannot be processed using **System.Convert**.</span></span>  
  
|<span data-ttu-id="0f18a-110">Typ .NET</span><span class="sxs-lookup"><span data-stu-id="0f18a-110">.NET type</span></span>|<span data-ttu-id="0f18a-111">Zwrócony ciąg</span><span class="sxs-lookup"><span data-stu-id="0f18a-111">String returned</span></span>|  
|-------------------------|---------------------|  
|<span data-ttu-id="0f18a-112">Boolean</span><span class="sxs-lookup"><span data-stu-id="0f18a-112">Boolean</span></span>|<span data-ttu-id="0f18a-113">"true", "false"</span><span class="sxs-lookup"><span data-stu-id="0f18a-113">"true", "false"</span></span>|  
|<span data-ttu-id="0f18a-114">Single. PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="0f18a-114">Single.PositiveInfinity</span></span>|<span data-ttu-id="0f18a-115">INF</span><span class="sxs-lookup"><span data-stu-id="0f18a-115">"INF"</span></span>|  
|<span data-ttu-id="0f18a-116">Single. NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="0f18a-116">Single.NegativeInfinity</span></span>|<span data-ttu-id="0f18a-117">"-INF"</span><span class="sxs-lookup"><span data-stu-id="0f18a-117">"-INF"</span></span>|  
|<span data-ttu-id="0f18a-118">Double. PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="0f18a-118">Double.PositiveInfinity</span></span>|<span data-ttu-id="0f18a-119">INF</span><span class="sxs-lookup"><span data-stu-id="0f18a-119">"INF"</span></span>|  
|<span data-ttu-id="0f18a-120">Double. NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="0f18a-120">Double.NegativeInfinity</span></span>|<span data-ttu-id="0f18a-121">"-INF"</span><span class="sxs-lookup"><span data-stu-id="0f18a-121">"-INF"</span></span>|  
|<span data-ttu-id="0f18a-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="0f18a-122">DateTime</span></span>|<span data-ttu-id="0f18a-123">Format to "RRRR-MM-DDTgg: mm: sszzzzzz" i jego podzestawy.</span><span class="sxs-lookup"><span data-stu-id="0f18a-123">Format is "yyyy-MM-ddTHH:mm:sszzzzzz" and its subsets.</span></span>|  
|<span data-ttu-id="0f18a-124">Zakres czasu</span><span class="sxs-lookup"><span data-stu-id="0f18a-124">Timespan</span></span>|<span data-ttu-id="0f18a-125">Format to PnYnMnTnHnMnS, czyli `P2Y10M15DT10H30M20S` okres 2 lat, 10 miesięcy, 15 dni, 10 godzin, 30 minut i 20 sekund.</span><span class="sxs-lookup"><span data-stu-id="0f18a-125">Format is PnYnMnTnHnMnS that is, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10 hours, 30 minutes, and 20 seconds.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="0f18a-126">W przypadku konwertowania dowolnego z typów .NET wymienionych w tabeli do ciągu przy użyciu metody **ToString** zwracany ciąg nie jest typem podstawowym, ale typ ciągu schematu XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="0f18a-126">If converting any of the .NET types listed in the table to a string using the **ToString** method, the returned string is not the base type, but the XML Schema (XSD) string type.</span></span>  
  
 <span data-ttu-id="0f18a-127">Typ wartości **DateTime** i **TimeSpan** różni się w tym, że element **DateTime** reprezentuje chwilę w czasie, podczas gdy obiekt **TimeSpan** reprezentuje przedział czasu.</span><span class="sxs-lookup"><span data-stu-id="0f18a-127">The **DateTime** and **Timespan** value type differs in that a **DateTime** represents an instant in time, whereas a **TimeSpan** represents a time interval.</span></span> <span data-ttu-id="0f18a-128">Formaty **DateTime** i **TimeSpan** są określone w specyfikacji typów danych schematu XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="0f18a-128">The **DateTime** and **Timespan** formats are specified in the XML Schema (XSD) data types specification.</span></span> <span data-ttu-id="0f18a-129">Przykład:</span><span class="sxs-lookup"><span data-stu-id="0f18a-129">For example:</span></span>  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim [date] As New DateTime(2001, 8, 4)  
writer.WriteElementString("Date", XmlConvert.ToString([date]))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
DateTime date = new DateTime (2001, 08, 04);  
writer.WriteElementString("Date", XmlConvert.ToString(date));  
```  
  
 <span data-ttu-id="0f18a-130">**Dane wyjściowe**</span><span class="sxs-lookup"><span data-stu-id="0f18a-130">**Output**</span></span>  
  
 <span data-ttu-id="0f18a-131">`<Date>2001-08-04T00:00:00</Date>`.</span><span class="sxs-lookup"><span data-stu-id="0f18a-131">`<Date>2001-08-04T00:00:00</Date>`.</span></span>  
  
 <span data-ttu-id="0f18a-132">Poniższy kod konwertuje liczbę całkowitą na ciąg:</span><span class="sxs-lookup"><span data-stu-id="0f18a-132">The following code converts an integer to a string:</span></span>  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim value As Int32 = 200  
writer.WriteElementString("Number", XmlConvert.ToString(value))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
Int32 value = 200;  
writer.WriteElementString("Number", XmlConvert.ToString(value));  
```  
  
 <span data-ttu-id="0f18a-133">**Dane wyjściowe**</span><span class="sxs-lookup"><span data-stu-id="0f18a-133">**Output**</span></span>  
  
 `<Number>200</Number>`  
  
 <span data-ttu-id="0f18a-134">Jeśli jednak konwertujesz ciąg na **wartość Boolean**, **Single** lub **Double**, zwracany typ platformy .NET nie jest taki sam jak typ zwracany podczas używania klasy **System. Convert** .</span><span class="sxs-lookup"><span data-stu-id="0f18a-134">However, if you are converting a string to **Boolean**, **Single**, or **Double**, the .NET type that's returned is not the same as the type returned when using the **System.Convert** class.</span></span>  
  
## <a name="string-to-boolean"></a><span data-ttu-id="0f18a-135">Ciąg do wartości logicznej</span><span class="sxs-lookup"><span data-stu-id="0f18a-135">String to Boolean</span></span>  
 <span data-ttu-id="0f18a-136">W poniższej tabeli przedstawiono typ, który jest generowany dla danego ciągu wejściowego podczas konwertowania ciągu na **wartość logiczną** przy użyciu metody **ToBoolean** .</span><span class="sxs-lookup"><span data-stu-id="0f18a-136">The following table shows what type is generated for the given input strings, when converting a string to **Boolean** using the **ToBoolean** method.</span></span>  
  
|<span data-ttu-id="0f18a-137">Prawidłowy parametr wejściowy ciągu</span><span class="sxs-lookup"><span data-stu-id="0f18a-137">Valid string input parameter</span></span>|<span data-ttu-id="0f18a-138">Typ danych wyjściowych platformy .NET</span><span class="sxs-lookup"><span data-stu-id="0f18a-138">.NET output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="0f18a-139">oznacza</span><span class="sxs-lookup"><span data-stu-id="0f18a-139">"true"</span></span>|<span data-ttu-id="0f18a-140">Wartość logiczna. true</span><span class="sxs-lookup"><span data-stu-id="0f18a-140">Boolean.True</span></span>|  
|<span data-ttu-id="0f18a-141">„1”</span><span class="sxs-lookup"><span data-stu-id="0f18a-141">"1"</span></span>|<span data-ttu-id="0f18a-142">Wartość logiczna. true</span><span class="sxs-lookup"><span data-stu-id="0f18a-142">Boolean.True</span></span>|  
|<span data-ttu-id="0f18a-143">false</span><span class="sxs-lookup"><span data-stu-id="0f18a-143">"false"</span></span>|<span data-ttu-id="0f18a-144">Wartość logiczna. false</span><span class="sxs-lookup"><span data-stu-id="0f18a-144">Boolean.False</span></span>|  
|<span data-ttu-id="0f18a-145">„0”</span><span class="sxs-lookup"><span data-stu-id="0f18a-145">"0"</span></span>|<span data-ttu-id="0f18a-146">Wartość logiczna. false</span><span class="sxs-lookup"><span data-stu-id="0f18a-146">Boolean.False</span></span>|  
  
 <span data-ttu-id="0f18a-147">Na przykład, uwzględniając następujący kod XML:</span><span class="sxs-lookup"><span data-stu-id="0f18a-147">For example, given the following XML:</span></span>  
  
 <span data-ttu-id="0f18a-148">**Dane wejściowe**</span><span class="sxs-lookup"><span data-stu-id="0f18a-148">**Input**</span></span>  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>
```  
  
 <span data-ttu-id="0f18a-149">Obie te wartości można zrozumieć przy użyciu poniższego kodu, a **bValue** to **System. Boolean. true**:</span><span class="sxs-lookup"><span data-stu-id="0f18a-149">Both can be understood by the following code, and **bvalue** is **System.Boolean.True**:</span></span>  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a><span data-ttu-id="0f18a-150">Ciąg do jednego</span><span class="sxs-lookup"><span data-stu-id="0f18a-150">String to Single</span></span>  
 <span data-ttu-id="0f18a-151">W poniższej tabeli przedstawiono typ, który jest generowany dla danych wejściowych ciągów, podczas konwertowania ciągu na **pojedynczy** przy użyciu metody **ToSingle —** .</span><span class="sxs-lookup"><span data-stu-id="0f18a-151">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToSingle** method.</span></span>  
  
|<span data-ttu-id="0f18a-152">Prawidłowy parametr wejściowy ciągu</span><span class="sxs-lookup"><span data-stu-id="0f18a-152">Valid string input parameter</span></span>|<span data-ttu-id="0f18a-153">Typ danych wyjściowych platformy .NET</span><span class="sxs-lookup"><span data-stu-id="0f18a-153">.NET output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="0f18a-154">INF</span><span class="sxs-lookup"><span data-stu-id="0f18a-154">"INF"</span></span>|<span data-ttu-id="0f18a-155">Single. PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="0f18a-155">Single.PositiveInfinity</span></span>|  
|<span data-ttu-id="0f18a-156">"-INF"</span><span class="sxs-lookup"><span data-stu-id="0f18a-156">"-INF"</span></span>|<span data-ttu-id="0f18a-157">Single. NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="0f18a-157">Single.NegativeInfinity</span></span>|  
  
## <a name="string-to-double"></a><span data-ttu-id="0f18a-158">Ciąg na Double</span><span class="sxs-lookup"><span data-stu-id="0f18a-158">String to Double</span></span>  
 <span data-ttu-id="0f18a-159">W poniższej tabeli przedstawiono typ, który jest generowany dla danych wejściowych ciągów, podczas konwertowania ciągu na **pojedynczy** przy użyciu metody **ToDouble —** .</span><span class="sxs-lookup"><span data-stu-id="0f18a-159">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToDouble** method.</span></span>  
  
|<span data-ttu-id="0f18a-160">Prawidłowy parametr wejściowy ciągu</span><span class="sxs-lookup"><span data-stu-id="0f18a-160">Valid string input parameter</span></span>|<span data-ttu-id="0f18a-161">Typ danych wyjściowych platformy .NET</span><span class="sxs-lookup"><span data-stu-id="0f18a-161">.NET output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="0f18a-162">INF</span><span class="sxs-lookup"><span data-stu-id="0f18a-162">"INF"</span></span>|<span data-ttu-id="0f18a-163">Double. PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="0f18a-163">Double.PositiveInfinity</span></span>|  
|<span data-ttu-id="0f18a-164">"-INF"</span><span class="sxs-lookup"><span data-stu-id="0f18a-164">"-INF"</span></span>|<span data-ttu-id="0f18a-165">Double. NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="0f18a-165">Double.NegativeInfinity</span></span>|  
  
 <span data-ttu-id="0f18a-166">Poniższy kod zapisuje `<Infinity>INF</Infinity>` :</span><span class="sxs-lookup"><span data-stu-id="0f18a-166">The following code writes `<Infinity>INF</Infinity>`:</span></span>  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f18a-167">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="0f18a-167">See also</span></span>

- [<span data-ttu-id="0f18a-168">Konwersja typów danych XML</span><span class="sxs-lookup"><span data-stu-id="0f18a-168">Conversion of XML Data Types</span></span>](conversion-of-xml-data-types.md)
- [<span data-ttu-id="0f18a-169">Konwertowanie typów .NET na ciągi</span><span class="sxs-lookup"><span data-stu-id="0f18a-169">Converting .NET Types to Strings</span></span>](converting-dotnet-types-to-strings.md)
