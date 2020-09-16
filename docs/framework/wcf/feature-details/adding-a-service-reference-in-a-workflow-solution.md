---
title: Dodawanie odwołania do usługi w rozwiązaniu usprawniającym przepływ pracy
ms.date: 03/30/2017
ms.assetid: 83574cf3-9803-49bc-837f-432936dc9c76
ms.openlocfilehash: 1b4cc16d3bd85c28ac7267e88ae0a714620c9861
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557061"
---
# <a name="add-a-service-reference-in-a-workflow-solution"></a>Dodawanie odwołania do usługi w rozwiązaniu przepływu pracy

Dodanie odwołania do usługi w aplikacji przepływu pracy działa nieco inaczej niż zwykła aplikacja WCF. Po wybraniu opcji **Dodaj**  >  **odwołanie do usługi** i określ adres URL usługi, metadane są pobierane i generowane są działania niestandardowe, które umożliwiają wywołanie tej usługi WCF lub usługi przepływu pracy WCF. Po dodaniu odwołania do usługi Skompiluj ponownie rozwiązanie, aby zostały skompilowane wygenerowane działania. Zostaną one wyświetlone w przyborniku projektanta przepływu pracy. Ta wartość będzie działała tylko w przypadku dodawania odwołania do usługi w ramach rozwiązania przepływu pracy. Poniższe Rzutowanie w sieci Web pokazuje, jak dodać odwołanie do usługi w innych typach projektów: [Wywoływanie usługi WCF z przepływu pracy w projekcie sieci Web](/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow).

Dodanie co najmniej dwóch odwołań do usług, które zawierają tę samą nazwę operacji, spowoduje wystąpienie problemu. Wygenerowane działania będą wywoływały tylko pierwszą operację usługi. Aby obejść ten problem, Zmień nazwy operacji usługi tak, aby były różne, lub Zmień nazwę konfiguracji punktu końcowego w ramach każdego wygenerowanego działania.

## <a name="see-also"></a>Zobacz także

- [Usługi przepływu pracy](workflow-services.md)
- [Wywoływanie usługi WCF z przepływu pracy w projekcie sieci Web](/archive/blogs/endpoint/how-to-consume-a-wcf-service-from-a-wf4-workflow)
