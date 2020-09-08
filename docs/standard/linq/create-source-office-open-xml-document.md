---
title: Tworzenie źródłowego dokumentu Office Open XML — LINQ to XML
description: Dowiedz się, jak utworzyć dokument Office Open XML WordprocessingML używany przez inne przykłady w tym samouczku.
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
ms.assetid: 653c8cdb-73be-4dc2-927f-924cfb4ed9ed
ms.openlocfilehash: b3401d7309879661dcfc7062418ee75430dccf35
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/08/2020
ms.locfileid: "89552852"
---
# <a name="create-the-source-office-open-xml-document-linq-to-xml"></a><span data-ttu-id="cb9ca-103">Tworzenie źródłowego dokumentu Office Open XML (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="cb9ca-103">Create the source Office Open XML document (LINQ to XML)</span></span>

<span data-ttu-id="cb9ca-104">W tym artykule przedstawiono sposób tworzenia dokumentu Office Open XML WordprocessingML używanego przez inne przykłady w tym samouczku.</span><span class="sxs-lookup"><span data-stu-id="cb9ca-104">This article shows how to create the Office Open XML WordprocessingML document used by the other examples in this tutorial.</span></span> <span data-ttu-id="cb9ca-105">Jeśli wykonasz te instrukcje, dane wyjściowe będą zgodne z danymi wyjściowymi podanymi w każdym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="cb9ca-105">If you follow these instructions, your output will match the output provided in each example.</span></span>

<span data-ttu-id="cb9ca-106">Jednak przykłady w tym samouczku będą działały z dowolnym prawidłowym dokumentem WordprocessingML.</span><span class="sxs-lookup"><span data-stu-id="cb9ca-106">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>

<span data-ttu-id="cb9ca-107">Aby utworzyć dokument, który jest wykorzystywany przez ten samouczek, musisz mieć zainstalowany Microsoft Office 2007 lub nowszy lub mieć Microsoft Office 2003 z pakietem zgodności Microsoft Office dla formatów plików programów Word, Excel i PowerPoint 2007.</span><span class="sxs-lookup"><span data-stu-id="cb9ca-107">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>

## <a name="create-the-wordprocessingml-document"></a><span data-ttu-id="cb9ca-108">Tworzenie dokumentu WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="cb9ca-108">Create the WordprocessingML document</span></span>

<span data-ttu-id="cb9ca-109">Wykonaj następujące kroki, aby utworzyć dokument WordprocessingML:</span><span class="sxs-lookup"><span data-stu-id="cb9ca-109">Use the following steps to create the WordprocessingML document:</span></span>

1. <span data-ttu-id="cb9ca-110">Utwórz nowy dokument programu Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="cb9ca-110">Create a new Microsoft Word document.</span></span>
1. <span data-ttu-id="cb9ca-111">Wklej następujący tekst do nowego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="cb9ca-111">Paste the following text into the new document.</span></span>
   1. <span data-ttu-id="cb9ca-112">W przypadku języka C# Użyj tego tekstu:</span><span class="sxs-lookup"><span data-stu-id="cb9ca-112">For C#, use this text:</span></span>

         ```text
         Parsing WordprocessingML with LINQ to XML

         The following example prints to the console.

         using System;

            class Program {
               public static void Main(string[] args) {
               Console.WriteLine("Hello World");
            }
         }

         This example produces the following output:

         Hello World
         ```

   1. <span data-ttu-id="cb9ca-113">W przypadku Visual Basic Użyj tego tekstu:</span><span class="sxs-lookup"><span data-stu-id="cb9ca-113">For Visual Basic, use this text:</span></span>

      ```text
      Parsing WordprocessingML with LINQ to XML

      The following example prints to the console.

      Imports System

      Class Program
         Public Shared  Sub Main(ByVal args() As String)
            Console.WriteLine("Hello World")
         End Sub
      End Class

      This example produces the following output:

      Hello World
      ```

1. <span data-ttu-id="cb9ca-114">Sformatuj pierwszy wiersz za pomocą stylu "Nagłówek 1".</span><span class="sxs-lookup"><span data-stu-id="cb9ca-114">Format the first line with the style "Heading 1".</span></span>
1. <span data-ttu-id="cb9ca-115">W przypadku języka C# wybierz wiersze zawierające kod w języku C#.</span><span class="sxs-lookup"><span data-stu-id="cb9ca-115">For C#, select the lines that contain the C# code.</span></span> <span data-ttu-id="cb9ca-116">Pierwszy wiersz rozpoczyna się od `using` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="cb9ca-116">The first line starts with the `using` keyword.</span></span> <span data-ttu-id="cb9ca-117">Ostatnim wierszem jest ostatni zamykający nawias klamrowy.</span><span class="sxs-lookup"><span data-stu-id="cb9ca-117">The last line is the last closing brace.</span></span> <span data-ttu-id="cb9ca-118">Sformatuj linie przy użyciu czcionki Courier.</span><span class="sxs-lookup"><span data-stu-id="cb9ca-118">Format the lines with the courier font.</span></span> <span data-ttu-id="cb9ca-119">Sformatuj je przy użyciu nowego stylu i nazwij nowy styl "Code".</span><span class="sxs-lookup"><span data-stu-id="cb9ca-119">Format them with a new style, and name the new style "Code".</span></span>
1. <span data-ttu-id="cb9ca-120">W obszarze Visual Basic wybierz wiersze zawierające kod Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="cb9ca-120">For Visual Basic, select the lines that contain the Visual Basic code.</span></span> <span data-ttu-id="cb9ca-121">Pierwszy wiersz rozpoczyna się od `Imports` słowa kluczowego.</span><span class="sxs-lookup"><span data-stu-id="cb9ca-121">The first line starts with the `Imports` keyword.</span></span> <span data-ttu-id="cb9ca-122">Ostatnim wierszem jest "End Class".</span><span class="sxs-lookup"><span data-stu-id="cb9ca-122">The last line is "End Class".</span></span> <span data-ttu-id="cb9ca-123">Sformatuj linie przy użyciu czcionki Courier.</span><span class="sxs-lookup"><span data-stu-id="cb9ca-123">Format the lines with the courier font.</span></span> <span data-ttu-id="cb9ca-124">Sformatuj je przy użyciu nowego stylu i nazwij nowy styl "Code".</span><span class="sxs-lookup"><span data-stu-id="cb9ca-124">Format them with a new style, and name the new style "Code".</span></span>
1. <span data-ttu-id="cb9ca-125">Na koniec zaznacz cały wiersz zawierający dane wyjściowe i sformatuj go przy użyciu `Code` stylu.</span><span class="sxs-lookup"><span data-stu-id="cb9ca-125">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>
1. <span data-ttu-id="cb9ca-126">Zapisz dokument i nadaj mu nazwę SampleDoc.docx.</span><span class="sxs-lookup"><span data-stu-id="cb9ca-126">Save the document, and name it SampleDoc.docx.</span></span>

> [!NOTE]
> <span data-ttu-id="cb9ca-127">Jeśli używasz programu Microsoft Word 2003, wybierz pozycję **dokument programu Word 2007** na liście rozwijanej **Zapisz jako typ** .</span><span class="sxs-lookup"><span data-stu-id="cb9ca-127">If you're using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb9ca-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="cb9ca-128">See also</span></span>

- [<span data-ttu-id="cb9ca-129">Samouczek: manipulowanie zawartością w dokumencie WordprocessingML</span><span class="sxs-lookup"><span data-stu-id="cb9ca-129">Tutorial: Manipulate content in a WordprocessingML document</span></span>](xml-shape-wordprocessingml-documents.md)
