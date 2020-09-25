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

<span data-ttu-id="02c35-101">`commonBehaviors`Sekcję można zdefiniować tylko w pliku machine.config.</span><span class="sxs-lookup"><span data-stu-id="02c35-101">The `commonBehaviors` section can only be defined in the machine.config file.</span></span> <span data-ttu-id="02c35-102">Definiuje dwie kolekcje podrzędne o nazwach `endpointBehaviors` i `serviceBehaviors` .</span><span class="sxs-lookup"><span data-stu-id="02c35-102">It defines two child collections named `endpointBehaviors` and `serviceBehaviors`.</span></span>  <span data-ttu-id="02c35-103">Każda kolekcja definiuje elementy zachowań używane przez wszystkie punkty końcowe i usługi WCF odpowiednio na maszynie.</span><span class="sxs-lookup"><span data-stu-id="02c35-103">Each collection defines behavior elements consumed by all WCF endpoints and services on the machine respectively.</span></span> <span data-ttu-id="02c35-104">Zachowania zdefiniowane w programie `endpointBehaviors` są stosowane tylko do klientów, a zachowania zdefiniowane w programie `serviceBehaviors` są stosowane tylko do usług.</span><span class="sxs-lookup"><span data-stu-id="02c35-104">Behaviors defined in `endpointBehaviors` are only applied to clients, and behaviors defined in `serviceBehaviors` are only applied to services.</span></span> <span data-ttu-id="02c35-105">Jeśli zachowanie jest zdefiniowane w obu `commonBehaviors` `behaviors` sekcjach, zachowanie w `behaviors` sekcji ma pierwszeństwo.</span><span class="sxs-lookup"><span data-stu-id="02c35-105">If a behavior is defined in both `commonBehaviors` and `behaviors` sections, the behavior in the `behaviors` section is given preference.</span></span>
