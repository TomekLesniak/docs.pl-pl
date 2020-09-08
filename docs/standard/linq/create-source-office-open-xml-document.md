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
# <a name="create-the-source-office-open-xml-document-linq-to-xml"></a>Tworzenie źródłowego dokumentu Office Open XML (LINQ to XML)

W tym artykule przedstawiono sposób tworzenia dokumentu Office Open XML WordprocessingML używanego przez inne przykłady w tym samouczku. Jeśli wykonasz te instrukcje, dane wyjściowe będą zgodne z danymi wyjściowymi podanymi w każdym przykładzie.

Jednak przykłady w tym samouczku będą działały z dowolnym prawidłowym dokumentem WordprocessingML.

Aby utworzyć dokument, który jest wykorzystywany przez ten samouczek, musisz mieć zainstalowany Microsoft Office 2007 lub nowszy lub mieć Microsoft Office 2003 z pakietem zgodności Microsoft Office dla formatów plików programów Word, Excel i PowerPoint 2007.

## <a name="create-the-wordprocessingml-document"></a>Tworzenie dokumentu WordprocessingML

Wykonaj następujące kroki, aby utworzyć dokument WordprocessingML:

1. Utwórz nowy dokument programu Microsoft Word.
1. Wklej następujący tekst do nowego dokumentu.
   1. W przypadku języka C# Użyj tego tekstu:

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

   1. W przypadku Visual Basic Użyj tego tekstu:

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

1. Sformatuj pierwszy wiersz za pomocą stylu "Nagłówek 1".
1. W przypadku języka C# wybierz wiersze zawierające kod w języku C#. Pierwszy wiersz rozpoczyna się od `using` słowa kluczowego. Ostatnim wierszem jest ostatni zamykający nawias klamrowy. Sformatuj linie przy użyciu czcionki Courier. Sformatuj je przy użyciu nowego stylu i nazwij nowy styl "Code".
1. W obszarze Visual Basic wybierz wiersze zawierające kod Visual Basic. Pierwszy wiersz rozpoczyna się od `Imports` słowa kluczowego. Ostatnim wierszem jest "End Class". Sformatuj linie przy użyciu czcionki Courier. Sformatuj je przy użyciu nowego stylu i nazwij nowy styl "Code".
1. Na koniec zaznacz cały wiersz zawierający dane wyjściowe i sformatuj go przy użyciu `Code` stylu.
1. Zapisz dokument i nadaj mu nazwę SampleDoc.docx.

> [!NOTE]
> Jeśli używasz programu Microsoft Word 2003, wybierz pozycję **dokument programu Word 2007** na liście rozwijanej **Zapisz jako typ** .

## <a name="see-also"></a>Zobacz też

- [Samouczek: manipulowanie zawartością w dokumencie WordprocessingML](xml-shape-wordprocessingml-documents.md)
