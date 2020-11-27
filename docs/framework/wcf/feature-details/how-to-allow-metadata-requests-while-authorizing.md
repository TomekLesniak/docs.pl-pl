---
title: 'Instrukcje: zezwalanie na żądania metadanych podczas autoryzowania'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- allowing metadata requests while authorizing [WCF]
ms.assetid: 90cec34f-b619-452b-a056-8b1c0de49d05
ms.openlocfilehash: 9acc007ea7837f7b8e6c958fa81547fe4fa5b2c0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257616"
---
# <a name="how-to-allow-metadata-requests-while-authorizing"></a>Instrukcje: zezwalanie na żądania metadanych podczas autoryzowania

W trakcie autoryzacji niestandardowej może być konieczne zezwolenie na przetworzenie żądania metadanych. W poniższym temacie przedstawiono kroki umożliwiające zweryfikowanie takiego żądania.  
  
 Aby uzyskać więcej informacji na temat autoryzacji Windows Communication Foundation (WCF), zobacz [autoryzacja](authorization-in-wcf.md).  
  
### <a name="to-allow-metadata-requests-during-authorization"></a>Aby zezwolić na żądania metadanych podczas autoryzacji  
  
1. Utwórz rozszerzenie <xref:System.ServiceModel.ServiceAuthorizationManager> klasy.  
  
2. Zastąp <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> metodę. Metoda zwraca `true` lub `false` w zależności od tego, czy Autoryzacja jest dozwolona. Informacje na temat bieżącej procedury znajdują się w <xref:System.ServiceModel.OperationContext> przekazaniu jako parametr do metody.  
  
3. W przesłonięciu Sprawdź nazwę kontraktu, przestrzeń nazw i akcję, jak pokazano w poniższym przykładzie. Jeśli warunki są prawidłowe, Wróć `true.`  
  
4. Użyj punktu rozszerzalności, aby użyć klasy. Aby uzyskać więcej informacji, zobacz [jak: Tworzenie niestandardowego Menedżera autoryzacji dla usługi](../extending/how-to-create-a-custom-authorization-manager-for-a-service.md).  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie pokazano przesłonięcie <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> metody.  
  
 [!code-csharp[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/cs/source.cs#1)]
 [!code-vb[C_HowtoCheckForMexRequestsInAuthorization#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtocheckformexrequestsinauthorization/vb/source.vb#1)]  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [Autoryzacja](authorization-in-wcf.md)
- [Zarządzanie oświadczeniami i autoryzacją za pomocą modelu tożsamości](managing-claims-and-authorization-with-the-identity-model.md)
