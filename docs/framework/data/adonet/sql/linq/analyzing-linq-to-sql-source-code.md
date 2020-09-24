---
title: Analizowanie kodu źródłowego LINQ to SQL
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: e39b1686269442044beb73bb7e572738832bec27
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164587"
---
# <a name="analyzing-linq-to-sql-source-code"></a>Analizowanie kodu źródłowego LINQ to SQL

Wykonując poniższe kroki, można utworzyć [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] kod źródłowy z przykładowej bazy danych Northwind. Można porównać elementy modelu obiektów z elementami bazy danych, aby lepiej zobaczyć, jak są mapowane różne elementy.  
  
> [!NOTE]
> Deweloperzy korzystający z programu Visual Studio mogą używać projektanta O/R do tworzenia tego kodu.  
  
1. Jeśli nie masz jeszcze przykładowej bazy danych Northwind na komputerze deweloperskim, możesz pobrać bezpłatnie. Aby uzyskać więcej informacji, zobacz [Pobieranie przykładowych baz danych](downloading-sample-databases.md).  
  
2. Użyj narzędzia wiersza polecenia SqlMetal, aby wygenerować plik źródłowy Visual Basic lub C#. Aby uzyskać więcej informacji, zobacz [SqlMetal.exe (Narzędzie generowania kodu)](../../../../tools/sqlmetal-exe-code-generation-tool.md). Wpisując następujące polecenia w wierszu polecenia, można generować pliki źródłowe Visual Basic i C#, które zawierają procedury składowane i funkcje:  
  
    - `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    - `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a>Zobacz też

- [Odwołanie](reference.md)
- [Informacje uzupełniające](background-information.md)
