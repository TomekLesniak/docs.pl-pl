---
title: Mieszanie protokołów zaufania w scenariuszach obejmujących federację
ms.date: 03/30/2017
ms.assetid: d7b5fee9-2246-4b09-b8d7-9e63cb817279
ms.openlocfilehash: 5ce178c0b2c83469a26993ce6db2d6c87815543b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96248178"
---
# <a name="mixing-trust-protocols-in-federated-scenarios"></a><span data-ttu-id="09341-102">Mieszanie protokołów zaufania w scenariuszach obejmujących federację</span><span class="sxs-lookup"><span data-stu-id="09341-102">Mixing Trust Protocols in Federated Scenarios</span></span>

<span data-ttu-id="09341-103">Mogą istnieć scenariusze, w których klienci federacyjne komunikują się z usługą i usługą tokenu zabezpieczającego (STS), która nie ma tej samej wersji zaufania.</span><span class="sxs-lookup"><span data-stu-id="09341-103">There may be scenarios in which federated clients communicate with a service and a Security Token Service (STS) that do not have the same trust version.</span></span> <span data-ttu-id="09341-104">WSDL usługi może zawierać `RequestSecurityTokenTemplate` potwierdzenie z WS-Trust elementami, które różnią się od wersji programu STS.</span><span class="sxs-lookup"><span data-stu-id="09341-104">The service WSDL can contain a `RequestSecurityTokenTemplate` assertion with WS-Trust elements that are of different versions than the STS.</span></span> <span data-ttu-id="09341-105">W takich przypadkach klient Windows Communication Foundation (WCF) konwertuje elementy WS-Trust otrzymane z programu `RequestSecurityTokenTemplate` w celu dopasowania do wersji zaufania usługi STS.</span><span class="sxs-lookup"><span data-stu-id="09341-105">In such cases, a Windows Communication Foundation (WCF) client converts the WS-Trust elements received from the `RequestSecurityTokenTemplate` to match the STS trust version.</span></span> <span data-ttu-id="09341-106">Usługa WCF obsługuje niezgodne wersje zaufania tylko dla powiązań standardowych.</span><span class="sxs-lookup"><span data-stu-id="09341-106">WCF handles mismatched trust versions only for standard bindings.</span></span> <span data-ttu-id="09341-107">Wszystkie parametry algorytmu standardowego rozpoznawane przez funkcję WCF są częścią standardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="09341-107">All standard algorithm parameters that are recognized by WCF are part of the standard binding.</span></span> <span data-ttu-id="09341-108">W tym temacie opisano zachowanie WCF z różnymi ustawieniami zaufania między usługą i usługą STS.</span><span class="sxs-lookup"><span data-stu-id="09341-108">This topic describes the WCF behavior with various trust settings between the service and the STS.</span></span>  
  
## <a name="rp-feb-2005-and-sts-feb-2005"></a><span data-ttu-id="09341-109">RP lut 2005 i STS lutego 2005</span><span class="sxs-lookup"><span data-stu-id="09341-109">RP Feb 2005 and STS Feb 2005</span></span>  

 <span data-ttu-id="09341-110">WSDL dla jednostki uzależnionej (RP) zawiera następujące elementy w `RequestSecurityTokenTemplate` sekcji:</span><span class="sxs-lookup"><span data-stu-id="09341-110">The WSDL for Relying Party (RP) contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 <span data-ttu-id="09341-111">Plik konfiguracji klienta zawiera listę parametrów.</span><span class="sxs-lookup"><span data-stu-id="09341-111">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="09341-112">Funkcja WCF nie może rozróżnić parametrów klienta i usługi; dodaje wszystkie parametry i wysyła je w `RequestSecurityTokenTemplate` (RST).</span><span class="sxs-lookup"><span data-stu-id="09341-112">WCF cannot differentiate between the client and service parameters; it adds all the parameters and sends them in the `RequestSecurityTokenTemplate` (RST).</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-13"></a><span data-ttu-id="09341-113">RP Trust 1,3 i usługa STS — zaufanie 1,3</span><span class="sxs-lookup"><span data-stu-id="09341-113">RP Trust 1.3 and STS Trust 1.3</span></span>  

 <span data-ttu-id="09341-114">WSDL dla RP zawiera następujące elementy w `RequestSecurityTokenTemplate` sekcji:</span><span class="sxs-lookup"><span data-stu-id="09341-114">The WSDL for RP contains the following elements within the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 <span data-ttu-id="09341-115">Plik konfiguracji klienta zawiera `secondaryParameters` element, który otacza parametry określone przez RP.</span><span class="sxs-lookup"><span data-stu-id="09341-115">The client configuration file contains a `secondaryParameters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="09341-116">Funkcja WCF usuwa `EncryptionAlgorithm` `CanonicalizationAlgorithm` elementy i `KeyWrapAlgorithm` z elementu najwyższego poziomu w obszarze RST, jeśli są obecne wewnątrz `SecondaryParameters` elementu.</span><span class="sxs-lookup"><span data-stu-id="09341-116">WCF removes the `EncryptionAlgorithm`, `CanonicalizationAlgorithm` and `KeyWrapAlgorithm` elements from the top-level element under the RST if these are present inside the `SecondaryParameters` element.</span></span> <span data-ttu-id="09341-117">Funkcja WCF dołącza `SecondaryParameters` element do wychodzącego RST o niemodyfikowaniu.</span><span class="sxs-lookup"><span data-stu-id="09341-117">WCF appends the `SecondaryParameters` element to the outgoing RST unmodified.</span></span>  
  
## <a name="rp-trust-feb-2005-and-sts-trust-13"></a><span data-ttu-id="09341-118">RP Trust 2005 i usługa STS — zaufanie 1,3</span><span class="sxs-lookup"><span data-stu-id="09341-118">RP Trust Feb 2005 and STS Trust 1.3</span></span>  

 <span data-ttu-id="09341-119">WSDL dla RP zawiera następujące elementy w `RequestSecurityTokenTemplate` sekcji:</span><span class="sxs-lookup"><span data-stu-id="09341-119">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
 <span data-ttu-id="09341-120">Plik konfiguracji klienta zawiera listę parametrów.</span><span class="sxs-lookup"><span data-stu-id="09341-120">The client configuration file contains a list of parameters.</span></span>  
  
 <span data-ttu-id="09341-121">W pliku konfiguracji klienta WCF nie można rozróżnić między parametrami usługi i klienta.</span><span class="sxs-lookup"><span data-stu-id="09341-121">From the client configuration file, WCF cannot differentiate between the service and client parameters.</span></span> <span data-ttu-id="09341-122">W związku z tym WCF konwertuje wszystkie parametry do przestrzeni nazw zaufania 1,3.</span><span class="sxs-lookup"><span data-stu-id="09341-122">Therefore WCF converts all the parameters to a Trust version 1.3 namespace.</span></span>  
  
 <span data-ttu-id="09341-123">Usługa WCF obsługuje `KeyType` `KeySize` elementy, i `TokenType` w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="09341-123">WCF handles the `KeyType`, `KeySize`, and `TokenType` elements as follows:</span></span>  
  
- <span data-ttu-id="09341-124">Pobierz WSDL, utwórz powiązanie i przypisz `KeyType` , `KeySize` i `TokenType` z parametrów RP.</span><span class="sxs-lookup"><span data-stu-id="09341-124">Download the WSDL, create the binding, and assign `KeyType`, `KeySize`, and `TokenType` from the RP parameters.</span></span> <span data-ttu-id="09341-125">Następnie zostanie wygenerowany plik konfiguracji klienta.</span><span class="sxs-lookup"><span data-stu-id="09341-125">The client configuration file is then generated.</span></span>  
  
- <span data-ttu-id="09341-126">Klient może teraz zmienić dowolny parametr w pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="09341-126">The client can now change any parameter in the configuration file.</span></span>  
  
- <span data-ttu-id="09341-127">W czasie wykonywania WCF kopiuje wszystkie parametry określone w `AdditionalTokenParameters` sekcji pliku konfiguracji klienta z wyjątkiem `KeyType` , `KeySize` i `TokenType` , ponieważ te parametry są uwzględniane podczas generowania pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="09341-127">During runtime, WCF copies all parameters specified into the `AdditionalTokenParameters` section of the client configuration file except `KeyType`, `KeySize` and `TokenType`, because these parameters are accounted for during the configuration file generation.</span></span>  
  
## <a name="rp-trust-13-and-sts-trust-feb-2005"></a><span data-ttu-id="09341-128">RP Trust 1,3 i STS — luty 2005</span><span class="sxs-lookup"><span data-stu-id="09341-128">RP Trust 1.3 and STS Trust Feb 2005</span></span>  

 <span data-ttu-id="09341-129">WSDL dla RP zawiera następujące elementy w `RequestSecurityTokenTemplate` sekcji:</span><span class="sxs-lookup"><span data-stu-id="09341-129">The WSDL for RP contains the following elements in the `RequestSecurityTokenTemplate` section:</span></span>  
  
- `CanonicalizationAlgorithm`  
  
- `EncryptionAlgorithm`  
  
- `EncryptWith`  
  
- `SignWith`  
  
- `KeySize`  
  
- `KeyType`  
  
- `KeyWrapAlgorithm`  
  
 <span data-ttu-id="09341-130">Plik konfiguracji klienta zawiera `secondaryParamters` element, który otacza parametry określone przez RP.</span><span class="sxs-lookup"><span data-stu-id="09341-130">The client configuration file contains a `secondaryParamters` element that wraps the parameters specified by the RP.</span></span>  
  
 <span data-ttu-id="09341-131">Program WCF kopiuje wszystkie parametry określone w `SecondaryParameters` sekcji do najwyższego pierwszego poziomu RST elementu, ale nie konwertuje je do przestrzeni nazw 2005 WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="09341-131">WCF copies all the parameters specified within the `SecondaryParameters` section to the top-level RST element, but does not convert them to the 2005 WS-Trust namespace.</span></span>
