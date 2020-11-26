---
title: 'Instrukcje: tworzenie niestandardowej tożsamości podmiotu zabezpieczeń'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IPrincipal
- IAuthorizationPolicy
- PrincipalPermissionMode
- PrincipalPermissionAttribute
ms.assetid: c4845fca-0ed9-4adf-bbdc-10812be69b61
ms.openlocfilehash: 6c50d6b0ac2baa2dc61431af4afb8dca3860456a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249309"
---
# <a name="how-to-create-a-custom-principal-identity"></a>Instrukcje: tworzenie niestandardowej tożsamości podmiotu zabezpieczeń

<xref:System.Security.Permissions.PrincipalPermissionAttribute>Jest deklaratywnym sposobem kontrolowania dostępu do metod usługi. W przypadku korzystania z tego atrybutu <xref:System.ServiceModel.Description.PrincipalPermissionMode> Wyliczenie określa tryb wykonywania kontroli autoryzacji. Gdy ten tryb jest ustawiony na <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> , umożliwia użytkownikowi określenie <xref:System.Security.Principal.IPrincipal> klasy niestandardowej zwracanej przez <xref:System.Threading.Thread.CurrentPrincipal%2A> Właściwość. W tym temacie przedstawiono scenariusz, gdy <xref:System.ServiceModel.Description.PrincipalPermissionMode.Custom> jest używany w połączeniu z niestandardowymi zasadami autoryzacji i niestandardowym podmiotem zabezpieczeń.  
  
 Aby uzyskać więcej informacji o używaniu programu <xref:System.Security.Permissions.PrincipalPermissionAttribute> , zobacz [How to: ograniczanie dostępu za pomocą klasy PrincipalPermissionAttribute](../how-to-restrict-access-with-the-principalpermissionattribute-class.md).  
  
## <a name="example"></a>Przykład  

 [!code-csharp[PrincipalPermissionMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/principalpermissionmode/cs/source.cs#8)]
 [!code-vb[PrincipalPermissionMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/principalpermissionmode/vb/source.vb#8)]  
  
## <a name="compiling-the-code"></a>Kompilowanie kodu  

 Do kompilowania kodu są konieczne odwołania do następujących przestrzeni nazw:  
  
- <xref:System>  
  
- <xref:System.Collections.Generic>  
  
- <xref:System.Security.Permissions>  
  
- <xref:System.Security.Principal>  
  
- <xref:System.Threading>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.ServiceModel.Channels>  
  
- <xref:System.ServiceModel.Description>  
  
- <xref:System.IdentityModel.Claims>  
  
- <xref:System.IdentityModel.Policy>  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Description.PrincipalPermissionMode>
- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [Instrukcje: używanie dostawcy ról ASP.NET razem z usługą](../feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [Instrukcje: Ograniczanie dostępu przy użyciu klasy PrincipalPermissionAttribute](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)
