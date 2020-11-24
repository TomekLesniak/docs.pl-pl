---
title: Zachowane odwołania do jednostek
ms.date: 03/30/2017
ms.assetid: 000a6cae-5972-40d6-bd6c-a9b7d9649b3c
ms.openlocfilehash: 484eb5c874c6de05acae7dcd87a477c186b81482
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687271"
---
# <a name="entity-references-are-preserved"></a>Zachowane odwołania do jednostek

Gdy odwołanie do jednostki nie jest rozwinięte, ale zachowane, Document Object Model XML (DOM) kompiluje węzeł **XmlEntityReference** , gdy napotka odwołanie do jednostki.  
  
 Przy użyciu następującego kodu XML  
  
```xml  
<author>Fred</author>  
<pubinfo>Published by &publisher;</pubinfo>  
```  
  
 DOM kompiluje węzeł **XmlEntityReference** , gdy napotka `&publisher;` odwołanie. **XmlEntityReference** zawiera węzły podrzędne skopiowane z zawartości w deklaracji jednostki. Poprzedni przykład kodu zawiera tekst w deklaracji jednostki, więc węzeł **XmlText** jest tworzony jako węzeł podrzędny węzła odwołania do jednostki.  
  
 ![Struktura drzewa dla zachowanych odwołań do jednostek](media/xmlentityref-notexpanded-nodes.gif "xmlentityref_notexpanded_nodes")  
Struktura drzewa dla odwołań do jednostek, które są zachowywane  
  
 Węzły podrzędne klasy **XmlEntityReference** są kopiami wszystkich węzłów podrzędnych utworzonych na podstawie węzła **XmlEntity** podczas napotkania deklaracji jednostki.  
  
> [!NOTE]
> Węzły skopiowane z elementu **XmlEntity** nie zawsze są wiernie kopiowane po umieszczeniu ich w węźle odwołania do jednostki. Mogą istnieć przestrzenie nazw, które znajdują się w zakresie w węźle odwołania do jednostki i mają wpływ na ostateczną konfigurację węzłów podrzędnych.  
  
 Domyślnie obiekty ogólne, takie jak `&abc;` są zachowywane, i węzły **XmlEntityReference** są zawsze tworzone.  
  
## <a name="see-also"></a>Zobacz także

- [XML Document Object Model (DOM)](xml-document-object-model-dom.md)
