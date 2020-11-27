---
title: HttpTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 088a7bce-6bb2-4839-ad74-f68d4b1aa0f9
ms.openlocfilehash: 2be32591c4844cc6d5d0f02916dd1563bb15dc2a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96288791"
---
# <a name="httptransportbindingelement"></a><span data-ttu-id="70bdd-102">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="70bdd-102">HttpTransportBindingElement</span></span>

<span data-ttu-id="70bdd-103">HttpTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="70bdd-103">HttpTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70bdd-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="70bdd-104">Syntax</span></span>  
  
```csharp
class HttpTransportBindingElement : TransportBindingElement  
{  
  boolean AllowCookies;  
  string AuthenticationScheme;  
  boolean BypassProxyOnLocal;  
  string HostNameComparisonMode;  
  boolean KeepAliveEnabled;  
  sint32 MaxBufferSize;  
  string ProxyAddress;  
  string ProxyAuthenticationScheme;  
  string Realm;  
  string TransferMode;  
  boolean UnsafeConnectionNtlmAuthentication;  
  boolean UseDefaultWebProxy;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="70bdd-105">Metody</span><span class="sxs-lookup"><span data-stu-id="70bdd-105">Methods</span></span>  

 <span data-ttu-id="70bdd-106">Klasa HttpTransportBindingElement nie definiuje żadnych metod.</span><span class="sxs-lookup"><span data-stu-id="70bdd-106">The HttpTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="70bdd-107">Właściwości</span><span class="sxs-lookup"><span data-stu-id="70bdd-107">Properties</span></span>  

 <span data-ttu-id="70bdd-108">Klasa HttpTransportBindingElement ma następujące właściwości:</span><span class="sxs-lookup"><span data-stu-id="70bdd-108">The HttpTransportBindingElement class has the following properties:</span></span>  
  
### <a name="allowcookies"></a><span data-ttu-id="70bdd-109">AllowCookies</span><span class="sxs-lookup"><span data-stu-id="70bdd-109">AllowCookies</span></span>  

 <span data-ttu-id="70bdd-110">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="70bdd-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="70bdd-111">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="70bdd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70bdd-112">Wartość wskazująca, czy klient akceptuje pliki cookie i propaguje je do przyszłych żądań.</span><span class="sxs-lookup"><span data-stu-id="70bdd-112">A value that indicates whether the client accepts cookies and propagates them on future requests.</span></span>  
  
### <a name="authenticationscheme"></a><span data-ttu-id="70bdd-113">AuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="70bdd-113">AuthenticationScheme</span></span>  

 <span data-ttu-id="70bdd-114">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="70bdd-114">Data type: string</span></span>  
  
 <span data-ttu-id="70bdd-115">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="70bdd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70bdd-116">Schemat uwierzytelniania używany do uwierzytelniania żądań klientów przetwarzanych przez odbiornik HTTP.</span><span class="sxs-lookup"><span data-stu-id="70bdd-116">The authentication scheme used to authenticate client requests being processed by an HTTP listener.</span></span>  
  
### <a name="bypassproxyonlocal"></a><span data-ttu-id="70bdd-117">BypassProxyOnLocal</span><span class="sxs-lookup"><span data-stu-id="70bdd-117">BypassProxyOnLocal</span></span>  

 <span data-ttu-id="70bdd-118">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="70bdd-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="70bdd-119">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="70bdd-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70bdd-120">Wartość wskazująca, czy serwery proxy są ignorowane dla adresów lokalnych.</span><span class="sxs-lookup"><span data-stu-id="70bdd-120">A value that indicates whether proxies are ignored for local addresses.</span></span>  
  
### <a name="hostnamecomparisonmode"></a><span data-ttu-id="70bdd-121">HostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="70bdd-121">HostNameComparisonMode</span></span>  

 <span data-ttu-id="70bdd-122">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="70bdd-122">Data type: string</span></span>  
  
 <span data-ttu-id="70bdd-123">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="70bdd-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70bdd-124">Wartość wskazująca, czy nazwa hosta jest używana do uzyskiwania dostępu do usługi podczas dopasowywania identyfikatora URI.</span><span class="sxs-lookup"><span data-stu-id="70bdd-124">A value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>  
  
### <a name="keepaliveenabled"></a><span data-ttu-id="70bdd-125">KeepAliveEnabled</span><span class="sxs-lookup"><span data-stu-id="70bdd-125">KeepAliveEnabled</span></span>  

 <span data-ttu-id="70bdd-126">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="70bdd-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="70bdd-127">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="70bdd-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70bdd-128">Po włączeniu połączenia HTTP są utrzymywane bez względu na poziom aktywności.</span><span class="sxs-lookup"><span data-stu-id="70bdd-128">When enabled, HTTP connections are kept alive regardless of activity level.</span></span>  
  
### <a name="maxbuffersize"></a><span data-ttu-id="70bdd-129">MaxBufferSize</span><span class="sxs-lookup"><span data-stu-id="70bdd-129">MaxBufferSize</span></span>  

 <span data-ttu-id="70bdd-130">Typ danych: sint32</span><span class="sxs-lookup"><span data-stu-id="70bdd-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="70bdd-131">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="70bdd-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70bdd-132">Maksymalny rozmiar puli buforów.</span><span class="sxs-lookup"><span data-stu-id="70bdd-132">The maximum size of the buffer pool.</span></span>  
  
### <a name="proxyaddress"></a><span data-ttu-id="70bdd-133">ProxyAddress</span><span class="sxs-lookup"><span data-stu-id="70bdd-133">ProxyAddress</span></span>  

 <span data-ttu-id="70bdd-134">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="70bdd-134">Data type: string</span></span>  
  
 <span data-ttu-id="70bdd-135">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="70bdd-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70bdd-136">Identyfikator URI, który zawiera adres serwera proxy do użycia w żądaniach HTTP.</span><span class="sxs-lookup"><span data-stu-id="70bdd-136">A URI that contains the address of the proxy to use for HTTP requests.</span></span>  
  
### <a name="proxyauthenticationscheme"></a><span data-ttu-id="70bdd-137">ProxyAuthenticationScheme</span><span class="sxs-lookup"><span data-stu-id="70bdd-137">ProxyAuthenticationScheme</span></span>  

 <span data-ttu-id="70bdd-138">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="70bdd-138">Data type: string</span></span>  
  
 <span data-ttu-id="70bdd-139">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="70bdd-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70bdd-140">Schemat uwierzytelniania używany do uwierzytelniania żądań klientów przetwarzanych przez serwer proxy HTTP.</span><span class="sxs-lookup"><span data-stu-id="70bdd-140">The authentication scheme used to authenticate client requests being processed by an HTTP proxy.</span></span>  
  
### <a name="realm"></a><span data-ttu-id="70bdd-141">Obszar</span><span class="sxs-lookup"><span data-stu-id="70bdd-141">Realm</span></span>  

 <span data-ttu-id="70bdd-142">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="70bdd-142">Data type: string</span></span>  
  
 <span data-ttu-id="70bdd-143">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="70bdd-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70bdd-144">Obszar uwierzytelniania.</span><span class="sxs-lookup"><span data-stu-id="70bdd-144">The authentication realm.</span></span>  
  
### <a name="transfermode"></a><span data-ttu-id="70bdd-145">Elementy TransferMode</span><span class="sxs-lookup"><span data-stu-id="70bdd-145">TransferMode</span></span>  

 <span data-ttu-id="70bdd-146">Typ danych: ciąg</span><span class="sxs-lookup"><span data-stu-id="70bdd-146">Data type: string</span></span>  
  
 <span data-ttu-id="70bdd-147">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="70bdd-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70bdd-148">Wartość określająca, czy komunikaty są buforowane, czy przesyłane strumieniowo, czy też żądanie lub odpowiedź.</span><span class="sxs-lookup"><span data-stu-id="70bdd-148">A value that specifies whether messages are buffered or streamed or a request or response.</span></span>  
  
### <a name="unsafeconnectionntlmauthentication"></a><span data-ttu-id="70bdd-149">UnsafeConnectionNtlmAuthentication</span><span class="sxs-lookup"><span data-stu-id="70bdd-149">UnsafeConnectionNtlmAuthentication</span></span>  

 <span data-ttu-id="70bdd-150">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="70bdd-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="70bdd-151">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="70bdd-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70bdd-152">Wartość wskazująca, czy na serwerze jest włączona funkcja udostępniania niebezpiecznego połączenia.</span><span class="sxs-lookup"><span data-stu-id="70bdd-152">A value that indicates whether Unsafe Connection Sharing is enabled on the server.</span></span>  
  
### <a name="usedefaultwebproxy"></a><span data-ttu-id="70bdd-153">UseDefaultWebProxy</span><span class="sxs-lookup"><span data-stu-id="70bdd-153">UseDefaultWebProxy</span></span>  

 <span data-ttu-id="70bdd-154">Typ danych: wartość logiczna</span><span class="sxs-lookup"><span data-stu-id="70bdd-154">Data type: boolean</span></span>  
  
 <span data-ttu-id="70bdd-155">Typ dostępu: tylko do odczytu</span><span class="sxs-lookup"><span data-stu-id="70bdd-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="70bdd-156">Wartość wskazująca, czy ustawienia serwera proxy dla całego komputera są używane zamiast ustawień określonych przez użytkownika.</span><span class="sxs-lookup"><span data-stu-id="70bdd-156">A value that indicates whether the machine-wide proxy settings are used rather than the user specific settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70bdd-157">Wymagania</span><span class="sxs-lookup"><span data-stu-id="70bdd-157">Requirements</span></span>  
  
|<span data-ttu-id="70bdd-158">PLIK</span><span class="sxs-lookup"><span data-stu-id="70bdd-158">MOF</span></span>|<span data-ttu-id="70bdd-159">Zadeklarowany w ServiceModel. mof.</span><span class="sxs-lookup"><span data-stu-id="70bdd-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="70bdd-160">Przestrzeń nazw</span><span class="sxs-lookup"><span data-stu-id="70bdd-160">Namespace</span></span>|<span data-ttu-id="70bdd-161">Zdefiniowane w root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="70bdd-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="70bdd-162">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="70bdd-162">See also</span></span>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
