---
title: Weryfikacja nazw elementów i atrybutów XML podczas tworzenia nowych węzłów
ms.date: 03/30/2017
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
ms.openlocfilehash: 0678f7daf5276a905ce890a5f6a0f64993fb08b0
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828820"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>Weryfikacja nazw elementów i atrybutów XML podczas tworzenia nowych węzłów
Document Object Model XML (DOM) sprawdza poprawność nazw podczas tworzenia nowych węzłów elementów lub węzłów atrybutów. Jeśli nazwy zawierają niedozwolone znaki, zgłaszany jest wyjątek. Aby upewnić się, że nazwy są prawidłowe i zakodowane prawidłowo, należy użyć klasy **XmlConvert** do zakodowania nazwy i zdekodować ją z powrotem na poziomie aplikacji. Element **XmlWriter** ma metody, które wykonują dodatkowe zadania w celu zapewnienia, że generowany jest poprawnie sformułowany kod XML.  
  
## <a name="see-also"></a>Zobacz także

- [XML Document Object Model (DOM)](xml-document-object-model-dom.md)
