---
title: TransactionFlowBindingElement
ms.date: 03/30/2017
ms.assetid: 0a9656fe-2400-45ca-ad79-92715c8cf190
ms.openlocfilehash: 577502d1cd3d81784cb9b1eb3b249376b8ffa6b8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96234898"
---
# <a name="transactionflowbindingelement"></a><span data-ttu-id="147b9-102">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="147b9-102">TransactionFlowBindingElement</span></span>

<span data-ttu-id="147b9-103">TransactionFlowBindingElement</span><span class="sxs-lookup"><span data-stu-id="147b9-103">TransactionFlowBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="147b9-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="147b9-104">Syntax</span></span>  
  
```csharp
class TransactionFlowBindingElement : BindingElement  
{  
  string IssuedTokens;  
  string TransactionProtocol;  
  boolean Transactions;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="147b9-105">Metody</span><span class="sxs-lookup"><span data-stu-id="147b9-105">Methods</span></span>  

 <span data-ttu-id="147b9-106">Klasa TransactionFlowBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="147b9-106">The TransactionFlowBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="147b9-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="147b9-107">Properties</span></span>  

 <span data-ttu-id="147b9-108">Klasa TransactionFlowBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="147b9-108">The TransactionFlowBindingElement class has the following properties:</span></span>  
  
### <a name="issuedtokens"></a><span data-ttu-id="147b9-109">IssuedTokens</span><span class="sxs-lookup"><span data-stu-id="147b9-109">IssuedTokens</span></span>  

 <span data-ttu-id="147b9-110">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="147b9-110">Data type: string</span></span>  
  
 <span data-ttu-id="147b9-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="147b9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="147b9-112">Określa wymagania dotyczące wystawionego nagłówka tokenów zabezpieczeń (IssuedTokens z usługi WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="147b9-112">Specifies the requirement for an issued security tokens header (IssuedTokens from WS-Trust).</span></span>  
  
### <a name="transactionprotocol"></a><span data-ttu-id="147b9-113">Element TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="147b9-113">TransactionProtocol</span></span>  

 <span data-ttu-id="147b9-114">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="147b9-114">Data type: string</span></span>  
  
 <span data-ttu-id="147b9-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="147b9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="147b9-116">Protokół transakcji używany przez usługę do przepływu transakcji.</span><span class="sxs-lookup"><span data-stu-id="147b9-116">The transactions protocol used by the service to flow transactions.</span></span>  
  
### <a name="transactions"></a><span data-ttu-id="147b9-117">Transakcje</span><span class="sxs-lookup"><span data-stu-id="147b9-117">Transactions</span></span>  

 <span data-ttu-id="147b9-118">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="147b9-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="147b9-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="147b9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="147b9-120">Wskazuje, czy transakcja przychodząca jest obsługiwana.</span><span class="sxs-lookup"><span data-stu-id="147b9-120">Indicates whether the incoming transaction is supported.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="147b9-121">Wymagania</span><span class="sxs-lookup"><span data-stu-id="147b9-121">Requirements</span></span>  
  
|<span data-ttu-id="147b9-122">PLIK</span><span class="sxs-lookup"><span data-stu-id="147b9-122">MOF</span></span>|<span data-ttu-id="147b9-123">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="147b9-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="147b9-124">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="147b9-124">Namespace</span></span>|<span data-ttu-id="147b9-125">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="147b9-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="147b9-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="147b9-126">See also</span></span>

- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
