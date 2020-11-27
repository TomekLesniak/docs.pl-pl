---
title: 'Instrukcje: Określanie typu poświadczeń klienta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: b45d7b58d8a1fe79f9d7a8cff6e328b46633985c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293679"
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="3b31a-102">Instrukcje: Określanie typu poświadczeń klienta</span><span class="sxs-lookup"><span data-stu-id="3b31a-102">How to: Specify the Client Credential Type</span></span>

<span data-ttu-id="3b31a-103">Po ustawieniu trybu zabezpieczeń (transport lub wiadomość) można ustawić typ poświadczeń klienta.</span><span class="sxs-lookup"><span data-stu-id="3b31a-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="3b31a-104">Ta właściwość określa typ poświadczeń, które klient musi przekazać do usługi w celu uwierzytelnienia.</span><span class="sxs-lookup"><span data-stu-id="3b31a-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> <span data-ttu-id="3b31a-105">Aby uzyskać więcej informacji na temat ustawiania trybu zabezpieczeń (wymaganego kroku przed ustawieniem typu poświadczeń klienta), zobacz [How to: Set a Security Mode](how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="3b31a-105">For more information about setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="3b31a-106">Aby ustawić typ poświadczeń klienta w kodzie</span><span class="sxs-lookup"><span data-stu-id="3b31a-106">To set the client credential type in code</span></span>  
  
1. <span data-ttu-id="3b31a-107">Utwórz wystąpienie powiązania, które będzie używane przez usługę.</span><span class="sxs-lookup"><span data-stu-id="3b31a-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="3b31a-108">Ten przykład używa <xref:System.ServiceModel.WSHttpBinding> powiązania.</span><span class="sxs-lookup"><span data-stu-id="3b31a-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2. <span data-ttu-id="3b31a-109">Ustaw <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> Właściwość na odpowiednią wartość.</span><span class="sxs-lookup"><span data-stu-id="3b31a-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="3b31a-110">W tym przykładzie jest stosowany tryb wiadomości.</span><span class="sxs-lookup"><span data-stu-id="3b31a-110">This example uses the Message mode.</span></span>  
  
3. <span data-ttu-id="3b31a-111">Ustaw <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> Właściwość na odpowiednią wartość.</span><span class="sxs-lookup"><span data-stu-id="3b31a-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="3b31a-112">Ten przykład służy do ustawiania uwierzytelniania systemu Windows ( <xref:System.ServiceModel.MessageCredentialType.Windows> ).</span><span class="sxs-lookup"><span data-stu-id="3b31a-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="3b31a-113">Aby ustawić typ poświadczeń klienta w konfiguracji</span><span class="sxs-lookup"><span data-stu-id="3b31a-113">To set the client credential type in configuration</span></span>  
  
1. <span data-ttu-id="3b31a-114">Dodaj [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) element do pliku konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="3b31a-114">Add a [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2. <span data-ttu-id="3b31a-115">Jako element podrzędny Dodaj [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element.</span><span class="sxs-lookup"><span data-stu-id="3b31a-115">As a child element, add a [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3. <span data-ttu-id="3b31a-116">Dodaj odpowiednie powiązanie.</span><span class="sxs-lookup"><span data-stu-id="3b31a-116">Add an appropriate binding.</span></span> <span data-ttu-id="3b31a-117">W tym przykładzie używa [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="3b31a-117">This example uses the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4. <span data-ttu-id="3b31a-118">Dodaj [\<binding>](../configure-apps/file-schema/wcf/bindings.md) element i ustaw `name` odpowiednią wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="3b31a-118">Add a [\<binding>](../configure-apps/file-schema/wcf/bindings.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="3b31a-119">Ten przykład używa nazwy "SecureBinding".</span><span class="sxs-lookup"><span data-stu-id="3b31a-119">This example uses the name "SecureBinding".</span></span>  
  
5. <span data-ttu-id="3b31a-120">Dodaj `<security>` powiązanie.</span><span class="sxs-lookup"><span data-stu-id="3b31a-120">Add a `<security>` binding.</span></span> <span data-ttu-id="3b31a-121">Ustaw `mode` odpowiednią wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="3b31a-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="3b31a-122">Ten przykład ustawia go na `"Message"` .</span><span class="sxs-lookup"><span data-stu-id="3b31a-122">This example sets it to `"Message"`.</span></span>  
  
6. <span data-ttu-id="3b31a-123">Dodaj `<message>` `<transport>` element lub, zgodnie z trybem zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="3b31a-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="3b31a-124">Ustaw `clientCredentialType` odpowiednią wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="3b31a-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="3b31a-125">Ten przykład używa `"Windows"` .</span><span class="sxs-lookup"><span data-stu-id="3b31a-125">This example uses `"Windows"`.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3b31a-126">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="3b31a-126">See also</span></span>

- [<span data-ttu-id="3b31a-127">Zabezpieczanie usług</span><span class="sxs-lookup"><span data-stu-id="3b31a-127">Securing Services</span></span>](securing-services.md)
- [<span data-ttu-id="3b31a-128">Instrukcje: Ustawianie trybu zabezpieczeń</span><span class="sxs-lookup"><span data-stu-id="3b31a-128">How to: Set the Security Mode</span></span>](how-to-set-the-security-mode.md)
