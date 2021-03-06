---
title: Wiązania WCF (Windows Communication Foundation)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], bindings
- Windows Communication Foundation [WCF], bindings
- bindings [WCF]
ms.assetid: 83639133-89f7-43f0-b4ef-8d9e57c08d25
ms.openlocfilehash: 50c430489144589f6deb0930aeb3006bcb7efe8c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262102"
---
# <a name="windows-communication-foundation-bindings"></a>Wiązania WCF (Windows Communication Foundation)

Windows Communication Foundation (WCF) oddziela, w jaki sposób oprogramowanie aplikacji jest zapisywana z tego, jak komunikuje się z innym oprogramowaniem. Powiązania są używane do określania informacji o transportach, kodowaniu i protokole wymaganych przez klientów i usługi do komunikowania się ze sobą. Funkcja WCF używa powiązań do generowania wewnętrznej reprezentacji punktu końcowego, dlatego większość szczegółowych informacji o powiązaniach musi być uzgodniona przez strony, które komunikują się. Najprostszym sposobem osiągnięcia tej wartości jest to, że klienci usługi mogą używać tego samego powiązania, które jest używane przez punkt końcowy usługi. Aby uzyskać więcej informacji o tym, jak to zrobić, zobacz [using bindings to configure Services and clients](../using-bindings-to-configure-services-and-clients.md).  
  
 Powiązanie składa się z kolekcji elementów powiązania. Każdy element opisuje pewne aspekty, w jaki punkt końcowy komunikuje się z klientami. Powiązanie musi zawierać co najmniej jeden element powiązania transportu, co najmniej jeden element powiązania kodowania komunikatów (który może być udostępniany przez element powiązania transportu domyślnie) i dowolną liczbę innych elementów powiązania protokołu. Proces, który kompiluje środowisko uruchomieniowe z tego opisu, umożliwia każdemu elementowi powiązania, aby współtworzyć kod w tym środowisku uruchomieniowym.  
  
 Funkcja WCF oferuje powiązania zawierające typowe wybory elementów powiązania. Mogą one być używane z domyślnymi ustawieniami lub można modyfikować te wartości domyślne zgodnie z wymaganiami użytkownika. Te powiązania dostarczone przez system mają właściwości, które umożliwiają bezpośrednią kontrolę nad elementami powiązania i ich ustawieniami. Możesz również łatwo współpracować z wieloma wersjami powiązań, nadając każdej wersji powiązania swoją własną nazwę. Aby uzyskać szczegółowe informacje, zobacz [Konfigurowanie powiązań System-Provided](configuring-system-provided-bindings.md).  
  
 Jeśli potrzebujesz kolekcji elementów powiązania niedostarczonych przez jedno z tych powiązań dostarczonych przez system, możesz utworzyć niestandardowe powiązanie, które składa się z kolekcji wymaganych elementów powiązania. Te niestandardowe powiązania są łatwe do utworzenia i nie wymagają nowej klasy, ale nie zapewniają właściwości do kontrolowania elementów powiązania ani ich ustawień. Możesz uzyskać dostęp do elementów powiązania i zmodyfikować ich ustawienia za pomocą kolekcji, która je zawiera. Aby uzyskać szczegółowe informacje, zobacz [niestandardowe powiązania](../extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Konfigurowanie powiązań dostarczanych przez system](configuring-system-provided-bindings.md)  
 Opisuje, jak używać i modyfikować powiązania zapewniane przez WCF do obsługi typowych scenariuszy.  
  
 [Konfigurowanie usług i klientów za pomocą wiązań](../using-bindings-to-configure-services-and-clients.md)  
 Zawiera opis sposobu definiowania powiązań Windows Communication Foundation (WCF) dla usług i klientów w sposób niezbędny w kodzie i deklaratywnie korzystających z konfiguracji.  
  
 [Powiązania niestandardowe](../extending/custom-bindings.md)  
 Opisuje, co <xref:System.ServiceModel.Channels.CustomBinding> to jest i kiedy jest używany.  
  
## <a name="reference"></a>Dokumentacja  

 <xref:System.ServiceModel.Channels.Binding>  
  
 <xref:System.ServiceModel.Channels.BindingElement>  
  
 <xref:System.ServiceModel.Channels.CustomBinding>  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Rozszerzanie powiązań](../extending/extending-bindings.md)
