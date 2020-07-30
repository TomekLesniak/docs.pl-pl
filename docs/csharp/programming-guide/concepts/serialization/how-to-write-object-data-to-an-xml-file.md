---
title: Jak napisać dane obiektu do pliku XML (C#)
description: Ten przykład w języku C# zapisuje obiekt z klasy do pliku XML przy użyciu klasy XmlSerializer. Dowiedz się, jak skompilować kod.
ms.date: 07/20/2015
ms.assetid: 7681eb98-703d-4005-a369-26a7bca0f894
ms.openlocfilehash: c88a85f8bc65a195f404dab6aa39675bac7e4f84
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303130"
---
# <a name="how-to-write-object-data-to-an-xml-file-c"></a><span data-ttu-id="14f59-104">Jak napisać dane obiektu do pliku XML (C#)</span><span class="sxs-lookup"><span data-stu-id="14f59-104">How to write object data to an XML file (C#)</span></span>
<span data-ttu-id="14f59-105">Ten przykład zapisuje obiekt z klasy do pliku XML przy użyciu <xref:System.Xml.Serialization.XmlSerializer> klasy.</span><span class="sxs-lookup"><span data-stu-id="14f59-105">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14f59-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="14f59-106">Example</span></span>  
  
```csharp  
public class XMLWrite  
{  
  
   static void Main(string[] args)  
    {  
        WriteXML();  
    }  
  
    public class Book  
    {  
        public String title;
    }  
  
    public static void WriteXML()  
    {  
        Book overview = new Book();  
        overview.title = "Serialization Overview";  
        System.Xml.Serialization.XmlSerializer writer =
            new System.Xml.Serialization.XmlSerializer(typeof(Book));  
  
        var path = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments) + "//SerializationOverview.xml";  
        System.IO.FileStream file = System.IO.File.Create(path);  
  
        writer.Serialize(file, overview);  
        file.Close();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="14f59-107">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="14f59-107">Compiling the Code</span></span>  
 <span data-ttu-id="14f59-108">Serializacja klasy musi mieć Konstruktor publiczny bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="14f59-108">The class being serialized must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="14f59-109">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="14f59-109">Robust Programming</span></span>  
 <span data-ttu-id="14f59-110">Następujące warunki mogą spowodować wyjątek:</span><span class="sxs-lookup"><span data-stu-id="14f59-110">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="14f59-111">Serializowana Klasa nie ma publicznego konstruktora bez parametrów.</span><span class="sxs-lookup"><span data-stu-id="14f59-111">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="14f59-112">Plik istnieje i jest tylko do odczytu ( <xref:System.IO.IOException> ).</span><span class="sxs-lookup"><span data-stu-id="14f59-112">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="14f59-113">Ścieżka jest za długa ( <xref:System.IO.PathTooLongException> ).</span><span class="sxs-lookup"><span data-stu-id="14f59-113">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="14f59-114">Dysk jest pełny ( <xref:System.IO.IOException> ).</span><span class="sxs-lookup"><span data-stu-id="14f59-114">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="14f59-115">Zabezpieczenia platformy .NET</span><span class="sxs-lookup"><span data-stu-id="14f59-115">.NET Security</span></span>  
 <span data-ttu-id="14f59-116">Ten przykład tworzy nowy plik, jeśli plik jeszcze nie istnieje.</span><span class="sxs-lookup"><span data-stu-id="14f59-116">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="14f59-117">Jeśli aplikacja musi utworzyć plik, aplikacja musi `Create` mieć dostęp do tego folderu.</span><span class="sxs-lookup"><span data-stu-id="14f59-117">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="14f59-118">Jeśli plik już istnieje, aplikacja wymaga tylko `Write` dostępu, ale ma mniejsze uprawnienia.</span><span class="sxs-lookup"><span data-stu-id="14f59-118">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="14f59-119">Jeśli to możliwe, bezpieczniejsze jest tworzenie pliku podczas wdrażania i udzielanie `Read` dostępu do pojedynczego pliku, a nie `Create` dostęp do folderu.</span><span class="sxs-lookup"><span data-stu-id="14f59-119">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f59-120">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="14f59-120">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="14f59-121">Jak odczytywać dane obiektów z pliku XML (C#)</span><span class="sxs-lookup"><span data-stu-id="14f59-121">How to read object data from an XML file (C#)</span></span>](./how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="14f59-122">Serializacja (C#)</span><span class="sxs-lookup"><span data-stu-id="14f59-122">Serialization (C#)</span></span>](./index.md)
