---
title: 'Instrukcje: Określanie powiązań usługi w kodzie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 67ab5dd8-79c1-4e62-aa75-828ea918a53a
ms.openlocfilehash: 7cf54754661182dca1e91c75b158d9b0a34a1f5e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236484"
---
# <a name="how-to-specify-a-service-binding-in-code"></a>Instrukcje: Określanie powiązań usługi w kodzie

W tym przykładzie `ICalculator` jest definiowana umowa dla usługi kalkulatora, usługa jest zaimplementowana w `CalculatorService` klasie, a następnie jej punkt końcowy jest zdefiniowany w kodzie, w którym jest określony, że usługa musi używać <xref:System.ServiceModel.BasicHttpBinding> klasy.  
  
 Zazwyczaj najlepszym rozwiązaniem jest określenie informacji o powiązaniach i adresie w konfiguracji, a nie w sposób konieczny w kodzie. Definiowanie punktów końcowych w kodzie zazwyczaj nie jest praktyczne, ponieważ powiązania i adresy dla wdrożonej usługi są zwykle inne niż te używane podczas tworzenia usługi. Ogólnie rzecz biorąc, przechowywanie informacji o powiązaniach i adresach poza kodem pozwala na ich zmianę bez konieczności ponownego kompilowania lub wdrażania aplikacji.  
  
 Opis sposobu konfigurowania tej usługi przy użyciu elementów konfiguracji zamiast kodu znajduje się [w temacie How to: Określanie powiązania usługi w konfiguracji](how-to-specify-a-service-binding-in-configuration.md).  
  
### <a name="to-specify-in-code-to-use-the-basichttpbinding-for-the-service"></a>Aby określić w kodzie, aby użyć BasicHttpBinding dla usługi  
  
1. Zdefiniuj kontrakt usługi dla typu usługi.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_CodeServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#1)]  
  
2. Zaimplementuj kontrakt usługi w klasie usługi.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_CodeServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#2)]  
  
3. W aplikacji hostingowej Utwórz adres podstawowy usługi i powiązanie, które ma być używane z usługą.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#3)]
     [!code-vb[C_HowTo_CodeServiceBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#3)]  
  
4. Utwórz hosta dla usługi, Dodaj punkt końcowy, a następnie otwórz hosta.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#4)]
     [!code-vb[C_HowTo_CodeServiceBinding#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#4)]  
  
### <a name="to-modify-the-default-values-of-the-binding-properties"></a>Aby zmodyfikować wartości domyślne właściwości powiązania  
  
1. Aby zmodyfikować jedną z domyślnych wartości właściwości <xref:System.ServiceModel.BasicHttpBinding> klasy, przed utworzeniem hosta ustaw wartość właściwości w powiązaniu z nową wartością. Na przykład aby zmienić domyślne wartości limitu czasu otwarcia i zamknięcia wynoszące 1 minutę na 2 minuty, użyj poniższego.  
  
     [!code-csharp[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeservicebinding/cs/source.cs#5)]
     [!code-vb[C_HowTo_CodeServiceBinding#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeservicebinding/vb/source.vb#5)]  
  
## <a name="see-also"></a>Zobacz też

- [Konfigurowanie usług i klientów za pomocą wiązań](using-bindings-to-configure-services-and-clients.md)
- [Określanie adresu punktu końcowego](specifying-an-endpoint-address.md)
