---
title: <commonBehaviors>
ms.date: 03/30/2017
ms.assetid: 5260aeca-388d-4e82-94c0-124fa8054cf5
ms.openlocfilehash: 55f70157b6759c5e1cb45da20eed928fa1d4a183
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176061"
---
# \<commonBehaviors>

`commonBehaviors`Sekcję można zdefiniować tylko w pliku machine.config. Definiuje dwie kolekcje podrzędne o nazwach `endpointBehaviors` i `serviceBehaviors` .  Każda kolekcja definiuje elementy zachowań używane przez wszystkie punkty końcowe i usługi WCF odpowiednio na maszynie. Zachowania zdefiniowane w programie `endpointBehaviors` są stosowane tylko do klientów, a zachowania zdefiniowane w programie `serviceBehaviors` są stosowane tylko do usług. Jeśli zachowanie jest zdefiniowane w obu `commonBehaviors` `behaviors` sekcjach, zachowanie w `behaviors` sekcji ma pierwszeństwo.
