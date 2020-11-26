---
title: Generowanie klas typów danych z kodu XML
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: a7920a8c8c4f279dd3fc52029c5da5e9b685efe2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96238252"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="c3721-102">Generowanie klas typów danych z kodu XML</span><span class="sxs-lookup"><span data-stu-id="c3721-102">Generating Data Type Classes from XML</span></span>

<span data-ttu-id="c3721-103">.NET Framework 4,5 zawiera nową funkcję do generowania klas typów danych z pliku XML.</span><span class="sxs-lookup"><span data-stu-id="c3721-103">.NET Framework 4.5 includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="c3721-104">W tym temacie opisano sposób automatycznego generowania typów danych dla kanału informacyjnego RSS w blogu platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="c3721-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="c3721-105">Uzyskiwanie kodu XML ze źródła danych RSS blogu platformy .NET</span><span class="sxs-lookup"><span data-stu-id="c3721-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="c3721-106">W programie Internet Explorer przejdź do [kanału informacyjnego RSS blogu platformy .NET](https://devblogs.microsoft.com/dotnet/feed/).</span><span class="sxs-lookup"><span data-stu-id="c3721-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="c3721-107">Kliknij prawym przyciskiem myszy stronę i wybierz polecenie **Wyświetl źródło**.</span><span class="sxs-lookup"><span data-stu-id="c3721-107">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="c3721-108">Skopiuj tekst kanału informacyjnego, naciskając **klawisze Ctrl + A** , aby zaznaczyć cały tekst, a następnie **klawisze CTRL + C** , aby skopiować.</span><span class="sxs-lookup"><span data-stu-id="c3721-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="c3721-109">Tworzenie typów danych</span><span class="sxs-lookup"><span data-stu-id="c3721-109">Creating the data types</span></span>  
  
1. <span data-ttu-id="c3721-110">Otwórz plik kodu, w którym ma być używany serwer proxy.</span><span class="sxs-lookup"><span data-stu-id="c3721-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="c3721-111">Ten plik powinien być częścią projektu .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="c3721-111">This file should be part of a .NET Framework 4.5 project.</span></span>  
  
2. <span data-ttu-id="c3721-112">Umieść kursor w lokalizacji w pliku poza istniejącymi klasami.</span><span class="sxs-lookup"><span data-stu-id="c3721-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="c3721-113">Wybierz pozycję **Edytuj**, **Wklej specjalnie**, **Wklej kod XML jako klasy**.</span><span class="sxs-lookup"><span data-stu-id="c3721-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="c3721-114">Klasy o nazwie `link` , `rss` ,, `rssChannel` `rssChannelImage` `rssChannelItem` i `rssChannelItemGuid` są tworzone z niezbędnymi elementami członkowskimi w celu uzyskania dostępu do elementów w kanale informacyjnym RSS.</span><span class="sxs-lookup"><span data-stu-id="c3721-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="c3721-115">Korzystanie z wygenerowanych klas</span><span class="sxs-lookup"><span data-stu-id="c3721-115">Using the generated classes</span></span>  
  
1. <span data-ttu-id="c3721-116">Po wygenerowaniu klasy mogą być używane w kodzie, podobnie jak w przypadku innych klas.</span><span class="sxs-lookup"><span data-stu-id="c3721-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="c3721-117">Poniższy przykład kodu zwraca nowe wystąpienie `rssChannelImage` klasy.</span><span class="sxs-lookup"><span data-stu-id="c3721-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```csharp
    var channelImage = new rssChannelImage()
    {
        title = "MyImage",
        link = "http://www.contoso.com/images/channelImage.jpg",
        url = "http://www.contoso.com/entries/myEntry.html"
    };  
    ```
