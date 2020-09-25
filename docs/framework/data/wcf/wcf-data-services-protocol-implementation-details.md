---
title: Szczegóły implementacji protokołu usługi danych WCF
ms.date: 03/30/2017
ms.assetid: 712d689b-fada-4cbb-bcdb-d65a3ef83b4c
ms.openlocfilehash: 0723d5a473bb87b8bd464a944a5c68f1a8d3f5da
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202165"
---
# <a name="wcf-data-services-protocol-implementation-details"></a>Szczegóły implementacji protokołu usługi danych WCF

## <a name="odata-protocol-implementation-details"></a>Szczegóły implementacji protokołu OData  

Protokół Open Data Protocol (OData) wymaga, aby usługa danych implementująca protokół zapewniała określony minimalny zestaw funkcji. Te funkcje są opisane w dokumentach protokołu pod warunkiem "powinien" i "musi". Inne opcjonalne funkcje są opisane w części "mogą". W tym artykule opisano te opcjonalne funkcje, które nie są obecnie zaimplementowane przez Usługi danych programu WCF.
  
### <a name="support-for-the-format-query-option"></a>Obsługa opcji zapytania $format  

 Protokół OData obsługuje notację JavaScript (JSON) i kanały informacyjne Atom, a usługa OData udostępnia `$format` opcję kwerendy systemowej, aby umożliwić klientowi zażądanie formatu kanału informacyjnego odpowiedzi. Ta opcja kwerendy systemowej, jeśli jest obsługiwana przez usługę danych, musi zastąpić wartość nagłówka Accept żądania. Usługi danych programu WCF obsługuje Zwracanie danych JSON i Atom. Jednak implementacja domyślna nie obsługuje `$format` opcji zapytania i używa tylko wartości nagłówka Accept, aby określić format odpowiedzi. Istnieją przypadki, w których usługa danych może potrzebować obsługi `$format` opcji zapytania, na przykład gdy klienci nie mogą ustawić nagłówka Accept. Aby obsługiwać te scenariusze, należy rozłożyć usługę danych w celu obsługi tej opcji w identyfikatorze URI. Możesz dodać tę funkcję do usługi danych, pobierając [obsługę formatu JSONP i z obsługą adresu URL dla ADO.NET Data Services](https://go.microsoft.com/fwlink/?LinkId=208228) przykładowego projektu z witryny sieci Web galerii kodu MSDN i dodając go do projektu usługi danych. Ten przykład umożliwia usunięcie `$format` opcji zapytania i zmianę nagłówka Accept na `application/json` . Po dołączeniu przykładowego projektu i dodanie `JSONPSupportBehaviorAttribute` do klasy usługi danych umożliwia obsługę `$format` opcji zapytania przez usługę `$format=json` . Dalsze dostosowanie tego przykładowego projektu jest wymagane do obsługi `$format=atom` lub innych formatów niestandardowych.  
  
## <a name="wcf-data-services-behaviors"></a>Zachowania Usługi danych programu WCF  

 Następujące zachowania Usługi danych programu WCF nie są jawnie zdefiniowane przez Protokół OData:  
  
### <a name="default-sorting-behavior"></a>Domyślne zachowanie sortowania  

 Gdy żądanie zapytania wysyłane do usługi danych zawiera `$top` lub `$skip` Opcja zapytania systemowego i nie obejmuje `$orderby` opcji zapytania systemowego, zwracane źródło jest sortowane według właściwości klucza w kolejności rosnącej. Wynika to z tego, że kolejność jest wymagana w celu zapewnienia poprawnego stronicowania wyników. W tym celu usługa danych dodaje do zapytania wyrażenie porządkowania. To zachowanie występuje również, gdy w usłudze danych jest włączone stronicowanie oparte na serwerze. Aby uzyskać więcej informacji, zobacz [Konfigurowanie usługi danych](configuring-the-data-service-wcf-data-services.md). Aby sterować kolejnością zwracanego kanału informacyjnego, należy uwzględnić `$orderby` w identyfikatorze URI zapytania.  
  
## <a name="see-also"></a>Zobacz też

- [Definiowanie usług danych WCF](defining-wcf-data-services.md)
- [Biblioteka klienta usług danych WCF](wcf-data-services-client-library.md)
