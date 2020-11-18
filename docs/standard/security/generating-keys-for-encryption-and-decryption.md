---
title: Generowanie kluczy szyfrowania i odszyfrowywania
description: Informacje na temat tworzenia kluczy symetrycznych i asymetrycznych na potrzeby szyfrowania i odszyfrowywania w programie .NET oraz zarządzania nimi.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET], keys
- symmetric keys
- asymmetric keys [.NET]
- cryptography [.NET], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
ms.openlocfilehash: aa95204a90f2aee684cdd20095d1816e890a0306
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831081"
---
# <a name="generating-keys-for-encryption-and-decryption"></a>Generowanie kluczy szyfrowania i odszyfrowywania
Tworzenie kluczy i zarządzanie nimi jest ważną częścią procesu kryptograficznego. Algorytmy symetryczne wymagają utworzenia klucza i wektora inicjalizacji (IV). Klucz musi być poufny dla każdego, kto nie powinien odszyfrować danych. IV nie musi być tajny, ale powinien zostać zmieniony dla każdej sesji. Algorytmy asymetryczne wymagają utworzenia klucza publicznego i klucza prywatnego. Klucz publiczny może być publiczny dla każdej osoby, natomiast klucz prywatny musi być znany tylko przez osobę, która będzie odszyfrować dane zaszyfrowane za pomocą klucza publicznego. W tej sekcji opisano, jak generować klucze dla algorytmów symetrycznych i asymetrycznych oraz zarządzać nimi.  
  
## <a name="symmetric-keys"></a>Klucze symetryczne  
 Klasy szyfrowania symetrycznego dostarczane przez platformę .NET wymagają klucza i nowego wektora inicjalizacji (IV) do szyfrowania i odszyfrowywania danych. Za każdym razem, gdy tworzysz nowe wystąpienie jednej z zarządzanych, symetryczne klasy kryptograficzne przy użyciu metody bez parametrów `Create()` , nowy klucz i IV są tworzone automatycznie. Każda osoba, która zezwoli na odszyfrowanie danych, musi mieć ten sam klucz i IV i korzystać z tego samego algorytmu. Ogólnie rzecz biorąc, należy utworzyć nowy klucz i IV dla każdej sesji, a klucz i IV nie powinny być przechowywane do użytku w późniejszej sesji.  
  
 Aby przekazać klucz symetryczny i IV do strony zdalnej, zazwyczaj należy zaszyfrować klucz symetryczny przy użyciu szyfrowania asymetrycznego. Wysyłanie klucza w niezabezpieczonej sieci bez szyfrowania jest niebezpieczne, ponieważ każdy z nich przechwytuje klucz i IV może odszyfrować dane.  
  
 W poniższym przykładzie pokazano Tworzenie nowego wystąpienia domyślnej klasy implementacji dla <xref:System.Security.Cryptography.Aes> algorytmu.  
  
```vb  
Dim aes As Aes = Aes.Create()  
```  
  
```csharp  
Aes aes = Aes.Create();  
```  
  
 Gdy poprzedni kod jest wykonywany, nowy klucz i IV są generowane i umieszczane odpowiednio w właściwościach **Key** i **IV** .  
  
 Czasami może być konieczne wygenerowanie wielu kluczy. W takiej sytuacji można utworzyć nowe wystąpienie klasy implementującej algorytm symetryczny, a następnie utworzyć nowy klucz i IV, wywołując metody **do generowania kluczy** i **GenerateIV** . Poniższy przykład kodu ilustruje sposób tworzenia nowych kluczy i użycie japońskich ideograficznych po wykonaniu nowego wystąpienia symetrycznej klasy kryptograficznej.  
  
```vb  
Dim aes As Aes = Aes.Create()  
aes.GenerateIV()  
aes.GenerateKey()  
```  
  
```csharp  
Aes aes = Aes.Create();  
aes.GenerateIV();  
aes.GenerateKey();  
```  
  
 Gdy poprzedni kod jest wykonywany, klucz i IV są generowane po wykonaniu nowego wystąpienia **algorytmu AES** . Po wywołaniu metod **do generowania kluczy** i **GenerateIV** są tworzone inne klucze i IV.
  
## <a name="asymmetric-keys"></a>Klucze asymetryczne

 Platforma .NET udostępnia <xref:System.Security.Cryptography.RSA> klasę do szyfrowania asymetrycznego. Ta klasa tworzy parę kluczy publicznych/prywatnych `Create()` w przypadku utworzenia nowego wystąpienia przy użyciu metody bez parametrów. Klucze asymetryczne mogą być przechowywane do użytku w wielu sesjach lub generowane tylko dla jednej sesji. Chociaż klucz publiczny można ogólnie udostępnić, klucz prywatny powinien być ściśle chroniony.  
  
 Para kluczy publiczny/prywatny jest generowana za każdym razem, gdy tworzone jest nowe wystąpienie klasy algorytmu asymetrycznego. Po utworzeniu nowego wystąpienia klasy można wyodrębnić informacje o kluczu przy użyciu <xref:System.Security.Cryptography.RSA.ExportParameters%2A> metody, która zwraca <xref:System.Security.Cryptography.RSAParameters> strukturę, która zawiera informacje o kluczu. Metoda przyjmuje wartość logiczną, która wskazuje, czy zwrócić tylko informacje o kluczu publicznym, czy zwrócić zarówno klucz publiczny, jak i informacje o kluczu prywatnym.

Istnieją również inne metody, które umożliwiają wyodrębnienie najważniejszych informacji, takich jak:

* <xref:System.Security.Cryptography.RSA.ExportRSAPublicKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.RSA.ExportRSAPrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportSubjectPublicKeyInfo%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportPkcs8PrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportEncryptedPkcs8PrivateKey%2A?displayProperty=nameWithType>

Wystąpienie **RSA** można zainicjować do wartości struktury **RSAParameters** przy użyciu <xref:System.Security.Cryptography.RSA.ImportParameters%2A> metody. Lub Utwórz nowe wystąpienie przy użyciu <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> metody.  
  
 Asymetryczne klucze prywatne nigdy nie powinny być przechowywane Verbatim ani w postaci zwykłego tekstu na komputerze lokalnym. Jeśli musisz przechować klucz prywatny, należy użyć kontenera kluczy. Aby uzyskać więcej informacji o tym, jak przechowywać klucz prywatny w kontenerze kluczy, zobacz [jak: przechowywanie kluczy asymetrycznych w kontenerze kluczy](how-to-store-asymmetric-keys-in-a-key-container.md).  
  
 Poniższy przykład kodu tworzy nowe wystąpienie klasy **RSA** , tworząc parę kluczy publiczny/prywatny i zapisuje informacje o kluczu publicznym do struktury **RSAParameters** .  
  
```vb  
'Generate a public/private key pair.  
Dim rsa as RSA = RSA.Create()  
'Save the public key information to an RSAParameters structure.  
Dim rsaKeyInfo As RSAParameters = rsa.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSA rsa = RSA.Create();  
//Save the public key information to an RSAParameters structure.  
RSAParameters rsaKeyInfo = rsa.ExportParameters(false);  
```  
  
## <a name="see-also"></a>Zobacz także

- [Szyfrowanie danych](encrypting-data.md)
- [Odszyfrowywanie danych](decrypting-data.md)
- [Usługi kryptograficzne](cryptographic-services.md)
- [Instrukcje: Przechowywanie kluczy asymetrycznych w kontenerze kluczy](how-to-store-asymmetric-keys-in-a-key-container.md)
- [Kryptografia międzyplatformowa](cross-platform-cryptography.md)
- [Ochrona danych ASP.NET Core](/aspnet/core/security/data-protection/introduction)
