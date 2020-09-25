---
title: 'Instrukcje: Dostosowywanie zachowań powiązań danych (Usługi danych programu WCF)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, data binding
ms.assetid: 40476b89-8941-4771-8d21-2fe430c85a9d
ms.openlocfilehash: 13847923a5f31108e93ef12cf7775109be3cd9eb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172518"
---
# <a name="how-to-customize-data-binding-behaviors-wcf-data-services"></a>Instrukcje: Dostosowywanie zachowań powiązań danych (Usługi danych programu WCF)

Za pomocą Usługi danych programu WCF można dostarczyć logiki niestandardowej, która jest wywoływana przez, <xref:System.Data.Services.Client.DataServiceCollection%601> gdy obiekt jest dodawany lub usuwany z kolekcji powiązań lub gdy zostanie wykryta zmiana właściwości. Ta logika niestandardowa jest udostępniana jako metody, przywoływane jako <xref:System.Func%602> Delegaty, która zwraca wartość, `false` gdy zachowanie domyślne nadal powinno być wykonywane, gdy metoda niestandardowa zostanie zakończona, a `true` następne przetwarzanie zdarzenia powinno zostać zatrzymane.  
  
 Przykłady w tym temacie dostarczają niestandardowe metody dla obu `entityChanged` `entityCollectionChanged` parametrów i <xref:System.Data.Services.Client.DataServiceCollection%601> . Przykłady w tym temacie wykorzystują przykładową usługę danych Northwind i automatycznie wygenerowaną klasę usługi danych klienta. Ta usługa i klasy danych klienta są tworzone po zakończeniu [usługi danych programu WCF szybkiego startu](quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Przykład  

 Następująca Strona związana z kodem dla pliku XAML tworzy <xref:System.Data.Services.Client.DataServiceCollection%601> metody z metodami niestandardowymi, które są wywoływane, gdy wystąpią zmiany danych powiązanych z kolekcją powiązań. Gdy <xref:System.Collections.ObjectModel.ObservableCollection%601.CollectionChanged> wystąpi zdarzenie, podaną metodę uniemożliwiają usunięcie elementu z kolekcji powiązań z usługi danych. Gdy <xref:System.Collections.ObjectModel.ObservableCollection%601.PropertyChanged> wystąpi zdarzenie, `ShipDate` wartość zostanie sprawdzona, aby upewnić się, że zmiany nie zostały wprowadzone do już dostarczonych zamówień.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#wpfdatabindingcustom)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingCustom](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#wpfdatabindingcustom)]  
  
## <a name="example"></a>Przykład  

 Poniższy kod XAML definiuje okno dla poprzedniego przykładu.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingCustomXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml#wpfdatabindingcustomxaml)]  
  
## <a name="see-also"></a>Zobacz też

- [Biblioteka klienta usług danych WCF](wcf-data-services-client-library.md)
