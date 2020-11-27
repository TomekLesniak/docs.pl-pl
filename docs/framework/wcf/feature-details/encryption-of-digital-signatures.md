---
title: Szyfrowanie podpisów cyfrowych
ms.date: 03/30/2017
helpviewer_keywords:
- encryption of digital signatures [WCF]
- digital signatures [WCF], encryption
- digital signatures [WCF]
ms.assetid: 0868866d-40b4-4341-8e42-eee3b7f15b69
ms.openlocfilehash: dece961ac70dbcf310e5e4a9dcb05c303c787ad4
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251441"
---
# <a name="encryption-of-digital-signatures"></a>Szyfrowanie podpisów cyfrowych

Domyślnie komunikat jest podpisany i szyfrowany, a podpis jest szyfrowany cyfrowo. Można to kontrolować przez utworzenie niestandardowego powiązania z wystąpieniem <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> lub, <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> a następnie ustawienie `MessageProtectionOrder` właściwości każdej klasy na <xref:System.ServiceModel.Security.MessageProtectionOrder> wartość wyliczenia. Wartość domyślna to <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>. Ten proces trwa od 10 do 40% dłużej niż po prostu podpisywanie i szyfrowanie. Wyłączenie szyfrowania podpisu może jednak umożliwić atakującemu odgadnięcie zawartości komunikatu. Jest to możliwe, ponieważ element Signature zawiera kod skrótu zwykłego tekstu każdej podpisanej części wiadomości. Na przykład mimo że treść komunikatu jest zaszyfrowana domyślnie, podpis niezaszyfrowany zawiera kod skrótu treści wiadomości. Jeśli komunikat jest mały, osoba atakująca może mieć możliwość wywnioskowania zawartości. Szyfrowanie podpisu jest ograniczone lub eliminuje tę możliwość.  
  
 W związku z tym należy wyłączyć szyfrowanie podpisu tylko wtedy, gdy wartość zawartości jest niska, a wzrost wydajności będzie znaczący, na przykład podczas wysyłania dużych plików binarnych, które nie mają wpływu na zabezpieczenia.  
  
### <a name="to-disable-digital-signing"></a>Aby wyłączyć podpisywanie cyfrowe  
  
1. Utwórz <xref:System.ServiceModel.Channels.CustomBinding> . Aby uzyskać więcej informacji, zobacz [jak: Tworzenie niestandardowego powiązania przy użyciu elementu SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
2. Dodaj albo <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> do kolekcji powiązań.  
  
3. Ustaw <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> Właściwość na wartość <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> lub ustaw <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement.MessageProtectionOrder%2A?displayProperty=nameWithType> Właściwość na <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> .  
  
 Aby uzyskać więcej informacji na temat tworzenia powiązań niestandardowych, zobacz [Tworzenie powiązań User-Defined](../extending/creating-user-defined-bindings.md). Aby uzyskać więcej informacji na temat tworzenia niestandardowego powiązania dla określonego trybu uwierzytelniania, zobacz [How to: Create a elementu SecurityBindingElement for a Authentication Mode dla określonego trybu uwierzytelniania](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md).  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Security.MessageProtectionOrder>
- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
- [Instrukcje: tworzenie niestandardowego wiązania za pomocą elementu SecurityBindingElement](how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [Tworzenie wiązań zdefiniowanych przez użytkownika](../extending/creating-user-defined-bindings.md)
- [Instrukcje: tworzenie elementu SecurityBindingElement dla określonego trybu uwierzytelniania](how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)
