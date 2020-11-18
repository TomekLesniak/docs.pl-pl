---
title: 'Instrukcje: Dostęp do sprzętowych urządzeń szyfrujących'
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encryption
- key card
- cryptography
- hardware encryption
- CspParameters
ms.assetid: b0e734df-6eb4-4b16-b48c-6f0fe82d5f17
ms.openlocfilehash: c4f0b77985dea1818729af41b69a4a7d30427415
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829898"
---
# <a name="how-to-access-hardware-encryption-devices"></a>Instrukcje: Dostęp do sprzętowych urządzeń szyfrujących

> [!NOTE]
> Ten artykuł dotyczy systemu Windows.

<xref:System.Security.Cryptography.CspParameters>Aby uzyskać dostęp do urządzeń do szyfrowania sprzętu, można użyć klasy. Na przykład można użyć tej klasy do zintegrowania aplikacji z kartą inteligentną, generatorem losowych liczb sprzętowych lub sprzętową implementacją określonego algorytmu kryptograficznego.  

<xref:System.Security.Cryptography.CspParameters>Klasa tworzy dostawcę usług kryptograficznych (CSP), który uzyskuje dostęp do prawidłowo zainstalowanego urządzenia szyfrującego sprzęt.  Dostępność dostawcy CSP można sprawdzić, sprawdzając następujący klucz rejestru przy użyciu Edytora rejestru (Regedit.exe): HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.  
  
### <a name="to-sign-data-using-a-key-card"></a>Aby podpisać dane przy użyciu karty klucza  
  
1. Utwórz nowe wystąpienie <xref:System.Security.Cryptography.CspParameters> klasy, przekazując typ dostawcy integer i nazwę dostawcy do konstruktora.  
  
2. Przekaż odpowiednie flagi do <xref:System.Security.Cryptography.CspParameters.Flags%2A> właściwości nowo utworzonego <xref:System.Security.Cryptography.CspParameters> obiektu.  Na przykład, Przekaż <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer> flagę.  
  
3. Utwórz nowe wystąpienie <xref:System.Security.Cryptography.AsymmetricAlgorithm> klasy (na przykład <xref:System.Security.Cryptography.RSACryptoServiceProvider> klasy), przekazując <xref:System.Security.Cryptography.CspParameters> obiekt do konstruktora.  
  
4. Podpisz swoje dane przy użyciu jednej z `Sign` metod i sprawdź swoje dane przy użyciu jednej z `Verify` metod.  
  
### <a name="to-generate-a-random-number-using-a-hardware-random-number-generator"></a>Aby wygenerować liczbę losową przy użyciu generatora liczb losowych sprzętowych  
  
1. Utwórz nowe wystąpienie <xref:System.Security.Cryptography.CspParameters> klasy, przekazując typ dostawcy integer i nazwę dostawcy do konstruktora.  
  
2. Utwórz nowe wystąpienie <xref:System.Security.Cryptography.RNGCryptoServiceProvider> , przekazując <xref:System.Security.Cryptography.CspParameters> obiekt do konstruktora.  
  
3. Utwórz wartość losową przy użyciu <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A> metody lub.  
  
## <a name="example"></a>Przykład

Poniższy przykład kodu demonstruje sposób podpisywania danych przy użyciu karty inteligentnej.  Przykładowy kod tworzy <xref:System.Security.Cryptography.CspParameters> obiekt, który uwidacznia kartę inteligentną, a następnie inicjuje <xref:System.Security.Cryptography.RSACryptoServiceProvider> Obiekt przy użyciu dostawcy CSP.  Przykład kodu następnie podpisuje i weryfikuje niektóre dane.  

Ze względu na kolizje problemów z algorytmem SHA1 zalecamy SHA256 lub lepszą.
  
[!code-cpp[Cryptography.SmartCardCSP#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CPP/Cryptography.SmartCardCSP.cpp#1)]
[!code-csharp[Cryptography.SmartCardCSP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CS/example.cs#1)]
[!code-vb[Cryptography.SmartCardCSP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Cryptography.SmartCardCSP/VB/example.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  
  
- Uwzględnij <xref:System> <xref:System.Security.Cryptography> przestrzenie nazw i.  
  
- Na komputerze musi być zainstalowany czytnik kart inteligentnych i sterowniki.  
  
- Należy zainicjować <xref:System.Security.Cryptography.CspParameters> Obiekt przy użyciu informacji specyficznych dla czytnika kart.  Aby uzyskać więcej informacji, zobacz dokumentację czytnika kart.

## <a name="see-also"></a>Zobacz także

- [Model kryptografii](cryptography-model.md)
- [Usługi kryptograficzne](cryptographic-services.md)
- [Kryptografia międzyplatformowa](cross-platform-cryptography.md)
- [Ochrona danych ASP.NET Core](/aspnet/core/security/data-protection/introduction)
