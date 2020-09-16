---
title: Dostęp do usług WCF za pomocą aplikacji klienckiej ze Sklepu Windows
ms.date: 03/30/2017
ms.assetid: e2002ef4-5dee-4a54-9d87-03b33d35fc52
ms.openlocfilehash: d575907feea3d831b7e6f69410c8d4647e6ac95d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557960"
---
# <a name="access-wcf-services-with-a-windows-store-client-app"></a><span data-ttu-id="9fd28-102">Dostęp do usług WCF za pomocą aplikacji klienckiej ze sklepu Windows</span><span class="sxs-lookup"><span data-stu-id="9fd28-102">Access WCF Services with a Windows Store Client App</span></span>

<span data-ttu-id="9fd28-103">System Windows 8 wprowadza nowy typ aplikacji o nazwie aplikacje ze sklepu Windows.</span><span class="sxs-lookup"><span data-stu-id="9fd28-103">Windows 8 introduces a new type of application called Windows Store applications.</span></span> <span data-ttu-id="9fd28-104">Te aplikacje są projektowane wokół interfejsu ekranu dotykowego.</span><span class="sxs-lookup"><span data-stu-id="9fd28-104">These applications are designed around a touch screen interface.</span></span> <span data-ttu-id="9fd28-105">.NET Framework 4,5 umożliwia aplikacjom ze sklepu Windows wywoływanie usług WCF.</span><span class="sxs-lookup"><span data-stu-id="9fd28-105">.NET Framework 4.5 enables Windows Store applications to call WCF services.</span></span>  
  
## <a name="wcf-support-in-windows-store-applications"></a><span data-ttu-id="9fd28-106">Obsługa platformy WCF w aplikacjach ze sklepu Windows</span><span class="sxs-lookup"><span data-stu-id="9fd28-106">WCF Support in Windows Store Applications</span></span>  
 <span data-ttu-id="9fd28-107">Podzestaw funkcji WCF jest dostępny w aplikacji ze sklepu Windows. więcej informacji znajduje się w poniższych sekcjach.</span><span class="sxs-lookup"><span data-stu-id="9fd28-107">A subset of WCF functionality is available from within a Windows Store application, see the following sections for more details.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9fd28-108">Użyj interfejsów API zespalania zamiast tych, które są udostępniane przez platformę WCF.</span><span class="sxs-lookup"><span data-stu-id="9fd28-108">Use the WinRT syndication APIs instead of those exposed by WCF.</span></span> <span data-ttu-id="9fd28-109">Aby uzyskać więcej informacji, zobacz [interfejs API zespalania programu WinRT](xref:Windows.Web.Syndication)</span><span class="sxs-lookup"><span data-stu-id="9fd28-109">For more information see, [WinRT Syndication API](xref:Windows.Web.Syndication)</span></span>  
  
> [!WARNING]
> <span data-ttu-id="9fd28-110">Dodawanie odwołania do usługi sieci Web do składnika środowisko wykonawcze systemu Windows przy użyciu Dodaj odwołanie do usługi nie jest obsługiwane.</span><span class="sxs-lookup"><span data-stu-id="9fd28-110">Using Add Service Reference to add a web service reference to a Windows Runtime Component isn't supported.</span></span>  
  
### <a name="supported-bindings"></a><span data-ttu-id="9fd28-111">Obsługiwane powiązania</span><span class="sxs-lookup"><span data-stu-id="9fd28-111">Supported Bindings</span></span>  
 <span data-ttu-id="9fd28-112">W aplikacjach ze sklepu Windows obsługiwane są następujące powiązania WCF:</span><span class="sxs-lookup"><span data-stu-id="9fd28-112">The following WCF bindings are supported in Windows Store Applications:</span></span>  
  
1. <xref:System.ServiceModel.BasicHttpBinding>  
  
2. <xref:System.ServiceModel.NetTcpBinding>  
  
3. <xref:System.ServiceModel.NetHttpBinding>  
  
4. <xref:System.ServiceModel.Channels.CustomBinding>
  
 <span data-ttu-id="9fd28-113">Następujące elementy powiązania są obsługiwane w aplikacjach ze sklepu Windows</span><span class="sxs-lookup"><span data-stu-id="9fd28-113">The following binding elements are supported in Windows Store Applications</span></span>  
  
1. <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
2. <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
3. <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>  
  
4. <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
5. <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
6. <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
7. <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
8. <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
9. <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>  
  
 <span data-ttu-id="9fd28-114">Obsługiwane są zarówno kodowanie tekstu, jak i binarne.</span><span class="sxs-lookup"><span data-stu-id="9fd28-114">Both Text and Binary encodings are supported.</span></span> <span data-ttu-id="9fd28-115">Obsługiwane są wszystkie tryby transferu WCF.</span><span class="sxs-lookup"><span data-stu-id="9fd28-115">All WCF transfer modes are supported.</span></span> <span data-ttu-id="9fd28-116">Aby uzyskać więcej informacji, zobacz [transfer komunikatów przesyłanych strumieniowo](streaming-message-transfer.md).</span><span class="sxs-lookup"><span data-stu-id="9fd28-116">For more information see, [Streaming Message Transfer](streaming-message-transfer.md).</span></span>  
  
### <a name="add-service-reference"></a><span data-ttu-id="9fd28-117">Dodaj odwołanie do usługi</span><span class="sxs-lookup"><span data-stu-id="9fd28-117">Add Service Reference</span></span>  
 <span data-ttu-id="9fd28-118">Aby wywołać usługę WCF z poziomu aplikacji ze sklepu Windows, użyj funkcji Dodaj odwołanie do usługi programu Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="9fd28-118">To call a WCF service from a Windows Store application, use the Add Service Reference feature of Visual Studio 2012.</span></span> <span data-ttu-id="9fd28-119">Po wykonaniu tej czynności w aplikacji ze sklepu Windows zobaczysz kilka zmian w funkcji Dodaj odwołanie do usługi.</span><span class="sxs-lookup"><span data-stu-id="9fd28-119">You will notice a few changes in the functionality of Add Service Reference when done within a Windows Store application.</span></span> <span data-ttu-id="9fd28-120">Nie jest generowany pierwszy plik konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="9fd28-120">First no configuration file is generated.</span></span> <span data-ttu-id="9fd28-121">Aplikacje ze sklepu Windows nie używają plików konfiguracji, dlatego muszą być skonfigurowane w kodzie.</span><span class="sxs-lookup"><span data-stu-id="9fd28-121">Windows Store applications do not use configuration files, so they must be configured in code.</span></span> <span data-ttu-id="9fd28-122">Ten kod konfiguracji można znaleźć w pliku References.cs generowanym przez Dodaj odwołanie do usługi.</span><span class="sxs-lookup"><span data-stu-id="9fd28-122">This configuration code can be found in the References.cs file generated by Add Service Reference.</span></span> <span data-ttu-id="9fd28-123">Aby wyświetlić ten plik, upewnij się, że wybrano opcję "Pokaż wszystkie pliki" w Eksploratorze rozwiązań.</span><span class="sxs-lookup"><span data-stu-id="9fd28-123">To see this file, make sure to select "Show All Files" in the solution explorer.</span></span> <span data-ttu-id="9fd28-124">Plik będzie znajdował się w ramach odwołań do usługi, a następnie odwołuje się do węzłów. svcmap w ramach projektu.</span><span class="sxs-lookup"><span data-stu-id="9fd28-124">The file will be located under the Service References and then Reference.svcmap nodes within the project.</span></span> <span data-ttu-id="9fd28-125">Wszystkie operacje wygenerowane dla usług WCF w ramach aplikacji ze sklepu Windows będą asynchroniczne za pomocą wzorca asynchronicznego opartego na zadaniach.</span><span class="sxs-lookup"><span data-stu-id="9fd28-125">All operations generated for WCF services within a Windows Store application will be asynchronous using the Task-based asynchronous pattern.</span></span> <span data-ttu-id="9fd28-126">Aby uzyskać więcej informacji, zobacz [zadania asynchroniczne — uproszczenie programowania asynchronicznego z zadaniami](/archive/msdn-magazine/2010/september/async-tasks-simplify-asynchronous-programming-with-tasks).</span><span class="sxs-lookup"><span data-stu-id="9fd28-126">For more information, see [Async Tasks - Simplify Asynchronous Programming with Tasks](/archive/msdn-magazine/2010/september/async-tasks-simplify-asynchronous-programming-with-tasks).</span></span>  
  
 <span data-ttu-id="9fd28-127">Ponieważ konfiguracja jest teraz generowana w kodzie, wszelkie zmiany wprowadzone w pliku Reference.cs zostałyby zastępować za każdym razem, gdy odwołanie do usługi zostanie zaktualizowane.</span><span class="sxs-lookup"><span data-stu-id="9fd28-127">Because configuration is now generated in code, any changes made in the Reference.cs file would be overwritten every time the service reference is updated.</span></span> <span data-ttu-id="9fd28-128">Aby wyeliminować tę sytuację, kod konfiguracji jest generowany w ramach metody częściowej, którą można zaimplementować w klasie proxy klienta.</span><span class="sxs-lookup"><span data-stu-id="9fd28-128">To remedy this situation the configuration code is generated within a partial method, which you can implement in your client proxy class.</span></span> <span data-ttu-id="9fd28-129">Metoda częściowa jest zadeklarowana w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="9fd28-129">The partial method is declared as follows:</span></span>  
  
```csharp  
static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,  
            System.ServiceModel.Description.ClientCredentials clientCredentials);  
```  
  
 <span data-ttu-id="9fd28-130">Następnie można zaimplementować tę metodę częściową i zmienić powiązanie lub punkt końcowy w klasie proxy klienta w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="9fd28-130">You can then implement this partial method and change the binding or endpoint in your client proxy class as follows:</span></span>  
  
```csharp  
public partial class Service1Client : System.ServiceModel.ClientBase<MetroWcfClient.ServiceRefMultiEndpt.IService1>, MetroWcfClient.ServiceRefMultiEndpt.IService1  
    {
        static partial void Configure(System.ServiceModel.Description.ServiceEndpoint serviceEndpoint,
            System.ServiceModel.Description.ClientCredentials clientCredentials)  
        {  
            if (serviceEndpoint.Name ==
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
            }  
            else if (serviceEndpoint.Name ==
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.BasicHttpBinding_IService11.ToString())  
            {  
                serviceEndpoint.Binding.SendTimeout = new System.TimeSpan(0, 1, 0);  
                clientCredentials.UserName.UserName = "username1";  
                clientCredentials.UserName.Password = "password";  
            }  
            else if (serviceEndpoint.Name ==
                    ServiceRefMultiEndpt.Service1Client.EndpointConfiguration.NetTcpBinding_IService1.ToString())  
            {  
                serviceEndpoint.Binding.Name = "MyTcpBinding";  
                serviceEndpoint.Address = new System.ServiceModel.EndpointAddress("net.tcp://localhost/tcp");  
            }  
        }  
    }  
```  
  
### <a name="serialization"></a><span data-ttu-id="9fd28-131">Serializacja</span><span class="sxs-lookup"><span data-stu-id="9fd28-131">Serialization</span></span>  
 <span data-ttu-id="9fd28-132">Następujące serializatory są obsługiwane w aplikacjach ze sklepu Windows:</span><span class="sxs-lookup"><span data-stu-id="9fd28-132">The following serializers are supported in Windows Store applications:</span></span>  
  
1. <span data-ttu-id="9fd28-133">DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="9fd28-133">DataContractSerializer</span></span>  
  
2. <span data-ttu-id="9fd28-134">Klasa DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="9fd28-134">DataContractJsonSerializer</span></span>  
  
3. <span data-ttu-id="9fd28-135">XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="9fd28-135">XmlSerializer</span></span>  
  
> [!WARNING]
> <span data-ttu-id="9fd28-136">Implementacja obiektu XmlDictionaryWriter. Write (DateTime) teraz zapisuje obiekt DateTime jako ciąg.</span><span class="sxs-lookup"><span data-stu-id="9fd28-136">XmlDictionaryWriter.Write(DateTime) now writes the DateTime object as a string.</span></span>  
  
### <a name="security"></a><span data-ttu-id="9fd28-137">Zabezpieczenia</span><span class="sxs-lookup"><span data-stu-id="9fd28-137">Security</span></span>  

<span data-ttu-id="9fd28-138">W aplikacjach ze sklepu Windows obsługiwane są następujące tryby zabezpieczeń:</span><span class="sxs-lookup"><span data-stu-id="9fd28-138">The following security modes are supported in Windows Store applications:</span></span>
  
1. <xref:System.ServiceModel.SecurityMode.None>  
  
2. <xref:System.ServiceModel.SecurityMode.Transport>  
  
3. <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>
  
4. <xref:System.ServiceModel.SecurityMode.Message>
  
<span data-ttu-id="9fd28-139">Następujące typy poświadczeń klienta są obsługiwane w aplikacjach ze sklepu Windows:</span><span class="sxs-lookup"><span data-stu-id="9fd28-139">The following client credential types are supported in Windows Store applications:</span></span>
  
1. <span data-ttu-id="9fd28-140">Brak</span><span class="sxs-lookup"><span data-stu-id="9fd28-140">None</span></span>  
  
2. <span data-ttu-id="9fd28-141">Podstawowy</span><span class="sxs-lookup"><span data-stu-id="9fd28-141">Basic</span></span>  
  
3. <span data-ttu-id="9fd28-142">Szyfrowane</span><span class="sxs-lookup"><span data-stu-id="9fd28-142">Digest</span></span>  
  
4. <span data-ttu-id="9fd28-143">Negotiate</span><span class="sxs-lookup"><span data-stu-id="9fd28-143">Negotiate</span></span>  
  
5. <span data-ttu-id="9fd28-144">NTLM</span><span class="sxs-lookup"><span data-stu-id="9fd28-144">NTLM</span></span>  
  
6. <span data-ttu-id="9fd28-145">Windows</span><span class="sxs-lookup"><span data-stu-id="9fd28-145">Windows</span></span>  
  
7. <span data-ttu-id="9fd28-146">Nazwa użytkownika (zabezpieczenia komunikatów)</span><span class="sxs-lookup"><span data-stu-id="9fd28-146">Username (Message Security)</span></span>  
  
8. <span data-ttu-id="9fd28-147">Windows (Transport Security)</span><span class="sxs-lookup"><span data-stu-id="9fd28-147">Windows (Transport Security)</span></span>  
  
 <span data-ttu-id="9fd28-148">Aby aplikacje ze sklepu Windows mogły uzyskiwać dostęp do domyślnych poświadczeń systemu Windows i je wysyłać, należy włączyć tę funkcję w pliku Package. Appmanifest.</span><span class="sxs-lookup"><span data-stu-id="9fd28-148">In order for Windows Store applications to access and send default Windows credentials, you must enable this functionality within the Package.appmanifest file.</span></span> <span data-ttu-id="9fd28-149">Otwórz ten plik i wybierz kartę możliwości i wybierz pozycję "domyślne poświadczenia systemu Windows".</span><span class="sxs-lookup"><span data-stu-id="9fd28-149">Open this file and select the Capabilities tab and select "Default Windows Credentials".</span></span> <span data-ttu-id="9fd28-150">Umożliwia to aplikacji łączenie się z zasobami intranetowymi, które wymagają poświadczeń domeny.</span><span class="sxs-lookup"><span data-stu-id="9fd28-150">This allows the application to connect to intranet resources that require domain credentials.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9fd28-151">Aby aplikacje ze sklepu Windows mogły wykonywać wywołania między maszynami, należy włączyć inną możliwość nazywaną "siecią domową/służbową".</span><span class="sxs-lookup"><span data-stu-id="9fd28-151">In order for Windows Store applications to make cross machine calls you must enable another capability called "Home/Work Networking".</span></span> <span data-ttu-id="9fd28-152">To ustawienie znajduje się również w pliku Package. Appmanifest na karcie możliwości. Wybierz pole wyboru Sieć domowa/Work.</span><span class="sxs-lookup"><span data-stu-id="9fd28-152">This setting is also in the Package.appmanifest file under the Capabilities tab. Select the Home/Work Networking checkbox.</span></span> <span data-ttu-id="9fd28-153">Zapewnia to aplikacji dostęp przychodzący i wychodzący do sieci zaufanych miejsc użytkownika, takich jak Home i Work.</span><span class="sxs-lookup"><span data-stu-id="9fd28-153">This gives your application inbound and outbound access to the networks of the user's trusted places like home and work.</span></span> <span data-ttu-id="9fd28-154">Przychodzące porty krytyczne są zawsze blokowane.</span><span class="sxs-lookup"><span data-stu-id="9fd28-154">Inbound critical ports are always blocked.</span></span> <span data-ttu-id="9fd28-155">Aby uzyskać dostęp do usług w Internecie, należy również włączyć funkcję internetową (klienta).</span><span class="sxs-lookup"><span data-stu-id="9fd28-155">For accessing services on the internet you must also enable Internet (Client) capability.</span></span>  
  
### <a name="misc"></a><span data-ttu-id="9fd28-156">Różne</span><span class="sxs-lookup"><span data-stu-id="9fd28-156">Misc</span></span>  
 <span data-ttu-id="9fd28-157">Użycie następujących klas jest obsługiwane w przypadku aplikacji ze sklepu Windows:</span><span class="sxs-lookup"><span data-stu-id="9fd28-157">The use of the following classes is supported for Windows Store Applications:</span></span>  
  
1. <xref:System.ServiceModel.ChannelFactory>  
  
2. <xref:System.ServiceModel.DuplexChannelFactory%601>
  
3. <xref:System.ServiceModel.CallbackBehaviorAttribute>  
  
### <a name="defining-service-contracts"></a><span data-ttu-id="9fd28-158">Definiowanie kontraktów usługi</span><span class="sxs-lookup"><span data-stu-id="9fd28-158">Defining Service Contracts</span></span>  
 <span data-ttu-id="9fd28-159">Zalecamy tylko Definiowanie asynchronicznych operacji usługi przy użyciu wzorca asynchronicznego opartego na zadaniach.</span><span class="sxs-lookup"><span data-stu-id="9fd28-159">We recommend only defining asynchronous service operations using the task-based async pattern.</span></span> <span data-ttu-id="9fd28-160">Dzięki temu aplikacje ze sklepu Windows pozostają w stanie reagować podczas wywoływania operacji usługi.</span><span class="sxs-lookup"><span data-stu-id="9fd28-160">This ensures Windows Store applications remain responsive while calling a service operation.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="9fd28-161">Chociaż wyjątek nie zostanie wygenerowany, jeśli zdefiniujesz operację synchroniczną, zdecydowanie zaleca się tylko zdefiniowanie operacji asynchronicznych.</span><span class="sxs-lookup"><span data-stu-id="9fd28-161">While no exception will be thrown if you define a synchronous operation, it is strongly recommended to only define asynchronous operations.</span></span>  
  
### <a name="calling-wcf-services-from-windows-store-applications"></a><span data-ttu-id="9fd28-162">Wywoływanie usług WCF z aplikacji ze sklepu Windows</span><span class="sxs-lookup"><span data-stu-id="9fd28-162">Calling WCF Services from Windows Store Applications</span></span>  
 <span data-ttu-id="9fd28-163">Jak wspomniano wcześniej, przed całą konfiguracją należy wykonać w kodzie w metodzie GetBindingForEndpoint w wygenerowanej klasie proxy.</span><span class="sxs-lookup"><span data-stu-id="9fd28-163">As mentioned before all configuration must be done in code in the GetBindingForEndpoint method in the generated proxy class.</span></span> <span data-ttu-id="9fd28-164">Wywoływanie operacji usługi odbywa się tak samo jak wywołanie metody asynchronicznej opartej na zadaniach, jak pokazano w poniższym fragmencie kodu.</span><span class="sxs-lookup"><span data-stu-id="9fd28-164">Calling a service operation is done the same as calling any task-based asynchronous method as shown in the following code snippet.</span></span>  
  
```csharp  
void async SomeMethod()  
{  
    ServiceClient proxy = new ServiceClient();  
    Task<T> results = await proxy.CallAsync(param1, param2);  
    T result = results.Result;  
    if (result.Success)  
    {  
       // Do something with result  
    }  
}  
```  
  
 <span data-ttu-id="9fd28-165">Zwróć uwagę na użycie słowa kluczowego Async na metodzie wywołującym wywołanie asynchroniczne i słowo kluczowe await podczas wywoływania metody asynchronicznej.</span><span class="sxs-lookup"><span data-stu-id="9fd28-165">Notice the use of the async keyword on the method making the asynchronous call and the await keyword when calling the asynchronous method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fd28-166">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="9fd28-166">See also</span></span>

- [<span data-ttu-id="9fd28-167">Programowanie zabezpieczeń WCF</span><span class="sxs-lookup"><span data-stu-id="9fd28-167">Programming WCF Security</span></span>](programming-wcf-security.md)
- [<span data-ttu-id="9fd28-168">Powiązania</span><span class="sxs-lookup"><span data-stu-id="9fd28-168">Bindings</span></span>](../bindings.md)
