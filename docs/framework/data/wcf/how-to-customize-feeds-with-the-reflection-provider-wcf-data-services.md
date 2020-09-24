---
title: 'Instrukcje: Dostosowywanie kanałów informacyjnych za pomocą dostawcy odbicia (Usługi danych programu WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
ms.openlocfilehash: fb22e87569a8e243813b3186232b6989abeb2a5e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161311"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a>Instrukcje: Dostosowywanie kanałów informacyjnych za pomocą dostawcy odbicia (Usługi danych programu WCF)

Usługi danych programu WCF umożliwia dostosowanie serializacji Atom w odpowiedzi usługi danych, tak aby właściwości jednostki mogły być mapowane do nieużywanych elementów, które są zdefiniowane w protokole AtomPub. W tym temacie przedstawiono sposób definiowania atrybutów mapowania dla typów jednostek w modelu danych, który jest zdefiniowany przy użyciu dostawcy odbicia. Aby uzyskać więcej informacji, zobacz temat [Dostosowywanie kanału informacyjnego](feed-customization-wcf-data-services.md).  
  
 Model danych dla tego przykładu został zdefiniowany w temacie [jak: Tworzenie usługi danych przy użyciu dostawcy odbicia](create-a-data-service-using-rp-wcf-data-services.md)  
  
## <a name="example"></a>Przykład  

 W poniższym przykładzie obie właściwości `Order` typu są mapowane na istniejące elementy Atom. `Product`Właściwość `Item` typu jest zamapowana na atrybut niestandardowego kanału informacyjnego w oddzielnym obszarze nazw.  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a>Przykład  

 Poprzedni przykład zwraca Poniższy wynik dla identyfikatora URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items` .  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a>Zobacz też

- [Dostawca odbicia](reflection-provider-wcf-data-services.md)
