---
title: Zabezpieczenia w składniku LINQ to SQL
ms.date: 03/30/2017
ms.assetid: d49787f7-414e-4c71-aa33-80a5895536b1
ms.openlocfilehash: 6260f0c565a25764c8fabd2770d4f06a987aa9bb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173396"
---
# <a name="security-in-linq-to-sql"></a>Zabezpieczenia w składniku LINQ to SQL

Zagrożenia bezpieczeństwa są zawsze obecne podczas łączenia się z bazą danych. Mimo że LINQ to SQL mogą zawierać nowe sposoby pracy z danymi w SQL Server, nie zapewnia żadnych dodatkowych mechanizmów zabezpieczeń.  
  
## <a name="access-control-and-authentication"></a>Access Control i uwierzytelnianie  

 LINQ to SQL nie ma własnego modelu użytkownika ani mechanizmów uwierzytelniania. Użyj zabezpieczeń SQL Server, aby kontrolować dostęp do bazy danych, tabel baz danych, widoków i procedur składowanych, które są mapowane na model obiektu. Przyznaj minimalny dostęp użytkownikom i wymagaj silnych haseł do uwierzytelniania użytkowników.  
  
## <a name="mapping-and-schema-information"></a>Mapowanie i informacje o schemacie  

 Mapowanie typu SQL-CLR i informacje o schemacie bazy danych w modelu obiektów lub zewnętrznym pliku mapowania są dostępne dla wszystkich z dostępem do tych plików w systemie plików. Załóżmy, że informacje o schemacie będą dostępne dla wszystkich osób, które mogą uzyskiwać dostęp do modelu obiektów lub zewnętrznego pliku mapowania. Aby zapobiec bardziej rozległemu dostępowi do informacji o schemacie, należy użyć mechanizmów zabezpieczeń plików do zabezpieczania plików źródłowych i plików mapowania.  
  
## <a name="connection-strings"></a>Parametry połączeń  

 Zawsze, gdy jest to możliwe, należy unikać używania haseł w ciągach połączenia. Nie tylko jest parametrami połączenia, które jest ryzykiem związanym z zabezpieczeniami, ale parametry połączenia mogą być również dodawane w postaci zwykłego tekstu do modelu obiektów lub zewnętrznego pliku mapowania przy użyciu narzędzia wiersza polecenia Object Relational Designer lub SQLMetal. Każda osoba mająca dostęp do modelu obiektów lub zewnętrznego pliku mapowania za pośrednictwem systemu plików może zobaczyć hasło połączenia (jeśli zostało dołączone do parametrów połączenia).  
  
 Aby zminimalizować takie ryzyko, należy używać zabezpieczeń zintegrowanych w celu nawiązania zaufanego połączenia z SQL Server. Korzystając z tej metody, nie trzeba przechowywać hasła w parametrach połączenia. Aby uzyskać więcej informacji, zobacz [SQL Server zabezpieczenia](../sql-server-security.md).  
  
 W przypadku braku zintegrowanego zabezpieczenia w parametrach połączenia będzie wymagana wartość hasła w postaci zwykłego tekstu. Najlepszym sposobem na zabezpieczenie parametrów połączenia w celu zwiększenia kolejności ryzyka jest następujące:  
  
- Używaj zintegrowanych zabezpieczeń.  
  
- Zabezpieczanie parametrów połączenia z hasłami i minimalizowanie przekazywania między ciągami połączeń.  
  
- Użyj <xref:System.Data.SqlClient.SqlConnection?displayProperty=nameWithType> klasy zamiast parametrów połączenia, ponieważ ogranicza ona czas ekspozycji. Klasy LINQ to SQL <xref:System.Data.Linq.DataContext?displayProperty=nameWithType> można utworzyć przy użyciu <xref:System.Data.SqlClient.SqlConnection> .  
  
- Zminimalizuj okresy istnienia i punkty dotykowe dla wszystkich parametrów połączenia.  
  
## <a name="see-also"></a>Zobacz też

- [Informacje uzupełniające](background-information.md)
- [Często zadawane pytania](frequently-asked-questions.md)
