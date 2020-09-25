---
title: <transactionFlow>
ms.date: 03/30/2017
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
ms.openlocfilehash: c4e5cbac24e2c72791c2f5c0faed0703363c99e1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201424"
---
# \<transactionFlow>

<span data-ttu-id="55d1c-101">Określa obsługę przepływu transakcji dla niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="55d1c-101">Specifies transaction flow support for the custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transactionFlow>**  
  
## <a name="syntax"></a><span data-ttu-id="55d1c-102">Składnia</span><span class="sxs-lookup"><span data-stu-id="55d1c-102">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55d1c-103">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="55d1c-103">Attributes and Elements</span></span>  

 <span data-ttu-id="55d1c-104">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="55d1c-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55d1c-105">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="55d1c-105">Attributes</span></span>  
  
|<span data-ttu-id="55d1c-106">Atrybut</span><span class="sxs-lookup"><span data-stu-id="55d1c-106">Attribute</span></span>|<span data-ttu-id="55d1c-107">Opis</span><span class="sxs-lookup"><span data-stu-id="55d1c-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="55d1c-108">Element TransactionProtocol</span><span class="sxs-lookup"><span data-stu-id="55d1c-108">transactionProtocol</span></span>|<span data-ttu-id="55d1c-109">Określa protokół transakcji, który ma być używany.</span><span class="sxs-lookup"><span data-stu-id="55d1c-109">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="55d1c-110">Prawidłowe wartości to:</span><span class="sxs-lookup"><span data-stu-id="55d1c-110">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="55d1c-111">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="55d1c-111">-   OleTransactions</span></span><br /><span data-ttu-id="55d1c-112">- WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="55d1c-112">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="55d1c-113">Wartość domyślna to OleTransactions.</span><span class="sxs-lookup"><span data-stu-id="55d1c-113">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="55d1c-114">Ten atrybut jest typu <xref:System.ServiceModel.TransactionProtocol> .</span><span class="sxs-lookup"><span data-stu-id="55d1c-114">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55d1c-115">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="55d1c-115">Child Elements</span></span>  

 <span data-ttu-id="55d1c-116">Brak.</span><span class="sxs-lookup"><span data-stu-id="55d1c-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55d1c-117">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="55d1c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="55d1c-118">Element</span><span class="sxs-lookup"><span data-stu-id="55d1c-118">Element</span></span>|<span data-ttu-id="55d1c-119">Opis</span><span class="sxs-lookup"><span data-stu-id="55d1c-119">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="55d1c-120">Definiuje wszystkie możliwości powiązań niestandardowego powiązania.</span><span class="sxs-lookup"><span data-stu-id="55d1c-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55d1c-121">Uwagi</span><span class="sxs-lookup"><span data-stu-id="55d1c-121">Remarks</span></span>  

 <span data-ttu-id="55d1c-122">Ten element umożliwia włączenie lub wyłączenie przychodzącego przepływu transakcji w ustawieniach powiązań punktu końcowego, a także określenie żądanego formatu protokołu dla transakcji przychodzących.</span><span class="sxs-lookup"><span data-stu-id="55d1c-122">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="55d1c-123">Aby uzyskać więcej informacji na temat korzystania z tego elementu konfiguracji, zobacz [Konfiguracja transakcji ServiceModel](../../../wcf/feature-details/servicemodel-transaction-configuration.md) i [Włączanie przepływu transakcji](../../../wcf/feature-details/enabling-transaction-flow.md).</span><span class="sxs-lookup"><span data-stu-id="55d1c-123">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="55d1c-124">W przypadku korzystania z `OleTransactions` protokołu do przepływu transakcji z punktu końcowego do punktu końcowego limit czasu transakcji może zostać utracony, jeśli docelowy punkt końcowy próbuje ponownie przepływać przy użyciu dowolnego protokołu innego niż `OleTransactions` .</span><span class="sxs-lookup"><span data-stu-id="55d1c-124">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="55d1c-125">Może to spowodować, że wszystkie węzły wyższego poziomu po przejściu OleTransactions do limitu czasu później niż oczekiwano.</span><span class="sxs-lookup"><span data-stu-id="55d1c-125">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d1c-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="55d1c-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactionFlowElement>
- <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="55d1c-127">Konfiguracja transakcji modelu ServiceModel</span><span class="sxs-lookup"><span data-stu-id="55d1c-127">ServiceModel Transaction Configuration</span></span>](../../../wcf/feature-details/servicemodel-transaction-configuration.md)
- [<span data-ttu-id="55d1c-128">Włączanie przepływu transakcji</span><span class="sxs-lookup"><span data-stu-id="55d1c-128">Enabling Transaction Flow</span></span>](../../../wcf/feature-details/enabling-transaction-flow.md)
- [<span data-ttu-id="55d1c-129">Powiązania</span><span class="sxs-lookup"><span data-stu-id="55d1c-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="55d1c-130">Rozszerzanie powiązań</span><span class="sxs-lookup"><span data-stu-id="55d1c-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="55d1c-131">Powiązania niestandardowe</span><span class="sxs-lookup"><span data-stu-id="55d1c-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
