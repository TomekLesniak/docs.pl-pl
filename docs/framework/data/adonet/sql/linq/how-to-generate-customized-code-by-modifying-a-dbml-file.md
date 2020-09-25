---
title: 'Instrukcje: Generowanie kodu dostosowane przez zmodyfikowanie pliku DBML'
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: ab49f76a0d5e7338a93e21ae9a8d1d9d74a21e82
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173442"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a>Instrukcje: Generowanie kodu dostosowane przez zmodyfikowanie pliku DBML

Można wygenerować kod źródłowy Visual Basic lub C# z pliku metadanych języka DBML (Database Markup Language). Takie podejście umożliwia dostosowanie domyślnego pliku DBML przed wygenerowaniem kodu mapowania aplikacji. Jest to funkcja zaawansowana.  
  
 Kroki w tym procesie są następujące:  
  
1. Generuj plik. dbml.  
  
2. Zmodyfikuj plik DBML za pomocą edytora. Należy pamiętać, że plik. dbml musi sprawdzać poprawność pliku definicji schematu (XSD) dla [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] plików. dbml. Aby uzyskać więcej informacji, zobacz [generowanie kodu w LINQ to SQL](code-generation-in-linq-to-sql.md).  
  
3. Generuj kod źródłowy Visual Basic lub C#.  
  
 W poniższych przykładach użyto narzędzia wiersza polecenia SQLMetal. Aby uzyskać więcej informacji, zobacz [SqlMetal.exe (Narzędzie generowania kodu)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Przykład  

 Poniższy kod generuje plik. dbml z przykładowej bazy danych Northwind. Jako źródło metadanych bazy danych można użyć nazwy bazy danych lub nazwy pliku MDF.  
  
```console  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a>Przykład  

 Poniższy kod generuje plik kodu źródłowego Visual Basic lub C# z pliku. dbml.  
  
```console
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a>Zobacz też

- [Generowanie kodu w składniku LINQ to SQL](code-generation-in-linq-to-sql.md)
- [SqlMetal.exe (Narzędzie generowania kodu)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [Tworzenie modelu obiektu](creating-the-object-model.md)
