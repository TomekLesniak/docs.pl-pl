---
title: N-warstwowa LINQ to SQL z użyciem ASP.NET
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: 1af7f0d78f16e25c1ae7bf563c6abfb3b77f6183
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559229"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a>N-warstwowa LINQ to SQL z użyciem ASP.NET
W aplikacjach ASP.NET korzystających z [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] programu można użyć <xref:System.Web.UI.WebControls.LinqDataSource> kontrolki serwer sieci Web. Kontrolka obsługuje większość logiki, która musi być wymagana do wykonywania zapytań [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , przekazać dane do przeglądarki, pobrać ją i przesłać do niej, a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> następnie zaktualizować bazę danych. Wystarczy skonfigurować kontrolkę w znaczniku, a kontrolka obsługuje cały transfer danych między programem [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] a przeglądarką. Ponieważ kontrolka obsługuje interakcje z warstwą prezentacji i [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] obsługuje komunikację z warstwą danych, głównym fokusem w aplikacjach wielowarstwowych ASP.NET jest tworzenie niestandardowej logiki biznesowej.  
  
 Aby uzyskać więcej informacji na temat `LINQDataSource` , zobacz temat [formant serwera sieci Web LinqDataSource — Omówienie](/previous-versions/aspnet/bb547113(v=vs.100)).  
  
## <a name="see-also"></a>Zobacz także

- [N-warstwowe i zdalne aplikacje z użyciem LINQ to SQL](n-tier-and-remote-applications-with-linq-to-sql.md)
