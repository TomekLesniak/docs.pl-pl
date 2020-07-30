---
title: Jak odczytywać dane obiektów z pliku XML (C#)
description: Ten przykład w języku C# odczytuje dane obiektu, które wcześniej Zapisano do pliku XML przy użyciu klasy XmlSerializer.
ms.date: 07/20/2015
ms.assetid: 6ad60d96-a4d9-48e6-a8b0-d7f6f803cafa
ms.openlocfilehash: 525a93812279756b3802d43d85bb5e61d8f7415e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302792"
---
# <a name="how-to-read-object-data-from-an-xml-file-c"></a><span data-ttu-id="10bfb-103">Jak odczytywać dane obiektów z pliku XML (C#)</span><span class="sxs-lookup"><span data-stu-id="10bfb-103">How to read object data from an XML file (C#)</span></span>
<span data-ttu-id="10bfb-104">Ten przykład odczytuje dane obiektu, które wcześniej Zapisano do pliku XML przy użyciu <xref:System.Xml.Serialization.XmlSerializer> klasy.</span><span class="sxs-lookup"><span data-stu-id="10bfb-104">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10bfb-105">Przykład</span><span class="sxs-lookup"><span data-stu-id="10bfb-105">Example</span></span>  
  
```csharp  
public class Book  
{  
    public String title;  
}
  
public void ReadXML()  
{  
    // First write something so that there is something to read ...  
    var b = new Book { title = "Serialization Overview" };  
    var writer = new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    var wfile = new System.IO.StreamWriter(@"c:\temp\SerializationOverview.xml");  
    writer.Serialize(wfile, b);  
    wfile.Close();  
  
    // Now we can read the serialized book ...  
    System.Xml.Serialization.XmlSerializer reader =
        new System.Xml.Serialization.XmlSerializer(typeof(Book));  
    System.IO.StreamReader file = new System.IO.StreamReader(  
        @"c:\temp\SerializationOverview.xml");  
    Book overview =  (Book)reader.Deserialize(file);  
    file.Close();  
  
    Console.WriteLine(overview.title);  
  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="10bfb-106">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="10bfb-106">Compiling the Code</span></span>  
<span data-ttu-id="10bfb-107">Zastąp nazwę pliku "c:\temp\SerializationOverview.xml" nazwą pliku zawierającego serializowane dane.</span><span class="sxs-lookup"><span data-stu-id="10bfb-107">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="10bfb-108">Aby uzyskać więcej informacji na temat serializowania danych, zobacz [jak pisać dane obiektów do pliku XML (C#)](./how-to-write-object-data-to-an-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="10bfb-108">For more information about serializing data, see [How to write object data to an XML file (C#)](./how-to-write-object-data-to-an-xml-file.md).</span></span>
  
 <span data-ttu-id="10bfb-109">Klasa musi mieć Konstruktor publiczny bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="10bfb-109">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="10bfb-110">Tylko publiczne właściwości i pola są deserializowane.</span><span class="sxs-lookup"><span data-stu-id="10bfb-110">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="10bfb-111">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="10bfb-111">Robust Programming</span></span>  
 <span data-ttu-id="10bfb-112">Następujące warunki mogą spowodować wyjątek:</span><span class="sxs-lookup"><span data-stu-id="10bfb-112">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="10bfb-113">Serializowana Klasa nie ma publicznego konstruktora bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="10bfb-113">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="10bfb-114">Dane w pliku nie reprezentują danych z klasy, która ma zostać poddana deserializacji.</span><span class="sxs-lookup"><span data-stu-id="10bfb-114">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
- <span data-ttu-id="10bfb-115">Plik nie istnieje ( <xref:System.IO.IOException> ).</span><span class="sxs-lookup"><span data-stu-id="10bfb-115">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="10bfb-116">Zabezpieczenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="10bfb-116">.NET Security</span></span>  
 <span data-ttu-id="10bfb-117">Zawsze Weryfikuj dane wejściowe i nigdy nie wykonuj deserializacji danych z niezaufanego źródła.</span><span class="sxs-lookup"><span data-stu-id="10bfb-117">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="10bfb-118">Nowo utworzony obiekt jest uruchamiany na komputerze lokalnym z uprawnieniami kodu, który został deserializowany.</span><span class="sxs-lookup"><span data-stu-id="10bfb-118">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="10bfb-119">Sprawdź wszystkie dane wejściowe, zanim użyjesz danych w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="10bfb-119">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10bfb-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="10bfb-120">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="10bfb-121">Jak napisać dane obiektu do pliku XML (C#)</span><span class="sxs-lookup"><span data-stu-id="10bfb-121">How to write object data to an XML file (C#)</span></span>](./how-to-write-object-data-to-an-xml-file.md)
- [<span data-ttu-id="10bfb-122">Serializacja (C#)</span><span class="sxs-lookup"><span data-stu-id="10bfb-122">Serialization (C#)</span></span>](./index.md)
- [<span data-ttu-id="10bfb-123">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="10bfb-123">C# Programming Guide</span></span>](../../index.md)
