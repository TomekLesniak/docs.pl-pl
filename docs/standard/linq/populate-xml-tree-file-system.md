---
title: Jak wypełnić drzewo XML z systemu plików — LINQ to XML
description: Dowiedz się, jak wypełnić drzewo XML z systemu plików w języku C# lub Visual Basic.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 2aa2ccac-4a22-47ae-9107-3bb8df232576
ms.openlocfilehash: 6b0307aca9c9075120021967c08efcad8b595653
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89553726"
---
# <a name="how-to-populate-an-xml-tree-from-the-file-system-linq-to-xml"></a><span data-ttu-id="bab5b-103">Jak wypełnić drzewo XML z systemu plików (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="bab5b-103">How to populate an XML tree from the file system (LINQ to XML)</span></span>

<span data-ttu-id="bab5b-104">Typową i użyteczną aplikacją drzew XML jest hierarchiczny magazyn danych o wartościach nazw.</span><span class="sxs-lookup"><span data-stu-id="bab5b-104">A common and useful application of XML trees is as a hierarchical name-value data store.</span></span> <span data-ttu-id="bab5b-105">Można wypełnić drzewo XML danymi hierarchicznymi, a następnie wykonać do nich zapytania, przekształcić je i w razie potrzeby serializować.</span><span class="sxs-lookup"><span data-stu-id="bab5b-105">You can populate an XML tree with hierarchical data, and then query it, transform it, and if necessary, serialize it.</span></span> <span data-ttu-id="bab5b-106">W tym przypadku wiele semantyki specyficznych dla języka XML, takich jak obszary nazw i zachowanie białych znaków, nie są ważne.</span><span class="sxs-lookup"><span data-stu-id="bab5b-106">For this use, many of the XML-specific semantics, such as namespaces and white space behavior, aren't important.</span></span> <span data-ttu-id="bab5b-107">Zamiast tego używasz drzewa XML jako małej, hierarchicznej bazy danych pojedynczego użytkownika.</span><span class="sxs-lookup"><span data-stu-id="bab5b-107">Instead, you're using the XML tree as a small, in-memory, single-user hierarchical database.</span></span>

## <a name="example-populate-an-xml-tree-and-then-query-it"></a><span data-ttu-id="bab5b-108">Przykład: Wypełnij drzewo XML, a następnie Zbadaj je</span><span class="sxs-lookup"><span data-stu-id="bab5b-108">Example: Populate an XML tree and then query it</span></span>

<span data-ttu-id="bab5b-109">Poniższy przykład używa rekursji do wypełnienia drzewa XML danymi o plikach w lokalnym systemie plików.</span><span class="sxs-lookup"><span data-stu-id="bab5b-109">The following example uses recursion to populate an XML tree with data about the files in the local file system.</span></span> <span data-ttu-id="bab5b-110">Następnie wykonuje zapytanie dotyczące drzewa, sumując wszystkie rozmiary plików.</span><span class="sxs-lookup"><span data-stu-id="bab5b-110">It then queries the tree, totalling all the file sizes.</span></span>

```csharp
class Program
{
    static XElement CreateFileSystemXmlTree(string source)
    {
        DirectoryInfo di = new DirectoryInfo(source);
        return new XElement("Dir",
            new XAttribute("Name", di.Name),
            from d in Directory.GetDirectories(source)
            select CreateFileSystemXmlTree(d),
            from fi in di.GetFiles()
            select new XElement("File",
                new XElement("Name", fi.Name),
                new XElement("Length", fi.Length)
            )
        );
    }

    static void Main(string[] args)
    {
        XElement fileSystemTree = CreateFileSystemXmlTree("C:/Tmp");
        Console.WriteLine(fileSystemTree);
        Console.WriteLine("------");
        long totalFileSize =
            (from f in fileSystemTree.Descendants("File")
             select (long)f.Element("Length")).Sum();
        Console.WriteLine("Total File Size:{0}", totalFileSize);
    }
}
```

```vb
Module Module1
    Function CreateFileSystemXmlTree(ByVal source As String) As XElement
        Dim di As DirectoryInfo = New DirectoryInfo(source)
        Return <Dir Name=<%= di.Name %>>
                   <%= From d In Directory.GetDirectories(source) _
                       Select CreateFileSystemXmlTree(d) %>
                   <%= From fi In di.GetFiles() _
                       Select <File>
                                  <Name><%= fi.Name %></Name>
                                  <Length><%= fi.Length %></Length>
                              </File> %>
               </Dir>
    End Function

    Sub Main()
        Dim fileSystemTree As XElement = CreateFileSystemXmlTree("C:/Tmp")
        Console.WriteLine(fileSystemTree)
        Console.WriteLine("------")
        Dim totalFileSize As Long = _
            ( _
                From f In fileSystemTree...<File> _
                Select CLng(f.<Length>(0)) _
            ).Sum()
        Console.WriteLine("Total File Size:{0}", totalFileSize)
    End Sub
End Module
```

<span data-ttu-id="bab5b-111">Przykład generuje dane wyjściowe podobne do następujących:</span><span class="sxs-lookup"><span data-stu-id="bab5b-111">The example produces output similar to the following:</span></span>

```xml
<Dir Name="Tmp">
  <Dir Name="ConsoleApplication1">
    <Dir Name="bin">
      <Dir Name="Debug">
        <File>
          <Name>ConsoleApplication1.exe</Name>
          <Length>4608</Length>
        </File>
        <File>
          <Name>ConsoleApplication1.pdb</Name>
          <Length>11776</Length>
        </File>
        <File>
          <Name>ConsoleApplication1.vshost.exe</Name>
          <Length>9568</Length>
        </File>
        <File>
          <Name>ConsoleApplication1.vshost.exe.manifest</Name>
          <Length>473</Length>
        </File>
      </Dir>
    </Dir>
    <Dir Name="obj">
      <Dir Name="Debug">
        <Dir Name="TempPE" />
        <File>
          <Name>ConsoleApplication1.csproj.FileListAbsolute.txt</Name>
          <Length>322</Length>
        </File>
        <File>
          <Name>ConsoleApplication1.exe</Name>
          <Length>4608</Length>
        </File>
        <File>
          <Name>ConsoleApplication1.pdb</Name>
          <Length>11776</Length>
        </File>
      </Dir>
    </Dir>
    <Dir Name="Properties">
      <File>
        <Name>AssemblyInfo.cs</Name>
        <Length>1454</Length>
      </File>
    </Dir>
    <File>
      <Name>ConsoleApplication1.csproj</Name>
      <Length>2546</Length>
    </File>
    <File>
      <Name>ConsoleApplication1.sln</Name>
      <Length>937</Length>
    </File>
    <File>
      <Name>ConsoleApplication1.suo</Name>
      <Length>10752</Length>
    </File>
    <File>
      <Name>Program.cs</Name>
      <Length>269</Length>
    </File>
  </Dir>
</Dir>
------
Total File Size:59089
```
