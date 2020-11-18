---
title: Zapewnianie integralności danych za pomocą wartości skrótu
description: Dowiedz się, jak zapewnić integralność danych przy użyciu kodów skrótu w programie .NET. Wartość skrótu to wartość liczbowa o stałej długości, która jednoznacznie identyfikuje dane.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generating hash
- verifying hash codes
- cryptography [.NET], hash
- data integrity
- checking hash codes
- encryption [.NET], hash
- hash
ms.assetid: 33660f33-b70f-4dca-8c87-ab35cfc2961a
ms.openlocfilehash: 085a0ea387e3415e6e916bcdf9055ffaa6753fef
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831094"
---
# <a name="ensuring-data-integrity-with-hash-codes"></a>Zapewnianie integralności danych za pomocą wartości skrótu
Wartość skrótu to wartość liczbowa o stałej długości, która jednoznacznie identyfikuje dane. Wartości skrótu przedstawiają duże ilości danych jako dużo mniejsze wartości liczbowe, dlatego są używane z podpisami cyfrowymi. Wartość skrótu można podpisywać bardziej wydajnie niż podpisywanie większej wartości. Wartości skrótu są również przydatne do sprawdzania integralności danych wysyłanych za pomocą niezabezpieczonych kanałów. Wartość skrótu odebranych danych może być porównywana z wartością skrótu danych, która została wysłana w celu określenia, czy dane zostały zmienione.  
  
W tym temacie opisano sposób generowania i weryfikowania kodów skrótów przy użyciu klas w <xref:System.Security.Cryptography> przestrzeni nazw.  
  
## <a name="generating-a-hash"></a>Generowanie skrótu

 Zarządzane klasy skrótów mogą mieszać tablicę bajtów lub obiekt strumienia zarządzanego. W poniższym przykładzie jest używany algorytm skrótu SHA1 do tworzenia wartości skrótu dla ciągu. W przykładzie użyto <xref:System.Text.UnicodeEncoding> klasy do przekonwertowania ciągu na tablicę bajtów, które są zmieszane przy użyciu <xref:System.Security.Cryptography.SHA256> klasy. Wartość skrótu zostanie następnie wyświetlona w konsoli programu.  

 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 Ten kod będzie wyświetlał następujący ciąg do konsoli:  
  
 `185 203 236 22 3 228 27 130 87 23 244 15 87 88 14 43 37 61 106 224 81 172 224 211 104 85 194 197 194 25 120 217`  
  
## <a name="verifying-a-hash"></a>Weryfikowanie skrótu

 Dane można porównać do wartości skrótu, aby określić jej integralność. Zwykle dane są zmieszane w określonym czasie, a wartość skrótu jest chroniona w jakiś sposób. Później można ponownie wykonać mieszanie danych i porównywać ją z wartością chronioną. W przypadku dopasowania wartości skrótu dane nie zostały zmienione. Jeśli wartości nie są zgodne, dane zostały uszkodzone. Aby ten system działał, chroniony skrót musi być zaszyfrowany lub przechowywany jako wpis tajny ze wszystkich niezaufanych stron.  
  
 Poniższy przykład porównuje poprzednią wartość skrótu ciągu z nową wartością skrótu. Ten przykład powoduje pętlę przez każdy bajt wartości skrótu i wykonuje porównanie.  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 Jeśli dwie wartości skrótów są zgodne, ten kod wyświetla następujące polecenie w konsoli programu:  
  
```console  
The hash codes match.  
```  
  
 Jeśli nie są zgodne, kod wyświetla następujące elementy:  
  
```console  
The hash codes do not match.  
```  
  
## <a name="see-also"></a>Zobacz także

- [Model kryptografii](cryptography-model.md)
- [Usługi kryptograficzne](cryptographic-services.md)
- [Kryptografia międzyplatformowa](cross-platform-cryptography.md)
- [Ochrona danych ASP.NET Core](/aspnet/core/security/data-protection/introduction)
