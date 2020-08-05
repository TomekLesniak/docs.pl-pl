---
title: 'Instrukcje: Stosowanie ochrony danych'
description: Dowiedz się, jak używać ochrony danych, uzyskując dostęp do interfejsu API ochrony danych (DPAPI) w środowisku .NET.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET], data protection API
- data [.NET], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET], data protection API
- data protection API [.NET]
- decryption
- data [.NET], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: 263a07ddf357734e819fffdd41cdff60657adf15
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557063"
---
# <a name="how-to-use-data-protection"></a>Instrukcje: Stosowanie ochrony danych

> [!NOTE]
> Ten artykuł dotyczy systemu Windows.
>
> Aby uzyskać informacje na temat ASP.NET Core, zobacz [ASP.NET Core ochrony danych](/aspnet/core/security/data-protection/introduction).

Platforma .NET zapewnia dostęp do interfejsu API ochrony danych (DPAPI), który umożliwia szyfrowanie danych przy użyciu informacji z bieżącego konta użytkownika lub komputera.  Korzystając z interfejsu DPAPI, można złagodzić trudne problemy związane z jawnym generowaniem i przechowywaniem klucza kryptograficznego.  
  
Użyj <xref:System.Security.Cryptography.ProtectedData> klasy, aby zaszyfrować kopię tablicy bajtów. Ta funkcja jest dostępna w .NET Framework, .NET Core i .NET 5.  Możesz określić, że dane zaszyfrowane przez bieżące konto użytkownika mogą zostać odszyfrowane tylko przez to samo konto użytkownika, lub możesz określić, że dane zaszyfrowane przez bieżące konto użytkownika mogą zostać odszyfrowane za pomocą dowolnego konta na komputerze.  <xref:System.Security.Cryptography.DataProtectionScope>Szczegółowy opis opcji można znaleźć w wyliczeniu <xref:System.Security.Cryptography.ProtectedData> .  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a>Aby zaszyfrować dane do pliku lub strumienia przy użyciu ochrony danych  
  
1. Utwórz entropię losową.  
  
2. Wywołaj metodę statyczną <xref:System.Security.Cryptography.ProtectedData.Protect%2A> podczas przekazywania tablicy bajtów do szyfrowania, entropii i zakresu ochrony danych.  
  
3. Zapisz dane zaszyfrowane do pliku lub strumienia.  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a>Aby odszyfrować dane z pliku lub strumienia przy użyciu ochrony danych  
  
1. Odczytaj zaszyfrowane dane z pliku lub strumienia.  
  
2. Wywołaj metodę statyczną <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> podczas przekazywania tablicy bajtów do odszyfrowania i zakresu ochrony danych.  
  
## <a name="example"></a>Przykład

Poniższy przykład kodu ilustruje dwie formy szyfrowania i odszyfrowywania.  Najpierw kod szyfruje, a następnie odszyfrowuje tablicę bajtów w pamięci.  W przykładzie kod szyfruje kopię tablicy bajtowej, zapisuje ją w pliku, ładuje dane z powrotem z pliku, a następnie odszyfrowuje dane.  Przykład wyświetla oryginalne dane, zaszyfrowane dane i odszyfrowane dane.

[!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
[!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  

Ten przykład kompiluje i działa tylko w przypadku .NET Framework i uruchamiania w systemie Windows.

- Dołącz odwołanie do `System.Security.dll` .  
  
- Dołącz <xref:System> <xref:System.IO> <xref:System.Security.Cryptography> przestrzeń nazw,,, i <xref:System.Text> .  
  
## <a name="see-also"></a>Zobacz też

- [Model kryptografii](cryptography-model.md)
- [Usługi kryptograficzne](cryptographic-services.md)
- [Kryptografia międzyplatformowa](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
- [Ochrona danych ASP.NET Core](/aspnet/core/security/data-protection/introduction)
