---
title: Konwertowanie ciągów na typy danych .NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
ms.openlocfilehash: 0cee7481f9c002f860bff7f12b8be0bb763dadb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701474"
---
# <a name="convert-strings-to-net-data-types"></a>Konwertowanie ciągów na typy danych .NET

Jeśli chcesz przekonwertować ciąg na typ danych .NET, użyj metody **XmlConvert** , która pasuje do wymagań aplikacji. Aby uzyskać listę wszystkich metod konwersji dostępnych w klasie **XmlConvert** , zobacz <xref:System.Xml.XmlConvert> .  
  
 Ciąg zwracany przez metodę **ToString** jest ciągiem wersji, która została przekazana. Ponadto istnieje kilka typów platformy .NET, które konwertują się przy użyciu klasy **XmlConvert** , ale nie używają metod w klasie **System. Convert** . Klasa **XmlConvert** jest zgodna ze specyfikacją typu danych schematu XML (XSD) i ma typ danych, na który mapowanie **XmlConvert** może być mapowane.  
  
 Poniższa tabela zawiera listę typów danych .NET i typów ciągów, które są zwracane przy użyciu mapowania typu danych schematu XML (XSD). Te typy .NET nie mogą być przetwarzane przy użyciu **System. Convert**.  
  
|Typ .NET|Zwrócony ciąg|  
|-------------------------|---------------------|  
|Wartość logiczna|"true", "false"|  
|Single. PositiveInfinity|INF|  
|Single. NegativeInfinity|"-INF"|  
|Double. PositiveInfinity|INF|  
|Double. NegativeInfinity|"-INF"|  
|DateTime|Format to "RRRR-MM-DDTgg: mm: sszzzzzz" i jego podzestawy.|  
|Zakres czasu|Format to PnYnMnTnHnMnS, czyli `P2Y10M15DT10H30M20S` okres 2 lat, 10 miesięcy, 15 dni, 10 godzin, 30 minut i 20 sekund.|  
  
> [!NOTE]
> W przypadku konwertowania dowolnego z typów .NET wymienionych w tabeli do ciągu przy użyciu metody **ToString** zwracany ciąg nie jest typem podstawowym, ale typ ciągu schematu XML (XSD).  
  
 Typ wartości **DateTime** i **TimeSpan** różni się w tym, że element **DateTime** reprezentuje chwilę w czasie, podczas gdy obiekt **TimeSpan** reprezentuje przedział czasu. Formaty **DateTime** i **TimeSpan** są określone w specyfikacji typów danych schematu XML (XSD). Na przykład:  
  
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
  
 **Dane wyjściowe**  
  
 `<Date>2001-08-04T00:00:00</Date>`.  
  
 Poniższy kod konwertuje liczbę całkowitą na ciąg:  
  
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
  
 **Dane wyjściowe**  
  
 `<Number>200</Number>`  
  
 Jeśli jednak konwertujesz ciąg na **wartość Boolean**, **Single** lub **Double**, zwracany typ platformy .NET nie jest taki sam jak typ zwracany podczas używania klasy **System. Convert** .  
  
## <a name="string-to-boolean"></a>Ciąg do wartości logicznej  

 W poniższej tabeli przedstawiono typ, który jest generowany dla danego ciągu wejściowego podczas konwertowania ciągu na **wartość logiczną** przy użyciu metody **ToBoolean** .  
  
|Prawidłowy parametr wejściowy ciągu|Typ danych wyjściowych platformy .NET|  
|----------------------------------|--------------------------------|  
|oznacza|Wartość logiczna. true|  
|„1”|Wartość logiczna. true|  
|false|Wartość logiczna. false|  
|„0”|Wartość logiczna. false|  
  
 Na przykład, uwzględniając następujący kod XML:  
  
 **Dane wejściowe**  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>
```  
  
 Obie te wartości można zrozumieć przy użyciu poniższego kodu, a **bValue** to **System. Boolean. true**:  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a>Ciąg do jednego  

 W poniższej tabeli przedstawiono typ, który jest generowany dla danych wejściowych ciągów, podczas konwertowania ciągu na **pojedynczy** przy użyciu metody **ToSingle —** .  
  
|Prawidłowy parametr wejściowy ciągu|Typ danych wyjściowych platformy .NET|  
|----------------------------------|--------------------------------|  
|INF|Single. PositiveInfinity|  
|"-INF"|Single. NegativeInfinity|  
  
## <a name="string-to-double"></a>Ciąg na Double  

 W poniższej tabeli przedstawiono typ, który jest generowany dla danych wejściowych ciągów, podczas konwertowania ciągu na **pojedynczy** przy użyciu metody **ToDouble —** .  
  
|Prawidłowy parametr wejściowy ciągu|Typ danych wyjściowych platformy .NET|  
|----------------------------------|--------------------------------|  
|INF|Double. PositiveInfinity|  
|"-INF"|Double. NegativeInfinity|  
  
 Poniższy kod zapisuje `<Infinity>INF</Infinity>` :  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a>Zobacz także

- [Konwersja typów danych XML](conversion-of-xml-data-types.md)
- [Konwertowanie typów .NET na ciągi](converting-dotnet-types-to-strings.md)
