---
title: 'Instrukcje: używanie krótkiej nazwy usługi z kontraktami WSDL'
ms.date: 03/30/2017
ms.assetid: a88d9650-bb50-4f48-8c85-12f5ce98a83a
ms.openlocfilehash: 6b1a6c905008b0232a098f253b9007e5147d71a2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280887"
---
# <a name="how-to-use-a-service-moniker-with-wsdl-contracts"></a>Instrukcje: używanie krótkiej nazwy usługi z kontraktami WSDL

Istnieją sytuacje, w których można chcieć korzystać z całkowicie niezależnego klienta międzyoperacyjnego modelu COM. Usługa, która ma zostać wywołana, może nie ujawniać punktu końcowego MEX, a Biblioteka DLL klienta WCF nie może być zarejestrowana na potrzeby współdziałania z modelem COM. W takich przypadkach można utworzyć plik WSDL opisujący usługę i przekazać go do monikera usługi WCF. W tym temacie opisano sposób wywoływania przykładu Wprowadzenie WCF przy użyciu monikera WSDL programu WCF.  
  
### <a name="using-the-wsdl-service-moniker"></a>Używanie monikera usługi WSDL  
  
1. Otwórz i skompiluj przykładowe rozwiązanie GettingStarted.  
  
2. Otwórz program Internet Explorer i przejdź do programu `http://localhost/ServiceModelSamples/Service.svc` , aby upewnić się, że usługa działa.  
  
3. W pliku Service.cs Dodaj następujący atrybut klasy CalculatorService:  
  
     [!code-csharp[S_WSDL_Client#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wsdl_client/cs/service.cs#0)]  
  
4. Dodaj przestrzeń nazw powiązania do App.config usługi:  

5. Utwórz plik WSDL, aby można było odczytać aplikację. Ponieważ przestrzenie nazw zostały dodane w krokach 3 i 4, można użyć programu IE do zapytania o cały opis WSDL usługi, przechodząc do tematu `http://localhost/ServiceModelSamples/Service.svc?wsdl` . Następnie można zapisać plik z programu Internet Explorer jako serviceWSDL.xml. Jeśli nie określisz przestrzeni nazw w krokach 3 i 4, dokument WSDL zwrócony z zapytania o powyższy adres URL nie będzie kompletny w języku WSDL. Zwrócony dokument WSDL będzie zawierać kilka instrukcji importu, które zaimportują inne dokumenty WSDL. Trzeba będzie przejść przez każdą instrukcję importu i utworzyć kompletny dokument WSDL, łącząc element WSDL zwrócony z usługi z zaimportowanym WSDL.  
  
6. Otwórz Visual Basic 6,0 i Utwórz nowy plik w standardowym pliku. exe. Dodaj przycisk do formularza i kliknij dwukrotnie przycisk, aby dodać następujący kod do procedury obsługi kliknięcia:  
  
    ```vb
    ' Open the WSDL contract file and read it all into the wsdlContract string.  
    Const ForReading = 1  
    Set objFSO = CreateObject("Scripting.FileSystemObject")  
    Set objFile = objFSO.OpenTextFile("c:\serviceWsdl.xml", ForReading)  
    wsdlContract = objFile.ReadAll  
    objFile.Close  
  
    ' Create a string for the service moniker including the content of the WSDL contract file.  
    wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
    wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
    wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
    wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
    ' Create the service moniker object.  
    Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
  
    ' Call the service operations using the moniker object.  
    MsgBox "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
    ```  
  
    > [!NOTE]
    > Jeśli moniker jest źle sformułowany lub usługa jest niedostępna, wywołanie zwróci `GetObject` błąd mówiąc "Nieprawidłowa składnia".  Jeśli wystąpi ten błąd, upewnij się, że moniker, którego używasz, jest poprawna i że usługa jest dostępna.  
  
7. Uruchom aplikację Visual Basic. Zostanie wyświetlone okno komunikatu z wynikami wywoływania odejmowania (145, 76,54).  
  
## <a name="see-also"></a>Zobacz też

- [Wprowadzenie](../samples/getting-started-sample.md)
- [Przegląd integrowania z aplikacjami modelu COM](integrating-with-com-applications-overview.md)
