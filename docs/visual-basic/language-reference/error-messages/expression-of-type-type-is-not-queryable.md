---
title: Wyrażenie <type> nie umożliwia zadawania zapytań
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: 78b47601bf0a013d079f638f6dac27511e01aec4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874212"
---
# <a name="expression-of-type-type-is-not-queryable"></a>Wyrażenie \<type> nie umożliwia zadawania zapytań

Wyrażenie typu \<type> nie jest queryable. Upewnij się, że nie brakuje importu odwołania do zestawu i/lub przestrzeni nazw dla dostawcy LINQ.  
  
 Typy Queryable są zdefiniowane w <xref:System.Linq> <xref:System.Data.Linq> <xref:System.Xml.Linq> przestrzeniach nazw, i. Aby wykonać zapytania LINQ, należy zaimportować co najmniej jedną z tych przestrzeni nazw.  
  
 <xref:System.Linq>Przestrzeń nazw umożliwia wykonywanie zapytań dotyczących obiektów, takich jak kolekcje i tablice, za pomocą LINQ.  
  
 <xref:System.Data.Linq>Przestrzeń nazw umożliwia wykonywanie zapytań dotyczących zestawów danych ADO.NET i baz SQL Server przy użyciu LINQ.  
  
 <xref:System.Xml.Linq>Przestrzeń nazw umożliwia wykonywanie zapytań XML przy użyciu LINQ i używanie funkcji XML w Visual Basic.  
  
 **Identyfikator błędu:** BC36593  
  
## <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1. Dodaj `Import` instrukcję dla <xref:System.Linq> <xref:System.Data.Linq> przestrzeni nazw,, lub <xref:System.Xml.Linq> do pliku z kodem. Możesz również zaimportować przestrzenie nazw dla projektu przy użyciu strony **odwołania** projektanta projektu (**mój projekt**).  
  
2. Upewnij się, że typ, który został zidentyfikowany jako źródło zapytania, jest typem queryable. Oznacza to, że typ, który implementuje <xref:System.Collections.Generic.IEnumerable%601> lub <xref:System.Linq.IQueryable%601> .  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [Wprowadzenie do LINQ w Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../programming-guide/language-features/linq/index.md)
- [XML](../../programming-guide/language-features/xml/index.md)
- [Referencje i instrukcja Imports](../../programming-guide/program-structure/references-and-the-imports-statement.md)
- [Imports — Instrukcja (.NET Namespace i Type)](../statements/imports-statement-net-namespace-and-type.md)
- [Strona odwołań, Projektant projektu (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
