---
title: Bezpieczeństwo danych i poufności informacji
ms.date: 03/30/2017
ms.assetid: 46fa5839-adf7-4c7c-bce3-71e941fa7de9
ms.openlocfilehash: b0721cbc4957dfe64627f3a18064110f96a26f2b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177387"
---
# <a name="privacy-and-data-security"></a>Bezpieczeństwo danych i poufności informacji

Zabezpieczanie poufnych informacji w aplikacji ADO.NET i zarządzanie nimi zależy od podstawowych produktów i technologii użytych do jego utworzenia. Usługa ADO.NET nie udostępnia bezpośrednio usług służących do zabezpieczania i szyfrowania danych.  
  
## <a name="cryptography-and-hash-codes"></a>Kody kryptografii i wartości skrótu  

 Klasy w <xref:System.Security.Cryptography> przestrzeni nazw .NET Framework mogą być używane z poziomu aplikacji ADO.NET, aby zapobiec odczytywaniu lub modyfikowaniu danych przez nieautoryzowane strony trzecie. Niektóre klasy są otokami dla niezarządzanego interfejsu CryptoAPI firmy Microsoft, podczas gdy inne są wdrożeniami zarządzanymi. Temat [usługi kryptograficzne](../../../standard/security/cryptographic-services.md) zawiera omówienie kryptografii w .NET Framework, opis sposobu implementacji cryptograph oraz sposób wykonywania określonych zadań kryptograficznych.  
  
 W przeciwieństwie do kryptografii, która umożliwia szyfrowanie i odszyfrowywanie danych, dane mieszania są procesem jednokierunkowym. Dane dotyczące mieszania są przydatne, gdy chcesz zapobiec naruszeniu przez sprawdzenie, czy dane nie zostały zmienione: dane wejściowe są identyczne, algorytmy wyznaczania wartości skrótu zawsze generują identyczne krótkie wartości wyjściowe, które można łatwo porównać. [Zapewnianie integralności danych za pomocą kodów skrótów](../../../standard/security/ensuring-data-integrity-with-hash-codes.md) opisuje sposób generowania i weryfikowania wartości skrótu.  
  
## <a name="encrypting-configuration-files"></a>Szyfrowanie plików konfiguracji  

 Ochrona dostępu do źródła danych jest jednym z najważniejszych celów związanych z zabezpieczaniem aplikacji. Parametry połączenia przedstawiają potencjalną lukę w zabezpieczeniach, jeśli nie została zabezpieczona. Parametry połączenia zapisane w plikach konfiguracji są przechowywane w standardowych plikach XML, dla których .NET Framework zdefiniował wspólny zestaw elementów. Konfiguracja chroniona umożliwia szyfrowanie poufnych informacji w pliku konfiguracji. Program, który jest przeznaczony głównie do aplikacji ASP.NET, może być również używany do szyfrowania sekcji plików konfiguracyjnych w aplikacjach systemu Windows. Aby uzyskać więcej informacji, zobacz [Ochrona informacji o połączeniu](protecting-connection-information.md).  
  
## <a name="securing-string-values-in-memory"></a>Zabezpieczanie wartości ciągu w pamięci  

 Jeśli <xref:System.String> obiekt zawiera informacje poufne, takie jak hasło, numer karty kredytowej lub dane osobowe, istnieje ryzyko, że te informacje mogą być ujawnione po ich użyciu, ponieważ aplikacja nie może usunąć danych z pamięci komputera.  
  
 Obiekt <xref:System.String> jest niezmienny; jego wartość nie może zostać zmodyfikowana po utworzeniu. Zmiany, które pojawiają się w celu zmodyfikowania wartości ciągu w rzeczywistości tworzą nowe wystąpienie <xref:System.String> obiektu w pamięci, przechowując dane jako zwykły tekst. Ponadto nie można przewidzieć, kiedy wystąpienia ciągu zostaną usunięte z pamięci. Odzyskiwanie pamięci z użyciem ciągów nie jest deterministyczne przy użyciu wyrzucania elementów bezużytecznych platformy .NET. Należy unikać używania <xref:System.String> klas i, <xref:System.Text.StringBuilder> Jeśli dane są naprawdę poufne.  
  
 <xref:System.Security.SecureString>Klasa zawiera metody szyfrowania tekstu przy użyciu interfejsu API ochrony danych (DPAPI) w pamięci. Ten ciąg jest następnie usuwany z pamięci, gdy nie jest już wymagany. Nie ma `ToString` metody, aby szybko odczytać zawartość <xref:System.Security.SecureString> . Można zainicjować nowe wystąpienie `SecureString` bez wartości lub przekazując wskaźnik do tablicy <xref:System.Char> obiektów. Następnie można użyć różnych metod klasy do pracy z ciągiem.
  
## <a name="see-also"></a>Zobacz też

- [Zabezpieczanie aplikacji ADO.NET](securing-ado-net-applications.md)
- [Zabezpieczenia serwera SQL](./sql/sql-server-security.md)
- [Omówienie ADO.NET](ado-net-overview.md)
