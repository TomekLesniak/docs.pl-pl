---
title: Dane binarne i dużej wartości w programie SQL Server
ms.date: 03/30/2017
ms.assetid: e00827b3-7511-4b2d-91d7-851ca86cc6b5
ms.openlocfilehash: a9296e83b0f4e4352423470433670bb2cbe5a248
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183042"
---
# <a name="sql-server-binary-and-large-value-data"></a>Dane binarne i dużej wartości w programie SQL Server

SQL Server zawiera `max` specyfikator, który rozszerza pojemność magazynu dla `varchar` , `nvarchar` i `varbinary` typów danych. `varchar(max)`, `nvarchar(max)` i `varbinary(max)` są nazywane zbiorczo *typami danych o dużej wartości*. Możesz użyć typów danych o dużej wartości do przechowywania maksymalnie 2 ^ 31-1 bajtów danych.  
  
 SQL Server 2008 wprowadza atrybut FILESTREAM, który nie jest typem danych, ale raczej atrybut, który można zdefiniować w kolumnie, umożliwiając przechowywanie danych dużych wartości w systemie plików, a nie w bazie danych.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Modyfikowanie dużej wartości (wartość maksymalna) danych w ADO.NET](modifying-large-value-max-data.md)  
 Opisuje sposób pracy z typami danych o dużej wartości.  
  
 [Dane FILESTREAM](filestream-data.md)  
 Opisuje sposób pracy z danymi o dużej wartości przechowywanych w SQL Server 2008 przy użyciu atrybutu FILESTREAM.  
  
## <a name="see-also"></a>Zobacz też

- [Typy danych programu SQL Server i ADO.NET](sql-server-data-types.md)
- [Operacje danych serwera SQL w ADO.NET](sql-server-data-operations.md)
- [Pobieranie i modyfikowanie danych ADO.NET](../retrieving-and-modifying-data.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
