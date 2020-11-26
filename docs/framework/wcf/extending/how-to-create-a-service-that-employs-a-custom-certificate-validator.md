---
title: 'Instrukcje: tworzenie usługi korzystającej z niestandardowego modułu weryfikacji certyfikatów'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
ms.openlocfilehash: 31918ca2d96b63911130d22476a6e5a6d48999ee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249244"
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a><span data-ttu-id="a3cb8-102">Instrukcje: tworzenie usługi korzystającej z niestandardowego modułu weryfikacji certyfikatów</span><span class="sxs-lookup"><span data-stu-id="a3cb8-102">How to: Create a Service that Employs a Custom Certificate Validator</span></span>

<span data-ttu-id="a3cb8-103">W tym temacie pokazano, jak zaimplementować niestandardowy moduł sprawdzania poprawności certyfikatu oraz jak skonfigurować poświadczenia klienta lub usługi w celu zastąpienia domyślnej logiki walidacji certyfikatu za pomocą niestandardowego modułu sprawdzania certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-103">This topic shows how to implement a custom certificate validator and how to configure client or service credentials to replace the default certificate validation logic with the custom certificate validator.</span></span>  
  
 <span data-ttu-id="a3cb8-104">Jeśli certyfikat X. 509 jest używany do uwierzytelniania klienta lub usługi, Windows Communication Foundation (WCF) domyślnie używa magazynu certyfikatów systemu Windows i interfejsu API kryptografii do weryfikacji certyfikatu i upewnienia się, że jest zaufany.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-104">If the X.509 certificate is used to authenticate a client or service, Windows Communication Foundation (WCF) by default uses the Windows certificate store and Crypto API to validate the certificate and to ensure that it is trusted.</span></span> <span data-ttu-id="a3cb8-105">Czasami Wbudowana funkcja weryfikacji certyfikatu jest za mała i należy ją zmienić.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-105">Sometimes the built-in certificate validation functionality is not enough and must be changed.</span></span> <span data-ttu-id="a3cb8-106">Funkcja WCF zapewnia łatwy sposób zmiany logiki walidacji przez umożliwienie użytkownikom dodawania niestandardowego modułu weryfikacji certyfikatu.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-106">WCF provides an easy way to change the validation logic by allowing users to add a custom certificate validator.</span></span> <span data-ttu-id="a3cb8-107">Jeśli jest określony niestandardowy moduł sprawdzania poprawności certyfikatu, funkcja WCF nie korzysta z wbudowanej logiki walidacji certyfikatu, ale zamiast tego używa niestandardowego modułu weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-107">If a custom certificate validator is specified, WCF does not use the built-in certificate validation logic but relies on the custom validator instead.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="a3cb8-108">Procedury</span><span class="sxs-lookup"><span data-stu-id="a3cb8-108">Procedures</span></span>  
  
#### <a name="to-create-a-custom-certificate-validator"></a><span data-ttu-id="a3cb8-109">Aby utworzyć niestandardowy moduł sprawdzania poprawności certyfikatu</span><span class="sxs-lookup"><span data-stu-id="a3cb8-109">To create a custom certificate validator</span></span>  
  
1. <span data-ttu-id="a3cb8-110">Zdefiniuj nową klasę pochodną <xref:System.IdentityModel.Selectors.X509CertificateValidator> .</span><span class="sxs-lookup"><span data-stu-id="a3cb8-110">Define a new class derived from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span>  
  
2. <span data-ttu-id="a3cb8-111">Zaimplementuj metodę abstrakcyjną <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> .</span><span class="sxs-lookup"><span data-stu-id="a3cb8-111">Implement the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> method.</span></span> <span data-ttu-id="a3cb8-112">Certyfikat, który musi zostać sprawdzony, jest przenoszona jako argument do metody.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-112">The certificate that must be validated is passed as an argument to the method.</span></span> <span data-ttu-id="a3cb8-113">Jeśli przesłany certyfikat nie jest prawidłowy zgodnie z logiką walidacji, ta metoda zgłasza <xref:System.IdentityModel.Tokens.SecurityTokenValidationException> .</span><span class="sxs-lookup"><span data-stu-id="a3cb8-113">If the passed certificate is not valid according to the validation logic, this method throws a <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span></span> <span data-ttu-id="a3cb8-114">Jeśli certyfikat jest prawidłowy, Metoda powraca do obiektu wywołującego.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-114">If the certificate is valid, the method returns to the caller.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="a3cb8-115">Aby przywrócić błędy uwierzytelniania z powrotem do klienta, należy zgłosić <xref:System.ServiceModel.FaultException> <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> metodę.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-115">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a><span data-ttu-id="a3cb8-116">Aby określić niestandardowy moduł sprawdzania poprawności certyfikatu w konfiguracji usługi</span><span class="sxs-lookup"><span data-stu-id="a3cb8-116">To specify a custom certificate validator in service configuration</span></span>  
  
1. <span data-ttu-id="a3cb8-117">Dodaj [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element i [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) do [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-117">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="a3cb8-118">Dodaj [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) a i ustaw `name` odpowiednią wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-118">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="a3cb8-119">Dodaj [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) `<behavior>` element do elementu.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-119">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the `<behavior>` element.</span></span>  
  
4. <span data-ttu-id="a3cb8-120">Dodaj `<clientCertificate>` element do `<serviceCredentials>` elementu.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-120">Add a `<clientCertificate>` element to the `<serviceCredentials>` element.</span></span>  
  
5. <span data-ttu-id="a3cb8-121">Dodaj [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) `<clientCertificate>` element do elementu.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-121">Add an [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) to the `<clientCertificate>` element.</span></span>  
  
6. <span data-ttu-id="a3cb8-122">Ustaw `customCertificateValidatorType` atrybut na typ walidacji.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-122">Set the `customCertificateValidatorType` attribute to the validator type.</span></span> <span data-ttu-id="a3cb8-123">Poniższy przykład ustawia atrybut na przestrzeń nazw i nazwę typu.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-123">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
7. <span data-ttu-id="a3cb8-124">Ustaw `certificateValidationMode` atrybut na `Custom` .</span><span class="sxs-lookup"><span data-stu-id="a3cb8-124">Set the `certificateValidationMode` attribute to `Custom`.</span></span>  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="ServiceBehavior">  
         <serviceCredentials>  
          <clientCertificate>  
          <authentication certificateValidationMode="Custom" customCertificateValidatorType="Samples.MyValidator, service" />  
          </clientCertificate>  
         </serviceCredentials>  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a><span data-ttu-id="a3cb8-125">Aby określić niestandardowy moduł sprawdzania poprawności certyfikatu przy użyciu konfiguracji na kliencie</span><span class="sxs-lookup"><span data-stu-id="a3cb8-125">To specify a custom certificate validator using configuration on the client</span></span>  
  
1. <span data-ttu-id="a3cb8-126">Dodaj [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element i [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) do [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elementu.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-126">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="a3cb8-127">Dodaj [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) element.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-127">Add an [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) element.</span></span>  
  
3. <span data-ttu-id="a3cb8-128">Dodaj `<behavior>` element i ustaw `name` odpowiednią wartość atrybutu.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-128">Add a `<behavior>` element and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="a3cb8-129">Dodaj [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) element.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-129">Add a [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
5. <span data-ttu-id="a3cb8-130">Dodaj [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .</span><span class="sxs-lookup"><span data-stu-id="a3cb8-130">Add a [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span></span>  
  
6. <span data-ttu-id="a3cb8-131">Dodaj [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) , jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-131">Add an [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) as shown on the following example.</span></span>  
  
7. <span data-ttu-id="a3cb8-132">Ustaw `customCertificateValidatorType` atrybut na typ walidacji.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-132">Set the `customCertificateValidatorType` attribute to the validator type.</span></span>  
  
8. <span data-ttu-id="a3cb8-133">Ustaw `certificateValidationMode` atrybut na `Custom` .</span><span class="sxs-lookup"><span data-stu-id="a3cb8-133">Set the `certificateValidationMode` attribute to `Custom`.</span></span> <span data-ttu-id="a3cb8-134">Poniższy przykład ustawia atrybut na przestrzeń nazw i nazwę typu.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-134">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <endpointBehaviors>  
        <behavior name="clientBehavior">  
         <clientCredentials>  
          <serviceCertificate>  
           <authentication certificateValidationMode="Custom"
                  customCertificateValidatorType=  
             "Samples.CustomX509CertificateValidator, client"/>  
          </serviceCertificate>  
         </clientCredentials>  
        </behavior>  
       </endpointBehaviors>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a><span data-ttu-id="a3cb8-135">Aby określić niestandardowy moduł sprawdzania poprawności certyfikatu przy użyciu kodu w usłudze</span><span class="sxs-lookup"><span data-stu-id="a3cb8-135">To specify a custom certificate validator using code on the service</span></span>  
  
1. <span data-ttu-id="a3cb8-136">Określ niestandardowy moduł sprawdzania poprawności certyfikatu <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> .</span><span class="sxs-lookup"><span data-stu-id="a3cb8-136">Specify the custom certificate validator on the <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> property.</span></span> <span data-ttu-id="a3cb8-137">Możesz uzyskać dostęp do poświadczeń usługi przy użyciu <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-137">You can access the service credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span>  
  
2. <span data-ttu-id="a3cb8-138">Ustaw <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> Właściwość na wartość <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom> .</span><span class="sxs-lookup"><span data-stu-id="a3cb8-138">Set the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a><span data-ttu-id="a3cb8-139">Aby określić niestandardowy moduł sprawdzania poprawności certyfikatu przy użyciu kodu na kliencie</span><span class="sxs-lookup"><span data-stu-id="a3cb8-139">To specify a custom certificate validator using code on the client</span></span>  
  
1. <span data-ttu-id="a3cb8-140">Określ niestandardowy moduł sprawdzania poprawności certyfikatu przy użyciu <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-140">Specify the custom certificate validator using the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> property.</span></span> <span data-ttu-id="a3cb8-141">Możesz uzyskać dostęp do poświadczeń klienta przy użyciu <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> właściwości.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-141">You can access the client credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span> <span data-ttu-id="a3cb8-142">(Klasa klienta wygenerowana przez [Narzędzie narzędzia metadanych ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) zawsze pochodzi od <xref:System.ServiceModel.ClientBase%601> klasy.)</span><span class="sxs-lookup"><span data-stu-id="a3cb8-142">(The client class generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) always derives from the <xref:System.ServiceModel.ClientBase%601> class.)</span></span>  
  
2. <span data-ttu-id="a3cb8-143">Ustaw <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> Właściwość na wartość <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom> .</span><span class="sxs-lookup"><span data-stu-id="a3cb8-143">Set the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3cb8-144">Przykład</span><span class="sxs-lookup"><span data-stu-id="a3cb8-144">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a3cb8-145">Opis</span><span class="sxs-lookup"><span data-stu-id="a3cb8-145">Description</span></span>  

 <span data-ttu-id="a3cb8-146">Poniższy przykład pokazuje implementację niestandardowego modułu weryfikacji certyfikatu i jego użycia w usłudze.</span><span class="sxs-lookup"><span data-stu-id="a3cb8-146">The following sample shows an implementation of a custom certificate validator and its usage on the service.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a3cb8-147">Kod</span><span class="sxs-lookup"><span data-stu-id="a3cb8-147">Code</span></span>  

 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a3cb8-148">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="a3cb8-148">See also</span></span>

- <xref:System.IdentityModel.Selectors.X509CertificateValidator>
