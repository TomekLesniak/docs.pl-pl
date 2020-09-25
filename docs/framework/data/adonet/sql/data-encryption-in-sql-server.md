---
title: Szyfrowanie danych w programie SQL Server
ms.date: 03/30/2017
ms.assetid: 83b992f7-b351-4678-b4b9-f4ffd58134cc
ms.openlocfilehash: d0bda11f1a2933d096aa91d2be79d3af35172284
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169534"
---
# <a name="data-encryption-in-sql-server"></a>Szyfrowanie danych w programie SQL Server

SQL Server udostępnia funkcje do szyfrowania i odszyfrowywania danych przy użyciu certyfikatu, klucza asymetrycznego lub klucza symetrycznego. Wszystkie te elementy są zarządzane w wewnętrznym magazynie certyfikatów. Magazyn używa hierarchii szyfrowania, która zabezpiecza certyfikaty i klucze na jednym poziomie z warstwą powyżej tej warstwy w hierarchii. Ten obszar funkcji SQL Server nosi nazwę magazyn tajny.  
  
 Najszybszym trybem szyfrowania obsługiwanym przez funkcje szyfrowania jest szyfrowanie klucza symetrycznego. Ten tryb jest odpowiedni do obsługi dużych ilości danych. Klucze symetryczne mogą być szyfrowane przez certyfikaty, hasła lub inne klucze symetryczne.  
  
## <a name="keys-and-algorithms"></a>Klucze i algorytmy  

 SQL Server obsługuje kilka algorytmów szyfrowania kluczy symetrycznych, w tym DES, Triple DES, RC2, RC4, 128-bitowy RC4, DESX, 128-bit AES, 192-bit AES i 256-bitowy AES. Algorytmy są implementowane przy użyciu interfejsu API kryptografii systemu Windows.  
  
 W zakresie połączenia z bazą danych SQL Server może obsługiwać wiele otwartych kluczy symetrycznych. Otwarty klucz zostanie pobrany ze sklepu i jest dostępny do odszyfrowania danych. Gdy dane są odszyfrowywane, nie ma potrzeby określania klucza symetrycznego do użycia. Każda zaszyfrowana wartość zawiera identyfikator klucza (identyfikator GUID klucza) klucza używany do szyfrowania. Aparat dopasowuje strumień szyfrowanych bajtów do otwartego klucza symetrycznego, jeśli prawidłowy klucz został odszyfrowany i jest otwarty. Ten klucz jest następnie używany do odszyfrowywania i zwracania danych. Jeśli prawidłowy klucz nie jest otwarty, zwracana jest wartość NULL.  
  
 Aby zapoznać się z przykładem, który pokazuje, jak korzystać z szyfrowanych danych w bazie danych, zobacz artykuł [szyfrowanie kolumny danych](/sql/relational-databases/security/encryption/encrypt-a-column-of-data).
  
## <a name="external-resources"></a>Zasoby zewnętrzne  

 Aby uzyskać więcej informacji na temat szyfrowania danych, zobacz następujące zasoby.  
  
|Zasób|Opis|  
|-|-|  
|[Szyfrowanie SQL Server](/sql/relational-databases/security/encryption/sql-server-encryption)|Zawiera omówienie szyfrowania w SQL Server. Ten temat zawiera linki do dodatkowych artykułów.|  
|[Hierarchia szyfrowania](/sql/relational-databases/security/encryption/encryption-hierarchy)|Zawiera omówienie szyfrowania w SQL Server. Ten temat zawiera linki do dodatkowych artykułów.|  
  
## <a name="see-also"></a>Zobacz też

- [Zabezpieczanie aplikacji ADO.NET](../securing-ado-net-applications.md)
- [Scenariusze zabezpieczeń aplikacji w programie SQL Server](application-security-scenarios-in-sql-server.md)
- [Uwierzytelnianie w programie SQL Server](authentication-in-sql-server.md)
- [Serwer i role bazy danych w programie SQL Server](server-and-database-roles-in-sql-server.md)
- [Własność i oddzielenie schematu użytkownika w programie SQL Server](ownership-and-user-schema-separation-in-sql-server.md)
- [Autoryzacja i uprawnienia w programie SQL Server](authorization-and-permissions-in-sql-server.md)
- [Omówienie ADO.NET](../ado-net-overview.md)
