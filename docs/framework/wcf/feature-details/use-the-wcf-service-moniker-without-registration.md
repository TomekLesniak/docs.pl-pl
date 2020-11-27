---
title: 'Instrukcje: używanie krótkiej nazwy programu Windows Communication Foundation bez rejestracji'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], service monikers without registration
ms.assetid: ee3cf5c0-24f0-4ae7-81da-73a60de4a1a8
ms.openlocfilehash: 41761313fae68a1a348a73f104e21dc19e07eb65
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293510"
---
# <a name="how-to-use-the-windows-communication-foundation-service-moniker-without-registration"></a><span data-ttu-id="53202-102">Instrukcje: używanie krótkiej nazwy programu Windows Communication Foundation bez rejestracji</span><span class="sxs-lookup"><span data-stu-id="53202-102">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>

<span data-ttu-id="53202-103">Aby nawiązać połączenie z usługą Windows Communication Foundation (WCF) i komunikować się z nią, aplikacja kliencka programu WCF musi mieć szczegóły dotyczące adresu usługi, konfiguracji powiązania i kontraktu usługi.</span><span class="sxs-lookup"><span data-stu-id="53202-103">To connect to and communicate with a Windows Communication Foundation (WCF) service, a WCF client application must have the details of the service address, the binding configuration, and the service contract.</span></span>  
  
 <span data-ttu-id="53202-104">Moniker usługi WCF zwykle uzyskuje wymagany kontrakt za pomocą wcześniejszej rejestracji wymaganych typów atrybutów, ale mogą wystąpić sytuacje, w których nie jest to możliwe.</span><span class="sxs-lookup"><span data-stu-id="53202-104">The WCF service moniker typically obtains the required contract through prior registration of the required attribute types, but there might be cases where this is not feasible.</span></span> <span data-ttu-id="53202-105">W miejscu rejestracji moniker może uzyskać definicję kontraktu w formie dokumentu języka definicji usług sieci Web (WSDL), poprzez użycie `wsdl` parametru lub za pomocą wymiany metadanych przy użyciu `mexAddress` parametru.</span><span class="sxs-lookup"><span data-stu-id="53202-105">In place of registration, the moniker can obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document, through the use of the `wsdl` parameter or through Metadata Exchange, through the use of the `mexAddress` parameter.</span></span>  
  
 <span data-ttu-id="53202-106">Pozwala to na takie scenariusze, jak dystrybucja arkusza kalkulacyjnego programu Excel, w którym niektóre wartości komórek są obliczane za pomocą interakcji usługi sieci Web.</span><span class="sxs-lookup"><span data-stu-id="53202-106">This enables scenarios such as the distribution of an Excel spreadsheet where some of the cell values are calculated through Web service interactions.</span></span> <span data-ttu-id="53202-107">W tym scenariuszu może nie być możliwe zarejestrowanie zestawu kontraktu usługi na wszystkich klientach, który może otworzyć ten dokument.</span><span class="sxs-lookup"><span data-stu-id="53202-107">In this scenario, it might not be feasible to register the service contract assembly on all clients that might open the document.</span></span> <span data-ttu-id="53202-108">`wsdl`Parametr lub `mexAddress` parametr włącza samodzielne rozwiązanie.</span><span class="sxs-lookup"><span data-stu-id="53202-108">The `wsdl` parameter or the `mexAddress` parameter enables a self-contained solution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53202-109">Wzajemne uwierzytelnianie musi być używane do ochrony przed manipulacjami lub fałszowaniem żądań i odpowiedzi.</span><span class="sxs-lookup"><span data-stu-id="53202-109">Mutual authentication must be used to protect against request and response tampering or spoofing.</span></span> <span data-ttu-id="53202-110">Szczególnie ważne jest, aby klienci mogli zapewnić, że punkt końcowy wymiany metadanych, który odpowiada, jest zamierzoną stroną zaufaną.</span><span class="sxs-lookup"><span data-stu-id="53202-110">Specifically, it is important for clients to be assured that the Metadata Exchange endpoint that is responding is the intended trusted party.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53202-111">Przykład</span><span class="sxs-lookup"><span data-stu-id="53202-111">Example</span></span>  

 <span data-ttu-id="53202-112">Ten przykład pokazuje użycie monikera usługi z kontraktem MEX.</span><span class="sxs-lookup"><span data-stu-id="53202-112">This example shows the use of the service moniker with a MEX contract.</span></span> <span data-ttu-id="53202-113">Usługa z następującym kontraktem jest udostępniona z wsHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="53202-113">A service with the following contract is exposed with a wsHttpBinding.</span></span>  
  
```csharp
using System.ServiceModel;  
  
// ...
  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Demo")]  
public interface IAffiliate  
{  
    [OperationContract]  
    bool NewAffiliate(string ID, string company, string fullname, string accountsCode);  
    [OperationContract]  
    bool RemoveAffiliate(string ID);  
    [OperationContract]  
    double RevenueCheckMonthly(ref string ID);  
    [OperationContract]  
    double RevenueCheckTotal(ref string ID);  
}  
```  
  
 <span data-ttu-id="53202-114">Aby utworzyć klienta WCF dla usługi zdalnej, można użyć następującego przykładowego ciągu monikera.</span><span class="sxs-lookup"><span data-stu-id="53202-114">To construct a WCF client for the remote service the following example moniker string can be used.</span></span>  
  
```
service4:mexAddress="http://servername/Affiliates/service.svc/mex",  
address="http://servername/Affiliates/service.svc",  
contract=IAffiliate, contractNamespace=http://Microsoft.ServiceModel.Demo,  
binding=WSHttpBinding_IAffiliate, bindingNamespace=http://tempuri.org/  
```  
  
 <span data-ttu-id="53202-115">Podczas wykonywania aplikacji klienckiej Klient wykonuje `WS-MetadataExchange` przy użyciu podanej wartości `mexAddress` .</span><span class="sxs-lookup"><span data-stu-id="53202-115">During the execution of the client application, the client performs a `WS-MetadataExchange` with the provided `mexAddress`.</span></span> <span data-ttu-id="53202-116">Może to zwrócić szczegóły dotyczące adresu, powiązania i kontraktu dla wielu usług.</span><span class="sxs-lookup"><span data-stu-id="53202-116">This might return the address, binding and contract details for a number of services.</span></span> <span data-ttu-id="53202-117">`address`Parametry, `contract` , `contractNamespace` i służą `binding` `bindingNamespace` do identyfikowania zamierzonej usługi.</span><span class="sxs-lookup"><span data-stu-id="53202-117">The `address`, `contract`, `contractNamespace`, `binding` and `bindingNamespace` parameters are used to identify the intended service.</span></span> <span data-ttu-id="53202-118">Po dopasowaniu tych parametrów moniker konstruuje klienta WCF przy użyciu odpowiedniej definicji kontraktu, a następnie wywołania można wykonać przy użyciu klienta WCF, podobnie jak w przypadku kontraktu o określonym typie.</span><span class="sxs-lookup"><span data-stu-id="53202-118">Once those parameters have been matched, the moniker constructs a WCF client with the appropriate contract definition and calls can then be made using the WCF client, as with the typed contract.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="53202-119">Jeśli moniker jest źle sformułowany lub usługa jest niedostępna, wywołanie do `GetObject` zwraca błąd mówiąc "Nieprawidłowa składnia".</span><span class="sxs-lookup"><span data-stu-id="53202-119">If the moniker is malformed or if the service is unavailable, the call to `GetObject` returns an error saying "Invalid Syntax".</span></span> <span data-ttu-id="53202-120">Jeśli wystąpi ten błąd, upewnij się, że moniker, którego używasz, jest poprawna i że usługa jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="53202-120">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53202-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="53202-121">See also</span></span>

- [<span data-ttu-id="53202-122">Instrukcje: rejestrowanie i konfigurowanie krótkiej nazwy usługi</span><span class="sxs-lookup"><span data-stu-id="53202-122">How to: Register and Configure a Service Moniker</span></span>](how-to-register-and-configure-a-service-moniker.md)
