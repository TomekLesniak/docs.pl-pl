---
title: Protokoły obsługi komunikatów
ms.date: 03/30/2017
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
ms.openlocfilehash: 69a92bfb406e2e1af3bdcbb0316711dbf531204b
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812058"
---
# <a name="messaging-protocols"></a><span data-ttu-id="d17ec-102">Protokoły obsługi komunikatów</span><span class="sxs-lookup"><span data-stu-id="d17ec-102">Messaging Protocols</span></span>

<span data-ttu-id="d17ec-103">Stos kanału Windows Communication Foundation (WCF) korzysta z kodowania i kanałów transportowych, aby przekształcić wewnętrzną reprezentację komunikatu na format przewodu i wysłać ją przy użyciu określonego transportu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-103">The Windows Communication Foundation (WCF) channel stack employs encoding and transport channels to transform internal message representation into its wire format and send it by using a particular transport.</span></span> <span data-ttu-id="d17ec-104">Najbardziej typowym transportem używanym do współdziałania usług sieci Web jest protokół HTTP, a najpopularniejsze kodowania używane przez usługi sieci Web są oparte na języku XML protokołu SOAP 1,1, SOAP 1,2 i mechanizmu optymalizacji transmisji wiadomości (MTOM).</span><span class="sxs-lookup"><span data-stu-id="d17ec-104">The most common transport used for Web services interoperability is HTTP, and the most common encodings used by Web services are XML-based SOAP 1.1, SOAP 1.2, and Message Transmission Optimization Mechanism (MTOM).</span></span>

<span data-ttu-id="d17ec-105">W tym temacie omówiono szczegóły implementacji WCF dla następujących protokołów używanych przez program <xref:System.ServiceModel.Channels.HttpTransportBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="d17ec-105">This topic covers WCF implementation details for the following protocols employed by <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span>

<span data-ttu-id="d17ec-106">Specyfikacja/dokument:</span><span class="sxs-lookup"><span data-stu-id="d17ec-106">Specification/document:</span></span>

- [<span data-ttu-id="d17ec-107">HTTP 1,1</span><span class="sxs-lookup"><span data-stu-id="d17ec-107">HTTP 1.1</span></span>](https://www.ietf.org/rfc/rfc2616.txt)
- <span data-ttu-id="d17ec-108">[Powiązanie http protokołu SOAP 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508), sekcja 7</span><span class="sxs-lookup"><span data-stu-id="d17ec-108">[SOAP 1.1 HTTP Binding](https://www.w3.org/TR/2000/NOTE-SOAP-20000508), Section 7</span></span>
- <span data-ttu-id="d17ec-109">[Powiązanie http protokołu SOAP 1,2](https://www.w3.org/TR/soap12-part2) Sekcja 7</span><span class="sxs-lookup"><span data-stu-id="d17ec-109">[SOAP 1.2 HTTP Binding](https://www.w3.org/TR/soap12-part2) Section 7</span></span>

<span data-ttu-id="d17ec-110">W tym temacie omówiono szczegóły implementacji programu WCF dotyczące następujących protokołów, które <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> i <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> wykorzystują.</span><span class="sxs-lookup"><span data-stu-id="d17ec-110">This topic covers WCF implementation details for the following protocols  that <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employ.</span></span>

<span data-ttu-id="d17ec-111">Specyfikacja/dokument:</span><span class="sxs-lookup"><span data-stu-id="d17ec-111">Specification/Document:</span></span>

- [<span data-ttu-id="d17ec-112">XML</span><span class="sxs-lookup"><span data-stu-id="d17ec-112">XML</span></span>](https://www.w3.org/TR/REC-xml)
- [<span data-ttu-id="d17ec-113">PROTOKÓŁ SOAP 1,1</span><span class="sxs-lookup"><span data-stu-id="d17ec-113">SOAP 1.1</span></span>](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)
- [<span data-ttu-id="d17ec-114">Rdzeń SOAP 1,2</span><span class="sxs-lookup"><span data-stu-id="d17ec-114">SOAP 1.2 Core</span></span>](https://www.w3.org/TR/soap12-part1/)
- [<span data-ttu-id="d17ec-115">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="d17ec-115">WS-Addressing 2004/08</span></span>](https://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/)
- [<span data-ttu-id="d17ec-116">Usługi sieci Web w formacie W3C o 1,0-Core</span><span class="sxs-lookup"><span data-stu-id="d17ec-116">W3C Web Services Addressing 1.0 - Core</span></span>](https://www.w3.org/TR/2006/REC-ws-addr-core-20060509)
- [<span data-ttu-id="d17ec-117">Usługi sieci Web w formacie W3C adresowanie 1,0 — powiązanie SOAP</span><span class="sxs-lookup"><span data-stu-id="d17ec-117">W3C Web Services Addressing 1.0 - SOAP Binding</span></span>](https://www.w3.org/TR/2006/REC-ws-addr-soap-20060509)
- [<span data-ttu-id="d17ec-118">Usługi sieci Web w formacie W3C adresowanie 1,0 — Powiązanie WSDL</span><span class="sxs-lookup"><span data-stu-id="d17ec-118">W3C Web Services Addressing 1.0 - WSDL Binding</span></span>](https://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/)
- [<span data-ttu-id="d17ec-119">Usługi sieci Web w formacie W3C Addressing 1,0 — metadane</span><span class="sxs-lookup"><span data-stu-id="d17ec-119">W3C Web Services Addressing 1.0 - Metadata</span></span>](https://www.w3.org/TR/ws-addr-metadata/)
- [<span data-ttu-id="d17ec-120">Powiązanie SOAP 1.1 języka WSDL</span><span class="sxs-lookup"><span data-stu-id="d17ec-120">WSDL SOAP1.1 Binding</span></span>](https://www.w3.org/TR/wsdl/)
- [<span data-ttu-id="d17ec-121">Powiązanie WSDL SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="d17ec-121">WSDL SOAP1.2 Binding</span></span>](https://www.w3.org/Submission/wsdl11soap12/)

<span data-ttu-id="d17ec-122">W tym temacie omówiono szczegóły implementacji programu WCF dotyczące następujących protokołów, które są używane <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="d17ec-122">This topic covers WCF implementation details for the following protocols that <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employs.</span></span>

<span data-ttu-id="d17ec-123">Specyfikacja/dokument:</span><span class="sxs-lookup"><span data-stu-id="d17ec-123">Specification/document:</span></span>

- [<span data-ttu-id="d17ec-124">XOP</span><span class="sxs-lookup"><span data-stu-id="d17ec-124">XOP</span></span>](https://www.w3.org/TR/xop10/)
- [<span data-ttu-id="d17ec-125">Powiązanie MTOM + SOAP 1,2</span><span class="sxs-lookup"><span data-stu-id="d17ec-125">MTOM + SOAP 1.2 Binding</span></span>](https://www.w3.org/TR/soap12-mtom/)
- [<span data-ttu-id="d17ec-126">Powiązanie SOAP 1,1</span><span class="sxs-lookup"><span data-stu-id="d17ec-126">MTOM SOAP 1.1 Binding</span></span>](https://www.w3.org/Submission/soap11mtom10/)
- [<span data-ttu-id="d17ec-127">Usługa MTOM — potwierdzenie zasad</span><span class="sxs-lookup"><span data-stu-id="d17ec-127">MTOM WS-Policy Assertion</span></span>](https://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/)

<span data-ttu-id="d17ec-128">W tym temacie są używane następujące przestrzenie nazw XML i skojarzone prefiksy:</span><span class="sxs-lookup"><span data-stu-id="d17ec-128">The following XML namespaces and associated prefixes are used throughout this topic:</span></span>

| <span data-ttu-id="d17ec-129">Prefiks</span><span class="sxs-lookup"><span data-stu-id="d17ec-129">Prefix</span></span> | <span data-ttu-id="d17ec-130">Uniform Resource Identifier przestrzeni nazw (URI)</span><span class="sxs-lookup"><span data-stu-id="d17ec-130">Namespace Uniform Resource Identifier (URI)</span></span> |
|------------|---------------------------------------------------|
| <span data-ttu-id="d17ec-131">s11</span><span class="sxs-lookup"><span data-stu-id="d17ec-131">s11</span></span> | `http://schemas.xmlsoap.org/soap/envelope` |
| <span data-ttu-id="d17ec-132">S12</span><span class="sxs-lookup"><span data-stu-id="d17ec-132">s12</span></span> |`http://www.w3.org/2003/05/soap-envelope` |
| <span data-ttu-id="d17ec-133">WSA</span><span class="sxs-lookup"><span data-stu-id="d17ec-133">wsa</span></span> |`http://www.w3.org/2004/08/addressing` |
| <span data-ttu-id="d17ec-134">wsam</span><span class="sxs-lookup"><span data-stu-id="d17ec-134">wsam</span></span> |`http://www.w3.org/2007/05/addressing/metadata` |
| <span data-ttu-id="d17ec-135">wsap</span><span class="sxs-lookup"><span data-stu-id="d17ec-135">wsap</span></span> |`http://schemas.xmlsoap.org/ws/2004/09/policy/addressing` |
| <span data-ttu-id="d17ec-136">wsa10</span><span class="sxs-lookup"><span data-stu-id="d17ec-136">wsa10</span></span> |`http://www.w3.org/2005/08/addressing` |
| <span data-ttu-id="d17ec-137">wsaw10</span><span class="sxs-lookup"><span data-stu-id="d17ec-137">wsaw10</span></span> |`http://www.w3.org/2006/05/addressing/wsdl` |
| <span data-ttu-id="d17ec-138">XOP</span><span class="sxs-lookup"><span data-stu-id="d17ec-138">xop</span></span> |`http://www.w3.org/2004/08/xop/include` |
| <span data-ttu-id="d17ec-139">xmime</span><span class="sxs-lookup"><span data-stu-id="d17ec-139">xmime</span></span> |`http://www.w3.org/2004/06/xmlmime`<br /><br /> `http://www.w3.org/2005/05/xmlmime` |
| <span data-ttu-id="d17ec-140">różnic</span><span class="sxs-lookup"><span data-stu-id="d17ec-140">dp</span></span> |`http://schemas.microsoft.com/net/2006/06/duplex` |

## <a name="soap-11-and-soap-12"></a><span data-ttu-id="d17ec-141">SOAP 1,1 i SOAP 1,2</span><span class="sxs-lookup"><span data-stu-id="d17ec-141">SOAP 1.1 and SOAP 1.2</span></span>

### <a name="envelope-and-processing-model"></a><span data-ttu-id="d17ec-142">Model kopert i przetwarzania</span><span class="sxs-lookup"><span data-stu-id="d17ec-142">Envelope and Processing Model</span></span>
<span data-ttu-id="d17ec-143">Funkcja WCF implementuje przetwarzanie kopert protokołu SOAP 1,1 przy zastosowaniu profilu podstawowego 1,1 (BP11) i profilu podstawowego 1,0 (SSBP10).</span><span class="sxs-lookup"><span data-stu-id="d17ec-143">WCF implements SOAP 1.1 envelope processing following Basic Profile 1.1 (BP11) and Basic Profile 1.0 (SSBP10).</span></span> <span data-ttu-id="d17ec-144">Przetwarzanie kopert protokołu SOAP 1,2 jest zaimplementowane po SOAP12-part1.</span><span class="sxs-lookup"><span data-stu-id="d17ec-144">SOAP 1.2 Envelope processing is implemented following SOAP12-Part1.</span></span>

<span data-ttu-id="d17ec-145">W tej sekcji opisano niektóre opcje implementacji podjęte przez program WCF w odniesieniu do BP11 i SOAP12-part1.</span><span class="sxs-lookup"><span data-stu-id="d17ec-145">This section explains certain implementation choices taken by WCF with regard to BP11 and SOAP12-Part1.</span></span>

#### <a name="mandatory-header-processing"></a><span data-ttu-id="d17ec-146">Obowiązkowe przetwarzanie nagłówka</span><span class="sxs-lookup"><span data-stu-id="d17ec-146">Mandatory Header Processing</span></span>
<span data-ttu-id="d17ec-147">Funkcja WCF stosuje reguły dotyczące przetwarzania nagłówków oznaczonych `mustUnderstand` w specyfikacjach soap 1,1 i soap 1,2 z następującymi odmianami.</span><span class="sxs-lookup"><span data-stu-id="d17ec-147">WCF follows rules for processing headers marked `mustUnderstand` described in the SOAP 1.1 and SOAP 1.2 specifications, with the following variations.</span></span>

<span data-ttu-id="d17ec-148">Komunikat wprowadzający stos kanału WCF jest przetwarzany przez poszczególne kanały skonfigurowane przez skojarzone elementy powiązania, na przykład kodowanie wiadomości tekstowych, zabezpieczenia, niezawodne komunikaty i transakcje.</span><span class="sxs-lookup"><span data-stu-id="d17ec-148">A message that enters the WCF channel stack is processed by individual channels configured by associated binding elements, for example, Text Message Encoding, Security, Reliable Messaging, and Transactions.</span></span> <span data-ttu-id="d17ec-149">Każdy kanał rozpoznaje nagłówki ze skojarzonej przestrzeni nazw i oznacza je jako zrozumiałe.</span><span class="sxs-lookup"><span data-stu-id="d17ec-149">Each channel recognizes headers from the associated namespace and marks them as understood.</span></span> <span data-ttu-id="d17ec-150">Gdy komunikat przechodzi do dyspozytora, program formatujący operacji odczytuje nagłówki oczekiwane przez odpowiedni kontrakt komunikatów/operacji i oznacza je zrozumiałe.</span><span class="sxs-lookup"><span data-stu-id="d17ec-150">Once a message enters the dispatcher, the operation formatter reads headers expected by the corresponding message/operation contract and marks them understood.</span></span> <span data-ttu-id="d17ec-151">Następnie Dyspozytor weryfikuje, czy wszystkie pozostałe nagłówki nie są zrozumiałe, ale oznaczone jako `mustUnderstand` i zgłasza wyjątek.</span><span class="sxs-lookup"><span data-stu-id="d17ec-151">Then the dispatcher verifies whether any remaining headers are not understood but marked as `mustUnderstand` and throws an exception.</span></span> <span data-ttu-id="d17ec-152">Komunikaty zawierające `mustUnderstand` nagłówki, które są przeznaczone dla odbiorców, nie są przetwarzane przez kod aplikacji odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d17ec-152">Messages that contain `mustUnderstand` headers that are targeted at the recipient are not processed by recipient application code.</span></span>

<span data-ttu-id="d17ec-153">Takie przetwarzanie warstwowe umożliwia rozdzielenie między warstwami infrastruktury i warstwami aplikacji węzła SOAP:</span><span class="sxs-lookup"><span data-stu-id="d17ec-153">Such layered processing allows for separation between infrastructure layers and application layers of the SOAP node:</span></span>

- <span data-ttu-id="d17ec-154">B1111: niezrozumiałe nagłówki są wykrywane po przetworzeniu komunikatu przez stos kanału infrastruktury WCF, ale przed przetworzeniem przez aplikację</span><span class="sxs-lookup"><span data-stu-id="d17ec-154">B1111: Headers that are not understood are detected after the message is processed by the WCF infrastructure channel stack, but before it is processed by application</span></span>

     <span data-ttu-id="d17ec-155">`mustUnderstand`Wartość nagłówka różni się od protokołu soap 1,1 i protokołu soap 1,2.</span><span class="sxs-lookup"><span data-stu-id="d17ec-155">The `mustUnderstand` header value differs between SOAP 1.1 and SOAP 1.2.</span></span> <span data-ttu-id="d17ec-156">Profil podstawowy 1,1 wymaga, aby `mustUnderstand` wartość była równa 0 lub 1 dla komunikatów protokołu SOAP 1,1.</span><span class="sxs-lookup"><span data-stu-id="d17ec-156">Basic Profile 1.1 requires that the `mustUnderstand` value be 0 or 1 for SOAP 1.1 messages.</span></span> <span data-ttu-id="d17ec-157">Protokół SOAP 1,2 dopuszcza wartość 0, 1, `false` i `true` jako wartości, ale zaleca emitowanie kanonicznej reprezentacji `xs:boolean` wartości ( `false` , `true` ).</span><span class="sxs-lookup"><span data-stu-id="d17ec-157">SOAP 1.2 allows 0, 1, `false`, and `true` as values, but recommends emitting a canonical representation of `xs:boolean` values (`false`, `true`).</span></span>

- <span data-ttu-id="d17ec-158">B1112: Funkcja WCF emituje `mustUnderstand` wartości 0 i 1 dla wersji soap 1,1 i soap 1,2 dla koperty protokołu SOAP.</span><span class="sxs-lookup"><span data-stu-id="d17ec-158">B1112: WCF emits `mustUnderstand` values 0 and 1 for both SOAP 1.1 and SOAP 1.2 versions of the SOAP envelope.</span></span> <span data-ttu-id="d17ec-159">Funkcja WCF akceptuje całą przestrzeń wartości `xs:boolean` dla `mustUnderstand` nagłówka (0, 1, `false` , `true` ).</span><span class="sxs-lookup"><span data-stu-id="d17ec-159">WCF accepts the entire value space of `xs:boolean` for the `mustUnderstand` header (0, 1, `false`, `true`)</span></span>

#### <a name="soap-faults"></a><span data-ttu-id="d17ec-160">Błędy SOAP</span><span class="sxs-lookup"><span data-stu-id="d17ec-160">SOAP Faults</span></span>
<span data-ttu-id="d17ec-161">Poniżej znajduje się lista implementacji błędów SOAP specyficznych dla WCF.</span><span class="sxs-lookup"><span data-stu-id="d17ec-161">The following is a list of WCF-specific SOAP fault implementations.</span></span>

- <span data-ttu-id="d17ec-162">B2121: Funkcja WCF zwraca następujące kody błędów SOAP 1,1: `s11:mustUnderstand` , `s11:Client` , i `s11:Server` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-162">B2121: WCF returns the following SOAP 1.1 Fault Codes: `s11:mustUnderstand`, `s11:Client`, and `s11:Server`.</span></span>

- <span data-ttu-id="d17ec-163">B2122: Funkcja WCF zwraca następujące kody błędów SOAP 1,2: `s12:MustUnderstand` , `s12:Sender` , i `s12:Receiver` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-163">B2122: WCF returns the following SOAP 1.2 Fault Codes: `s12:MustUnderstand`, `s12:Sender`, and `s12:Receiver`.</span></span>

### <a name="http-binding"></a><span data-ttu-id="d17ec-164">Powiązanie HTTP</span><span class="sxs-lookup"><span data-stu-id="d17ec-164">HTTP Binding</span></span>

#### <a name="soap-11-http-binding"></a><span data-ttu-id="d17ec-165">Powiązanie HTTP protokołu SOAP 1,1</span><span class="sxs-lookup"><span data-stu-id="d17ec-165">SOAP 1.1 HTTP Binding</span></span>
<span data-ttu-id="d17ec-166">Program WCF implementuje powiązanie HTTP 1.1 protokołu SOAP, postępując zgodnie z sekcją specyfikacji profilu podstawowego 1,1 3,4 z następującymi wyjaśnieniami:</span><span class="sxs-lookup"><span data-stu-id="d17ec-166">WCF implements SOAP1.1 HTTP binding following the Basic Profile 1.1 specification section 3.4 with the following clarifications:</span></span>

- <span data-ttu-id="d17ec-167">B2211: usługa WCF nie implementuje przekierowywania żądań POST protokołu HTTP.</span><span class="sxs-lookup"><span data-stu-id="d17ec-167">B2211: WCF service does not implement redirection of HTTP POST requests.</span></span>

- <span data-ttu-id="d17ec-168">B2212: klienci WCF obsługują pliki cookie protokołu HTTP zgodnie z 3.4.8.</span><span class="sxs-lookup"><span data-stu-id="d17ec-168">B2212: WCF clients support HTTP Cookies in accordance with 3.4.8.</span></span>

#### <a name="soap-12-http-binding"></a><span data-ttu-id="d17ec-169">Powiązanie HTTP protokołu SOAP 1,2</span><span class="sxs-lookup"><span data-stu-id="d17ec-169">SOAP 1.2 HTTP Binding</span></span>
<span data-ttu-id="d17ec-170">Funkcja WCF implementuje powiązania HTTP protokołu SOAP 1,2 zgodnie z opisem w specyfikacji SOAP 1,2-część 2 (SOAP12Part2) z następującymi wyjaśnieniami.</span><span class="sxs-lookup"><span data-stu-id="d17ec-170">WCF implements SOAP 1.2 HTTP binding as described in the SOAP 1.2-part 2 (SOAP12Part2) specification with the following clarifications.</span></span>

<span data-ttu-id="d17ec-171">W protokole SOAP 1,2 wprowadzono opcjonalny parametr akcji dla `application/soap+xml` typu nośnika.</span><span class="sxs-lookup"><span data-stu-id="d17ec-171">SOAP 1.2 introduced an optional action parameter for the `application/soap+xml` media type.</span></span> <span data-ttu-id="d17ec-172">Ten parametr jest przydatny do optymalizowania wysyłania komunikatów bez konieczności analizowania treści komunikatu protokołu SOAP, gdy nie jest używane adresowanie WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="d17ec-172">This parameter is useful to optimize message dispatch without requiring that the body of the SOAP message be parsed when WS-Addressing is not used.</span></span>

- <span data-ttu-id="d17ec-173">R2221: `application/soap+xml` parametr Action, gdy jest obecny w ŻĄDANIU SOAP 1,2, musi być zgodny z `soapAction` atrybutem `wsoap12:operation` elementu wewnątrz odpowiedniego powiązania WSDL.</span><span class="sxs-lookup"><span data-stu-id="d17ec-173">R2221: The `application/soap+xml` action parameter, when present on a SOAP 1.2 request, must match the `soapAction` attribute on the `wsoap12:operation` element inside the corresponding WSDL binding.</span></span>

- <span data-ttu-id="d17ec-174">R2222: `application/soap+xml` parametr Action, gdy jest obecny w komunikacie protokołu SOAP 1,2, musi być zgodny, `wsa:Action` gdy używane są WS-addressing 2004/08 lub WS-addressing 1,0.</span><span class="sxs-lookup"><span data-stu-id="d17ec-174">R2222: The `application/soap+xml` action parameter, when present on a SOAP 1.2 message, must match `wsa:Action` when WS-Addressing 2004/08 or WS-Addressing 1.0 are used.</span></span>

<span data-ttu-id="d17ec-175">Gdy Usługa WS-Addressing jest wyłączona, a żądanie przychodzące nie zawiera parametru akcji, komunikat `Action` jest traktowany jako nieokreślony.</span><span class="sxs-lookup"><span data-stu-id="d17ec-175">When WS-Addressing is disabled and an incoming request does not contain an action parameter, message `Action` is considered not specified.</span></span>

## <a name="ws-addressing"></a><span data-ttu-id="d17ec-176">Adresowanie WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="d17ec-176">WS-Addressing</span></span>
<span data-ttu-id="d17ec-177">Funkcja WCF implementuje 3 wersje WS-Addressing:</span><span class="sxs-lookup"><span data-stu-id="d17ec-177">WCF implements 3 versions of WS-Addressing:</span></span>

- <span data-ttu-id="d17ec-178">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="d17ec-178">WS-Addressing 2004/08</span></span>

- <span data-ttu-id="d17ec-179">W3C Web Services Addressing 1,0 Core (ADDR10-CORE) i powiązania SOAP (ADDR10-SOAP)</span><span class="sxs-lookup"><span data-stu-id="d17ec-179">W3C Web Services Addressing 1.0 Core  (ADDR10-CORE) and SOAP Binding (ADDR10-SOAP)</span></span>

- <span data-ttu-id="d17ec-180">WS-Addressing 1,0 — metadane</span><span class="sxs-lookup"><span data-stu-id="d17ec-180">WS-Addressing 1.0 - Metadata</span></span>

### <a name="endpoint-references"></a><span data-ttu-id="d17ec-181">Odwołania do punktu końcowego</span><span class="sxs-lookup"><span data-stu-id="d17ec-181">Endpoint References</span></span>
<span data-ttu-id="d17ec-182">Wszystkie wersje WS-Addressing, które obsługują program WCF, implementują odwołania do punktów końcowych, aby opisywać punkty końcowe.</span><span class="sxs-lookup"><span data-stu-id="d17ec-182">All versions of WS-Addressing that WCF implements use endpoint references to describe endpoints.</span></span>

#### <a name="endpoint-references-and-ws-addressing-versions"></a><span data-ttu-id="d17ec-183">Odwołania punktów końcowych i wersje WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="d17ec-183">Endpoint References and WS-Addressing Versions</span></span>
<span data-ttu-id="d17ec-184">Funkcja WCF implementuje szereg protokołów infrastruktury, które używają adresów WS-Addressing, w szczególności `EndpointReference` elementów i `W3C.WsAddressing.EndpointReferenceType` klas (na przykład WS-RELIABLEMESSAGING, WS-SECURECONVERSATION i WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="d17ec-184">WCF implements a number of the infrastructure protocols that use WS-Addressing and in particular the `EndpointReference` element and `W3C.WsAddressing.EndpointReferenceType` class (for example, WS-ReliableMessaging, WS-SecureConversation, and WS-Trust).</span></span> <span data-ttu-id="d17ec-185">Usługa WCF obsługuje korzystanie z dowolnej wersji WS-Addressing z innymi protokołami infrastruktury.</span><span class="sxs-lookup"><span data-stu-id="d17ec-185">WCF supports the use of either version of WS-Addressing with other infrastructure protocols.</span></span> <span data-ttu-id="d17ec-186">Punkty końcowe WCF obsługują jedną wersję WS-Addressing na punkt końcowy.</span><span class="sxs-lookup"><span data-stu-id="d17ec-186">WCF endpoints support one version of WS-Addressing per endpoint.</span></span>

<span data-ttu-id="d17ec-187">Dla R3111 przestrzeń nazw dla `EndpointReference` elementu lub typu używana w komunikatach wymienianych z punktem końcowym WCF musi być zgodna z wersją WS-Addressing implementowaną przez ten punkt końcowy.</span><span class="sxs-lookup"><span data-stu-id="d17ec-187">For R3111, the namespace for the `EndpointReference` element or type used in messages exchanged with a WCF endpoint must match the version of WS-Addressing implemented by this endpoint.</span></span>

<span data-ttu-id="d17ec-188">Na przykład, jeśli punkt końcowy programu WCF implementuje protokół WS-ReliableMessaging, `AcksTo` nagłówek zwrócony przez ten punkt końcowy `CreateSequenceResponse` używa wersji WS-Addressing, która jest `EncodingBinding` określana przez element dla tego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="d17ec-188">For example, if a WCF endpoint implements WS-ReliableMessaging, the `AcksTo` header returned by such an endpoint inside `CreateSequenceResponse` uses the WS-Addressing version that the `EncodingBinding` element specifies for this endpoint.</span></span>

#### <a name="endpoint-references-and-metadata"></a><span data-ttu-id="d17ec-189">Odwołania do punktów końcowych i metadane</span><span class="sxs-lookup"><span data-stu-id="d17ec-189">Endpoint References and Metadata</span></span>
<span data-ttu-id="d17ec-190">Niektóre scenariusze wymagają komunikacji metadanych lub odwołania do metadanych dla danego punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="d17ec-190">A number of scenarios require communicating metadata or a reference to metadata for a given endpoint.</span></span>

<span data-ttu-id="d17ec-191">B3121: Funkcja WCF korzysta z mechanizmów opisanych w sekcji specyfikacji WS-MetadataExchange (MEX) 6, aby uwzględnić metadane dla odwołań do punktów końcowych przez wartość lub przez odwołanie.</span><span class="sxs-lookup"><span data-stu-id="d17ec-191">B3121: WCF employs mechanisms described in the WS-MetadataExchange (MEX) specification Section 6 to include metadata for endpoint references by value or by reference.</span></span>

<span data-ttu-id="d17ec-192">Rozważmy scenariusz, w którym usługa WCF wymaga uwierzytelniania przy użyciu tokenu "Security Assertions Markup Language (SAML)" wystawionego przez wystawcę tokenów w `http://sts.fabrikam123.com` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-192">Consider a scenario where a WCF service requires authentication using a Security Assertions Markup Language (SAML) token issued by the token issuer at `http://sts.fabrikam123.com`.</span></span> <span data-ttu-id="d17ec-193">Punkt końcowy WCF opisuje to wymaganie uwierzytelniania przy użyciu `sp:IssuedToken` potwierdzenia z zagnieżdżonym `sp:Issuer` potwierdzeniem wskazującym wystawcę tokenu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-193">The WCF endpoint describes this authentication requirement by using `sp:IssuedToken` assertion with a nested `sp:Issuer` assertion pointing to the token issuer.</span></span> <span data-ttu-id="d17ec-194">Aplikacje klienckie, które uzyskują dostęp do `sp:Issuer` potwierdzenia, muszą wiedzieć, jak komunikować się z punktem końcowym wystawcy tokenu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-194">Client applications that access the `sp:Issuer` assertion need to know how to communicate with the token issuer endpoint.</span></span> <span data-ttu-id="d17ec-195">Klient musi znać metadane dotyczące wystawcy tokenu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-195">The client needs to know metadata about the token issuer.</span></span> <span data-ttu-id="d17ec-196">Przy użyciu rozszerzeń metadanych odwołań punktów końcowych zdefiniowanych w MEX, WCF zawiera odwołanie do metadanych wystawcy tokenu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-196">Using the endpoint reference metadata extensions defined in MEX, WCF provides a reference to the token issuer metadata.</span></span>

```xml
<sp:IssuedToken>
  <sp:Issuer>
    <wsa10:Address>
      http://sts.fabrikam123.com
    </wsa10:Address>
    <wsa10:Metadata>
      <mex:Metadata>
        <mex:MetadataSection>
          <mex:MetadataReference>
            <wsa10:Address>
              http://sts.fabrikam123.com/mex
            </wsa10:Address>
          </mex:MetadataReference>
        </mex:MetadataSection>
      </mex:Metadata>
    </wsa10:Metadata>
  </sp:Issuer>
</sp:IssuedToken>
```

### <a name="message-addressing-headers"></a><span data-ttu-id="d17ec-197">Nagłówki adresów komunikatów</span><span class="sxs-lookup"><span data-stu-id="d17ec-197">Message Addressing Headers</span></span>

#### <a name="message-headers"></a><span data-ttu-id="d17ec-198">Nagłówki komunikatów</span><span class="sxs-lookup"><span data-stu-id="d17ec-198">Message Headers</span></span>
<span data-ttu-id="d17ec-199">W przypadku wersji WS-Addressing WCF używa następujących nagłówków komunikatów zgodnie ze specyfikacją,, `wsa:To` , `wsa:ReplyTo` `wsa:Action` `wsa:MessageID` i `wsa:RelatesTo` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-199">For both WS-Addressing versions, WCF uses the following message headers as prescribed by the specifications `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`,and `wsa:RelatesTo`.</span></span>

<span data-ttu-id="d17ec-200">B3211: dla wszystkich wersji WS-Addressing program WCF honoruje, ale nie wygenerował z Box nagłówków komunikatów WS-Addressing `wsa:FaultTo` i `wsa:From` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-200">B3211: For all WS-Addressing versions, WCF honors, but does not produce out of the box, WS-Addressing message headers `wsa:FaultTo` and `wsa:From`.</span></span>

<span data-ttu-id="d17ec-201">Aplikacje, które współpracują z aplikacjami WCF, mogą dodawać te nagłówki komunikatów, a program WCF odpowiednio przetwarza je.</span><span class="sxs-lookup"><span data-stu-id="d17ec-201">Applications that interact with WCF applications can add these message headers and WCF will process them accordingly.</span></span>

#### <a name="reference-parameters-and-properties"></a><span data-ttu-id="d17ec-202">Parametry odwołania i właściwości</span><span class="sxs-lookup"><span data-stu-id="d17ec-202">Reference Parameters and Properties</span></span>

<span data-ttu-id="d17ec-203">WCF implementuje przetwarzanie parametrów odwołań punktów końcowych i właściwości odwołania zgodnie z odpowiednimi specyfikacjami.</span><span class="sxs-lookup"><span data-stu-id="d17ec-203">WCF implements processing of endpoint reference parameters and reference properties in accordance with respective specifications.</span></span>

<span data-ttu-id="d17ec-204">B3221: gdy jest skonfigurowany do korzystania z WS-Addressing 2004/08, punkty końcowe WCF nie rozróżnią między przetwarzaniem właściwości odwołania i parametrów referencyjnych.</span><span class="sxs-lookup"><span data-stu-id="d17ec-204">B3221: When configured to use WS-Addressing 2004/08, WCF endpoints do not differentiate between processing Reference Properties and Reference Parameters.</span></span>

### <a name="message-exchange-patterns"></a><span data-ttu-id="d17ec-205">Wzorce wymiany komunikatów</span><span class="sxs-lookup"><span data-stu-id="d17ec-205">Message Exchange Patterns</span></span>
<span data-ttu-id="d17ec-206">Sekwencja komunikatów występujących w wywołaniu operacji usługi sieci Web jest nazywana *wzorcem wymiany komunikatów*.</span><span class="sxs-lookup"><span data-stu-id="d17ec-206">The sequence of messages involved in the Web service operation invocation is referred to as the *message exchange pattern*.</span></span> <span data-ttu-id="d17ec-207">Usługa WCF obsługuje jednokierunkowe wzorce wymiany komunikatów z żądaniami i odpowiedziami.</span><span class="sxs-lookup"><span data-stu-id="d17ec-207">WCF supports one-way, request-reply, and duplex message exchange patterns.</span></span> <span data-ttu-id="d17ec-208">W tej sekcji objaśniono wymagania WS-Addressing dotyczące przetwarzania komunikatów w zależności od używanego wzorca wymiany komunikatów.</span><span class="sxs-lookup"><span data-stu-id="d17ec-208">This section clarifies WS-Addressing requirements on message processing depending on the message exchange pattern being used.</span></span>

<span data-ttu-id="d17ec-209">W tej sekcji Obiekt żądający wysyła pierwszy komunikat, a obiekt odpowiadający otrzymuje pierwszy komunikat.</span><span class="sxs-lookup"><span data-stu-id="d17ec-209">Throughout this section, the requester sends the first message and the responder receives the first message.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="d17ec-210">Komunikat jednokierunkowy</span><span class="sxs-lookup"><span data-stu-id="d17ec-210">One-Way Message</span></span>
<span data-ttu-id="d17ec-211">Gdy punkt końcowy programu WCF jest skonfigurowany do obsługi komunikatów, `Action` które mają być zgodne ze wzorcem jednokierunkowym, punkt końcowy programu WCF postępuje zgodnie z poniższymi zachowaniami i wymaganiami.</span><span class="sxs-lookup"><span data-stu-id="d17ec-211">When a WCF endpoint is configured to support messages with a given `Action` to follow a one-way pattern, the WCF endpoint follows the following behaviors and requirements.</span></span> <span data-ttu-id="d17ec-212">O ile nie określono inaczej, zachowania i reguły mają zastosowanie w przypadku obu wersji WS-Addressing obsługiwanych w programie WCF:</span><span class="sxs-lookup"><span data-stu-id="d17ec-212">Unless otherwise specified, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>

- <span data-ttu-id="d17ec-213">R3311: Obiekt żądający musi zawierać `wsa:To` `wsa:Action` nagłówki, i i dla wszystkich parametrów referencyjnych określonych przez odwołanie do punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="d17ec-213">R3311: The requester must include `wsa:To`, `wsa:Action`, and headers for all reference parameters specified by the endpoint reference.</span></span> <span data-ttu-id="d17ec-214">W przypadku użycia protokołu WS-Addressing 2004/08 i [właściwości odwołania] są określone przez odwołanie do punktu końcowego, odpowiednie nagłówki należy dodać do komunikatu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-214">When WS-Addressing 2004/08 is used and [reference properties] are specified by the endpoint reference, the corresponding headers must be added to the message too.</span></span>

- <span data-ttu-id="d17ec-215">B3312: Obiekt żądający może zawierać `MessageID` , `ReplyTo` , i `FaultTo` nagłówki.</span><span class="sxs-lookup"><span data-stu-id="d17ec-215">B3312: The requester may include `MessageID`, `ReplyTo`, and `FaultTo` headers.</span></span> <span data-ttu-id="d17ec-216">Infrastruktura odbiornika zignoruje je i zostanie przeniesiona do aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d17ec-216">The receiver infrastructure will ignore them, and they will be passed to the application.</span></span>

- <span data-ttu-id="d17ec-217">R3313: gdy jest używany protokół HTTP i nie jest wysyłany żaden komunikat w postawce odpowiedzi HTTP, obiekt odpowiadający musi wysłać odpowiedź HTTP z pustą treścią i kodem stanu HTTP 202.</span><span class="sxs-lookup"><span data-stu-id="d17ec-217">R3313: When HTTP is used and no message is being sent on the HTTP response leg, the responder must send an HTTP response with an empty body and an HTTP 202 status code.</span></span>

     <span data-ttu-id="d17ec-218">Gdy transport HTTP jest używany, a kontrakt operacji deklaruje komunikat jednokierunkowy, odpowiedź HTTP może być nadal używana do wysyłania komunikatów dotyczących infrastruktury — na przykład, niezawodne komunikaty mogą wysyłać `SequenceAcknowledgement` komunikat w odpowiedzi HTTP.</span><span class="sxs-lookup"><span data-stu-id="d17ec-218">When the HTTP transport is in use and the operation contract declares a message one-way, the HTTP response can still be used for sending infrastructure messages—for example, reliable messaging can send a `SequenceAcknowledgement` message on an HTTP response.</span></span>

- <span data-ttu-id="d17ec-219">B3314: obiekt odpowiadający WCF nie wysyła komunikatu o błędzie w odpowiedzi na komunikat jednokierunkowy.</span><span class="sxs-lookup"><span data-stu-id="d17ec-219">B3314: The WCF responder does not send a fault message in response to a one-way message.</span></span>

#### <a name="request-reply"></a><span data-ttu-id="d17ec-220">Żądanie i odpowiedź</span><span class="sxs-lookup"><span data-stu-id="d17ec-220">Request-Reply</span></span>
<span data-ttu-id="d17ec-221">Gdy punkt końcowy programu WCF jest skonfigurowany dla komunikatu z danym `Action` do przestrzegania wzorca żądanie-odpowiedź, punkt końcowy WCF postępuje zgodnie z zachowaniem i wymaganiami poniżej.</span><span class="sxs-lookup"><span data-stu-id="d17ec-221">When a WCF endpoint is configured for a message with a given `Action` to follow the request-reply pattern, the WCF endpoint follows the behaviors and requirements below.</span></span> <span data-ttu-id="d17ec-222">O ile nie określono inaczej, zachowania i reguły dotyczą obu wersji WS-Addressing obsługiwanych w programie WCF:</span><span class="sxs-lookup"><span data-stu-id="d17ec-222">Unless specified otherwise, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>

- <span data-ttu-id="d17ec-223">R3321: Obiekt żądający musi zawierać w żądaniu `wsa:To` , `wsa:Action` , `wsa:MessageID` i nagłówkach wszystkie parametry odwołania lub właściwości odwołania (lub obie) określone przez odwołanie do punktu końcowego.</span><span class="sxs-lookup"><span data-stu-id="d17ec-223">R3321: The requester must include in the request `wsa:To`, `wsa:Action`, `wsa:MessageID`, and headers for all reference parameters or reference properties (or both) specified by the endpoint reference.</span></span>

- <span data-ttu-id="d17ec-224">R3322: w przypadku korzystania z protokołu WS-Addressing 2004/08 `ReplyTo` należy również uwzględnić je w żądaniu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-224">R3322: When WS-Addressing 2004/08 is used, `ReplyTo` must also be included in the request.</span></span>

- <span data-ttu-id="d17ec-225">R3323: gdy Usługa WS-Addressing 1,0 jest używana i `ReplyTo` nie występuje w żądaniu, zostanie użyte domyślne odwołanie do punktu końcowego z właściwością [address] równą `http://www.w3.org/2005/08/addressing/anonymous` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-225">R3323: When WS-Addressing 1.0 is used and `ReplyTo` is not present in the request, a default endpoint reference with the [address] property equal to `http://www.w3.org/2005/08/addressing/anonymous` is used.</span></span>

- <span data-ttu-id="d17ec-226">R3324: Obiekt żądający musi zawierać `wsa:To` , `wsa:Action` , i `wsa:RelatesTo` nagłówki w komunikacie odpowiedzi, a także nagłówki dla wszystkich parametrów odwołania lub właściwości odwołania (lub obu) określonych przez odwołanie do `ReplyTo` punktu końcowego w żądaniu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-226">R3324: The requester must include `wsa:To`, `wsa:Action`, and `wsa:RelatesTo` headers in the reply message, as well as headers for all reference parameters or reference properties (or both) specified by the `ReplyTo` endpoint reference in the request.</span></span>

### <a name="web-services-addressing-faults"></a><span data-ttu-id="d17ec-227">Błędy adresowania usług sieci Web</span><span class="sxs-lookup"><span data-stu-id="d17ec-227">Web Services Addressing Faults</span></span>
<span data-ttu-id="d17ec-228">R3411: Funkcja WCF tworzy następujące błędy zdefiniowane przez WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="d17ec-228">R3411: WCF produces the following faults defined by WS-Addressing 2004/08.</span></span>

| <span data-ttu-id="d17ec-229">Kod</span><span class="sxs-lookup"><span data-stu-id="d17ec-229">Code</span></span> | <span data-ttu-id="d17ec-230">Przyczyna</span><span class="sxs-lookup"><span data-stu-id="d17ec-230">Cause</span></span> |
|----------|-----------|
| `wsa:DestinationUnreachable` | <span data-ttu-id="d17ec-231">Wiadomość dotarła do `ReplyTo` , która różni się od adresu zwrotnego dla tego kanału; brak punktu końcowego nasłuchiwania pod adresem określonym w nagłówku do.</span><span class="sxs-lookup"><span data-stu-id="d17ec-231">The message arrived with a `ReplyTo` that is different from the reply address established for this channel; there is no endpoint listening at the address specified in the To header.</span></span> |
| `wsa:ActionNotSupported` | <span data-ttu-id="d17ec-232">kanały infrastruktury lub Dyspozytor skojarzony z punktem końcowym nie rozpoznają akcji określonej w `Action` nagłówku.</span><span class="sxs-lookup"><span data-stu-id="d17ec-232">the infrastructure channels or dispatcher associated with the endpoint do not recognize the action specified in the `Action` header.</span></span> |

<span data-ttu-id="d17ec-233">R3412: Funkcja WCF tworzy następujące błędy zdefiniowane przez WS-Addressing 1,0.</span><span class="sxs-lookup"><span data-stu-id="d17ec-233">R3412: WCF produces the following faults defined by WS-Addressing 1.0.</span></span>

| <span data-ttu-id="d17ec-234">Kod</span><span class="sxs-lookup"><span data-stu-id="d17ec-234">Code</span></span> | <span data-ttu-id="d17ec-235">Przyczyna</span><span class="sxs-lookup"><span data-stu-id="d17ec-235">Cause</span></span> |
|----------|-----------|
| `wsa10:InvalidAddressingHeader` | <span data-ttu-id="d17ec-236">Duplikuj `wsa:To` , `wsa:ReplyTo` `wsa:From` lub `wsa:MessageID` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-236">Duplicate `wsa:To`, `wsa:ReplyTo`, `wsa:From` or `wsa:MessageID`.</span></span> <span data-ttu-id="d17ec-237">Duplikat `wsa:RelatesTo` z tą samą `RelationshipType` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-237">Duplicate `wsa:RelatesTo` with the same `RelationshipType`.</span></span> |
| `wsa10:MessageAddressingHeaderRequired` | <span data-ttu-id="d17ec-238">Brak wymaganego nagłówka Addressing.</span><span class="sxs-lookup"><span data-stu-id="d17ec-238">The required Addressing header is missing.</span></span> |
| `wsa10:DestinationUnreachable` | <span data-ttu-id="d17ec-239">Wiadomość dotarła do `ReplyTo` , która różni się od adresu odpowiedzi dla tego kanału.</span><span class="sxs-lookup"><span data-stu-id="d17ec-239">The message arrived with a `ReplyTo` that is different from the reply address established for this channel.</span></span> <span data-ttu-id="d17ec-240">Brak punktu końcowego nasłuchiwania pod adresem określonym w nagłówku do.</span><span class="sxs-lookup"><span data-stu-id="d17ec-240">There is no endpoint listening at the address specified in the To header.</span></span> |
| `wsa10:ActionNotSupported` | <span data-ttu-id="d17ec-241">Akcja określona w `Action` nagłówku nie jest rozpoznawana przez kanały infrastruktury ani dyspozytora skojarzone z punktem końcowym.</span><span class="sxs-lookup"><span data-stu-id="d17ec-241">An action specified in the `Action` header is not recognized by the infrastructure channels or dispatcher associated with the endpoint.</span></span> |
| `wsa10:EndpointUnavailable` | <span data-ttu-id="d17ec-242">Kanał RM wysyła ten błąd ponownie, wskazując, że punkt końcowy nie przetworzy sekwencji na podstawie badania `CreateSequence` nagłówków adresowania wiadomości.</span><span class="sxs-lookup"><span data-stu-id="d17ec-242">The RM channel sends this fault back, indicating the endpoint will not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span> |

<span data-ttu-id="d17ec-243">Kod w powyższych tabelach jest mapowany na `FaultCode` w protokole soap 1,1 i `SubCode` (z kodem = nadawca) w protokole SOAP 1,2.</span><span class="sxs-lookup"><span data-stu-id="d17ec-243">Code in the preceding tables maps to `FaultCode` in SOAP 1.1 and `SubCode` (with Code=Sender) in SOAP 1.2.</span></span>

### <a name="wsdl-11-binding-and-ws-policy-assertions"></a><span data-ttu-id="d17ec-244">Powiązania WSDL 1,1 i potwierdzenia WS-Policy</span><span class="sxs-lookup"><span data-stu-id="d17ec-244">WSDL 1.1 Binding and WS-Policy Assertions</span></span>

#### <a name="indicating-use-of-ws-addressing"></a><span data-ttu-id="d17ec-245">Wskazywanie użycia protokołu WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="d17ec-245">Indicating Use of WS-Addressing</span></span>
<span data-ttu-id="d17ec-246">Funkcja WCF używa potwierdzeń zasad, aby wskazać obsługę punktu końcowego dla określonej wersji WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="d17ec-246">WCF uses policy assertions to indicate endpoint support for a particular WS-Addressing version.</span></span>

<span data-ttu-id="d17ec-247">Następujące potwierdzenie zasad ma podmiot zasad punktu końcowego [WS-PA] i wskazuje, że komunikaty wysyłane i odbierane z punktu końcowego muszą używać WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="d17ec-247">The following policy assertion has Endpoint Policy Subject [WS-PA] and indicates messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>

```xml
<wsap:UsingAddressing />
```

<span data-ttu-id="d17ec-248">To potwierdzenie zasad rozszerza specyfikację WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="d17ec-248">This policy assertion augments the WS-Addressing 2004/08 specification.</span></span>

<span data-ttu-id="d17ec-249">Poniższe potwierdzenie zasad wskazuje, że komunikaty wysyłane/odbierane muszą używać WS-Addressing 1,0.</span><span class="sxs-lookup"><span data-stu-id="d17ec-249">The following policy assertion this indicates that messages sent/received must use WS-Addressing 1.0.</span></span>

```xml
<wsam:Addressing/>
```

<span data-ttu-id="d17ec-250">Następujące potwierdzenie zasad ma podmiot zasad punktu końcowego [WS-PA] i wskazuje, że komunikaty wysyłane i odbierane z punktu końcowego muszą używać WS-Addressing 2004/08.</span><span class="sxs-lookup"><span data-stu-id="d17ec-250">The following policy assertion has an Endpoint Policy Subject [WS-PA] and indicates that messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>

```xml
<wsaw10:UsingAddressing />
```

<span data-ttu-id="d17ec-251">`wsaw10:UsingAddressing`Element jest popożyczony z [WS-Addressing-WSDL] i jest używany w kontekście protokołu WS-Policy zgodności z tą specyfikacją w sekcji 3.1.2.</span><span class="sxs-lookup"><span data-stu-id="d17ec-251">The `wsaw10:UsingAddressing` element is borrowed from [WS-Addressing-WSDL] and is used in the context of WS-Policy in compliance with that specification, section 3.1.2.</span></span>

<span data-ttu-id="d17ec-252">Korzystanie z adresowania nie zmienia semantyki powiązań WSDL 1,1, SOAP 1,1 i SOAP 1,2 protokołu HTTP.</span><span class="sxs-lookup"><span data-stu-id="d17ec-252">Use of Addressing does not alter the semantics of WSDL 1.1, SOAP 1.1, and SOAP 1.2 HTTP Bindings.</span></span> <span data-ttu-id="d17ec-253">Na przykład jeśli oczekuje się, że odpowiedź jest wysyłana do punktu końcowego, który używa adresu i powiązania HTTP w języku WSDL 1. x, należy wysłać odpowiedź przy użyciu odpowiedzi HTTP.</span><span class="sxs-lookup"><span data-stu-id="d17ec-253">For example, if a reply is expected to a request that is sent to an endpoint that uses Addressing and WSDL SOAP 1.x HTTP binding, the reply must be sent by using the HTTP response.</span></span>

<span data-ttu-id="d17ec-254">W przypadku odpowiedzi wysyłanych za pośrednictwem odpowiedzi HTTP, potwierdzenie WS-AM:</span><span class="sxs-lookup"><span data-stu-id="d17ec-254">For replies sent over the http response, the WS-AM assertion is:</span></span>

```xml
<wsam:AnonymousResponses/>
```

<span data-ttu-id="d17ec-255">Kompletne potwierdzenie zasad może wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="d17ec-255">The complete policy assertion might look like this:</span></span>

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:AnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

<span data-ttu-id="d17ec-256">Istnieją jednak wzorce wymiany komunikatów, które korzystają z dwóch niezależnych połączeń HTTP, które są nawiązywane między obiektem żądającym a obiektem odpowiadającym, na przykład niechciane komunikaty jednokierunkowe wysyłane przez obiekt odpowiadający.</span><span class="sxs-lookup"><span data-stu-id="d17ec-256">However, there are message exchange patterns that benefit from having two independent converse HTTP connections established between the requester and the responder, for example, unsolicited one-way messages sent by the responder.</span></span>

<span data-ttu-id="d17ec-257">Program WCF oferuje funkcję, za pomocą której dwa bazowe kanały transportu mogą tworzyć złożony kanał dupleksowy, w którym jeden kanał jest używany do przesyłania komunikatów wejściowych, a drugi jest używany do przesyłania komunikatów wyjściowych.</span><span class="sxs-lookup"><span data-stu-id="d17ec-257">WCF offers a feature by which two underlying transport channels can form a Composite Duplex channel, where one channel is used for input messages and the other is used for output messages.</span></span> <span data-ttu-id="d17ec-258">W przypadku transportu HTTP złożony dupleks oferuje dwa odwrotne połączenia HTTP.</span><span class="sxs-lookup"><span data-stu-id="d17ec-258">In the case of the HTTP Transport, Composite Duplex provides two converse HTTP connections.</span></span> <span data-ttu-id="d17ec-259">Żądający używa jednego połączenia do wysyłania komunikatów do obiektu odpowiadającego, a obiekt odpowiadający używa innego do wysyłania komunikatów z powrotem do osoby żądającej.</span><span class="sxs-lookup"><span data-stu-id="d17ec-259">The requester uses one connection to send messages to the responder, and the responder uses the other to send messages back to the requester.</span></span>

<span data-ttu-id="d17ec-260">W przypadku odpowiedzi wysyłanych za pomocą oddzielnych żądań HTTP potwierdzenie protokołu WS-am to</span><span class="sxs-lookup"><span data-stu-id="d17ec-260">For replies sent over separate http requests, the ws-am assertion is</span></span>

```xml
<wsam:NonAnonymousResponses/>
```

<span data-ttu-id="d17ec-261">Kompletne potwierdzenie zasad może wyglądać następująco:</span><span class="sxs-lookup"><span data-stu-id="d17ec-261">The complete policy assertion might look like this:</span></span>

```xml
<wsam:Addressing>
    <wsp:Policy>
        <wsam:NonAnonymousResponses />
    </wsp:Policy>
</wsam:Addressing>
```

<span data-ttu-id="d17ec-262">Korzystanie z następującego potwierdzenia, który ma podmiot zasad punktu końcowego [WS-PA] w punktach końcowych korzystających z języka WSDL 1,1 SOAP 1. x powiązania HTTP wymaga, aby w przypadku komunikatów pływających od żądającego do obiektu odpowiadającego i obiektu odpowiadającego odpowiednio zażądano dwóch oddzielnych połączeń HTTP.</span><span class="sxs-lookup"><span data-stu-id="d17ec-262">Use of the following assertion that has Endpoint Policy Subject [WS-PA] on endpoints that use WSDL 1.1 SOAP 1.x HTTP bindings requires two separate converse HTTP connections to be used for messages flowing from requester to responder and responder to requester, respectively.</span></span>

```xml
<cdp:CompositeDuplex/>
```

<span data-ttu-id="d17ec-263">Poprzednia instrukcja prowadzi do następujących wymagań w `wsa:ReplyTo` nagłówku komunikatów żądania:</span><span class="sxs-lookup"><span data-stu-id="d17ec-263">The previous statement leads to the following requirements on the `wsa:ReplyTo` header for request messages:</span></span>

- <span data-ttu-id="d17ec-264">R3514: komunikaty żądania wysyłane do punktu końcowego muszą mieć `ReplyTo` Nagłówek z `[address]` właściwością, która nie jest równa, `http://www.w3.org/2005/08/addressing/anonymous` Jeśli punkt końcowy używa powiązania HTTP języka WSDL 1,1 SOAP 1. x i ma alternatywę dla zasad z `wsap10:UsingAddressing` `wsap:UsingAddressing` załączonym parametrem lub z potwierdzeniem `cdp:CompositeDuplex` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-264">R3514: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property not equal to `http://www.w3.org/2005/08/addressing/anonymous` if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with a `wsap10:UsingAddressing` or `wsap:UsingAddressing` assertion coupled with `cdp:CompositeDuplex` attached.</span></span>

- <span data-ttu-id="d17ec-265">R3515: komunikaty żądania wysyłane do punktu końcowego muszą mieć `ReplyTo` Nagłówek z `[address]` właściwością równą `http://www.w3.org/2005/08/addressing/anonymous` lub nie mieć `ReplyTo` nagłówka, jeśli punkt końcowy używa powiązania HTTP języka WSDL 1,1 SOAP 1. x i ma alternatywę dla zasad z `wsap10:UsingAddressing` potwierdzeniem i nie ma `cdp:CompositeDuplex` dołączonego potwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="d17ec-265">R3515: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property equal to `http://www.w3.org/2005/08/addressing/anonymous`, or not have a `ReplyTo` header at all, if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap10:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>

- <span data-ttu-id="d17ec-266">R3516: komunikaty żądania wysyłane do punktu końcowego muszą mieć `ReplyTo` nagłówek o `[address]` Właściwości równej, `http://www.w3.org/2005/08/addressing/anonymous` Jeśli punkt końcowy używa powiązania HTTP języka WSDL 1,1 SOAP 1. x i ma alternatywę dla zasad z `wsap:UsingAddressing` potwierdzeniem i nie ma `cdp:CompositeDuplex` dołączonego potwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="d17ec-266">R3516: Request messages sent to an endpoint must have a `ReplyTo` header with an `[address]` property equal to `http://www.w3.org/2005/08/addressing/anonymous` if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>

<span data-ttu-id="d17ec-267">Specyfikacja specyfikacji WSDL WS-Addressing próbuje opisać podobne powiązania protokołów przez wprowadzenie elementu `<wsaw:Anonymous/>` z trzema wartościami tekstowymi (wymagane, opcjonalne i zabronione), aby wskazać wymagania dotyczące `wsa:ReplyTo` nagłówka (sekcja 3,2).</span><span class="sxs-lookup"><span data-stu-id="d17ec-267">The WS-addressing WSDL specification attempts to describe similar protocol bindings by introducing an element `<wsaw:Anonymous/>` with three textual values (required, optional, and prohibited) to indicate requirements on the `wsa:ReplyTo` header (section 3.2).</span></span> <span data-ttu-id="d17ec-268">Niestety, taka definicja elementu nie jest szczególnie użyteczna jako potwierdzenie w kontekście usługi WS-Policy, ponieważ wymaga rozszerzeń specyficznych dla domeny do obsługi przecięcia się z alternatywami przy użyciu takiego elementu jako potwierdzenia.</span><span class="sxs-lookup"><span data-stu-id="d17ec-268">Unfortunately, such element definition is not particularly usable as an assertion in the context of WS-Policy, because it requires domain-specific extensions to support the intersection of alternatives using such an element as an assertion.</span></span> <span data-ttu-id="d17ec-269">Definicja elementu wskazuje również wartość `ReplyTo` nagłówka, a nie zachowanie punktu końcowego w sieci, co sprawia, że jest to specyficzne dla transportu HTTP.</span><span class="sxs-lookup"><span data-stu-id="d17ec-269">Such element definition also indicates the value of the `ReplyTo` header as opposed to the endpoint behavior on the wire, which makes it specific to HTTP transport.</span></span>

#### <a name="action-definition"></a><span data-ttu-id="d17ec-270">Definicja akcji</span><span class="sxs-lookup"><span data-stu-id="d17ec-270">Action Definition</span></span>
<span data-ttu-id="d17ec-271">WS-Addressing 2004/08 definiuje `wsa:Action` atrybut dla `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elementów.</span><span class="sxs-lookup"><span data-stu-id="d17ec-271">WS-Addressing 2004/08 defines a `wsa:Action` attribute for the `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements.</span></span> <span data-ttu-id="d17ec-272">Powiązanie WSDL WS-Addressing 1,0 (WS-ADDR10-WSDL) definiuje podobny atrybut, `wsaw10:Action` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-272">WS-Addressing 1.0 WSDL Binding (WS-ADDR10-WSDL) defines a similar attribute, `wsaw10:Action`.</span></span>

<span data-ttu-id="d17ec-273">Jedyną różnicą między nimi jest domyślna semantyka wzorca akcji opisana w sekcji 3.3.2 protokołu WS-ADDR i sekcja 4.4.4 protokołu WS-ADDR10-WSDL.</span><span class="sxs-lookup"><span data-stu-id="d17ec-273">The only difference between the two is the default Action pattern semantics described in section 3.3.2 of WS-ADDR and section 4.4.4 of WS-ADDR10-WSDL, respectively.</span></span>

<span data-ttu-id="d17ec-274">Rozsądne jest posiadanie dwóch punktów końcowych, które współużytkują ten sam `portType` (lub kontrakt, w terminologii WCF), ale korzystają z różnych wersji WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="d17ec-274">It is a reasonable to have two endpoints that share the same `portType` (or contract, in WCF terminology) but using different versions of WS-Addressing.</span></span> <span data-ttu-id="d17ec-275">Jeśli jednak dana akcja jest definiowana przez `portType` i nie powinna się zmieniać w punktach końcowych implementujących `portType` , nie można obsługiwać obu domyślnych wzorców akcji.</span><span class="sxs-lookup"><span data-stu-id="d17ec-275">But given that Action is defined by the `portType` and should not change across the endpoints that implement the `portType`, it becomes impossible to support both default action patterns.</span></span>

<span data-ttu-id="d17ec-276">Aby rozwiązać ten controversy, WCF obsługuje jedną wersję `Action` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-276">To resolve this controversy, WCF supports a single version of the `Action` attribute.</span></span>

<span data-ttu-id="d17ec-277">B3521: Funkcja WCF używa `wsaw10:Action` atrybutu dla `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elementów, zgodnie z definicją w specyfikacji WS-ADDR10-WSDL, w celu określenia `Action` identyfikatora URI dla odpowiednich komunikatów niezależnie od wersji WS-Addressing używanej przez punkt końcowy.</span><span class="sxs-lookup"><span data-stu-id="d17ec-277">B3521: WCF uses the `wsaw10:Action` attribute on `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements as defined in WS-ADDR10-WSDL to determine the `Action` URI for the corresponding messages irrespective of the WS-Addressing version used by the endpoint.</span></span>

#### <a name="use-endpoint-reference-inside-wsdl-port"></a><span data-ttu-id="d17ec-278">Użyj odwołania do punktu końcowego w porcie WSDL</span><span class="sxs-lookup"><span data-stu-id="d17ec-278">Use Endpoint Reference Inside WSDL Port</span></span>
<span data-ttu-id="d17ec-279">Usługa WS-ADDR10 — WSDL sekcja 4,1 rozszerza `wsdl:port` element w celu uwzględnienia `<wsa10:EndpointReference…/>` elementu podrzędnego opisującego punkt końcowy w warunkach WS-Addressing.</span><span class="sxs-lookup"><span data-stu-id="d17ec-279">WS-ADDR10-WSDL section 4.1 extends the `wsdl:port` element to include the `<wsa10:EndpointReference…/>` child element to describe the endpoint in WS-Addressing terms.</span></span> <span data-ttu-id="d17ec-280">Funkcja WCF rozszerza to narzędzie na WS-Addressing 2004/08, co umożliwia `<wsa:EndpointReference…/>` Wyświetlanie jako elementu podrzędnego `wsdl:port` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-280">WCF expands this utility on WS-Addressing 2004/08, allowing `<wsa:EndpointReference…/>` to appear as a child element of `wsdl:port`.</span></span>

- <span data-ttu-id="d17ec-281">R3531: Jeśli punkt końcowy ma dołączoną zasadę alternatywną z `<wsaw10:UsingAddressing/>` potwierdzeniem zasad, odpowiadający `wsdl:port` element może zawierać element podrzędny `<wsa10:EndpointReference …/>` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-281">R3531: If an endpoint has an attached policy alternative with a `<wsaw10:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa10:EndpointReference …/>`.</span></span>

- <span data-ttu-id="d17ec-282">R3532: Jeśli `wsdl:port` zawiera element podrzędny `<wsa10:EndpointReference …/>` , `wsa10:EndpointReference/wsa10:Address` wartość elementu podrzędnego musi być zgodna z wartością `@address` atrybutu elementu równorzędnego `wsdl:port` / `wsdl:location` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-282">R3532: If a `wsdl:port` contains a child element `<wsa10:EndpointReference …/>`, the `wsa10:EndpointReference/wsa10:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>

- <span data-ttu-id="d17ec-283">R3533: Jeśli punkt końcowy ma dołączoną zasadę alternatywną z `<wsap:UsingAddressing/>` potwierdzeniem zasad, odpowiadający `wsdl:port` element może zawierać element podrzędny `<wsa:EndpointReference …/>` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-283">R3533: If an endpoint has an attached policy alternative with `<wsap:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa:EndpointReference …/>`.</span></span>

- <span data-ttu-id="d17ec-284">R3534: Jeśli `wsdl:port` zawiera element podrzędny `<wsa:EndpointReference …/>` , `wsa:EndpointReference/wsa:Address` wartość elementu podrzędnego musi być zgodna z wartością `@address` atrybutu elementu równorzędnego `wsdl:port` / `wsdl:location` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-284">R3534: If a `wsdl:port` contains a child element `<wsa:EndpointReference …/>`, the `wsa:EndpointReference/wsa:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>

### <a name="composition-with-ws-security"></a><span data-ttu-id="d17ec-285">Tworzenie kompozycji przy użyciu protokołu WS-Security</span><span class="sxs-lookup"><span data-stu-id="d17ec-285">Composition with WS-Security</span></span>
<span data-ttu-id="d17ec-286">Zgodnie z sekcjami dotyczącymi zagadnień związanych z bezpieczeństwem w usłudze WS-ADDR i WS-ADDR10 zaleca się, aby wszystkie nagłówki komunikatów adresowych były podpisane razem z treścią komunikatu w celu powiązania ich ze sobą.</span><span class="sxs-lookup"><span data-stu-id="d17ec-286">According to security consideration sections in WS-ADDR and WS-ADDR10, all addressing message headers are recommended to be signed together with the message body to bind them together.</span></span>

<span data-ttu-id="d17ec-287">Gdy Usługa WS-Security jest używana do ochrony integralności komunikatów, nagłówki komunikatów WS-Addressing, a także nagłówki, które wynikają z parametrów odwołania lub właściwości (lub obu), muszą być podpisane razem z treścią wiadomości.</span><span class="sxs-lookup"><span data-stu-id="d17ec-287">When WS-Security is used for message integrity protection, WS-Addressing message headers as well as headers resulted from reference parameters or properties (or both) must be signed together with the body of the message.</span></span>

### <a name="examples"></a><span data-ttu-id="d17ec-288">Przykłady</span><span class="sxs-lookup"><span data-stu-id="d17ec-288">Examples</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="d17ec-289">Komunikat jednokierunkowy</span><span class="sxs-lookup"><span data-stu-id="d17ec-289">One-Way Message</span></span>
<span data-ttu-id="d17ec-290">W tym scenariuszu nadawca wysyła wiadomość jednokierunkową do odbiorcy.</span><span class="sxs-lookup"><span data-stu-id="d17ec-290">In this scenario, the sender sends a one-way message to the receiver.</span></span> <span data-ttu-id="d17ec-291">Używane są protokół SOAP 1,2, HTTP 1,1 i W3C WS-Addressing 1,0.</span><span class="sxs-lookup"><span data-stu-id="d17ec-291">SOAP 1.2, HTTP 1.1, and W3C WS-Addressing 1.0 are used.</span></span>

<span data-ttu-id="d17ec-292">Struktura komunikatu żądania: nagłówki wiadomości obejmują `wsa10:To` `wsa10:Action` elementy i.</span><span class="sxs-lookup"><span data-stu-id="d17ec-292">The Request Message Structure: The message headers include `wsa10:To` and `wsa10:Action` elements.</span></span> <span data-ttu-id="d17ec-293">Treść wiadomości zawiera określony `<app:Ping>` element z przestrzeni nazw aplikacji.</span><span class="sxs-lookup"><span data-stu-id="d17ec-293">The message body includes a specific `<app:Ping>` element from the application namespace.</span></span>

<span data-ttu-id="d17ec-294">Nagłówki HTTP: miejsce docelowe w WPISie dopasowuje identyfikator URI w `wsa10:To` elemencie.</span><span class="sxs-lookup"><span data-stu-id="d17ec-294">HTTP Headers: The destination in POST matches the URI in the `wsa10:To` element.</span></span>

<span data-ttu-id="d17ec-295">Nagłówek Content-Type ma wartość `application/soap+xml` , zgodnie z wymaganiami protokołu SOAP 1,2.</span><span class="sxs-lookup"><span data-stu-id="d17ec-295">The Content-Type header has the value of `application/soap+xml` as required by SOAP 1.2.</span></span> <span data-ttu-id="d17ec-296">Parametry `charset` i `action` są dołączone.</span><span class="sxs-lookup"><span data-stu-id="d17ec-296">Parameters `charset` and `action` are included.</span></span> <span data-ttu-id="d17ec-297">`action`Parametr nagłówka Content-Type jest zgodny z wartością `wsa10:Action` nagłówka komunikatu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-297">The `action` parameter of the Content-Type header matches the value of the `wsa10:Action` message header.</span></span>

```http
POST http://fabrikam123.com/Service HTTP/1.1
Content-Type: application/soap+xml; charset=utf-8;  
              action="http://fabrikam123.com/Service/OneWay"
Host: 131.107.72.15
Content-Length: 1501
Expect: 100-continue
Proxy-Connection: Keep-Alive
<s12:Envelope>
  <s12:Header>
    <wsa10:To s12:mustUnderstand="1">
        http://fabrikam123.com/Service
    </wsa10:To>
    <wsa10:Action s12:mustUnderstand="1">
        http://fabrikam123.com/Service/OneWay
    </wsa10:Action>
  </s12:Header>
  <s12:Body>
    <Ping xmlns="http://fabrikam123.com/Service/">
      <Text>Hello World</Text>
    </Ping>
  </s12:Body>
</s12:Envelope>
```

<span data-ttu-id="d17ec-298">Odbiornik reaguje na pustą odpowiedź HTTP i status 202.</span><span class="sxs-lookup"><span data-stu-id="d17ec-298">The receiver responds with an empty HTTP response and status 202.</span></span> <span data-ttu-id="d17ec-299">Przykład odpowiedzi HTTP:</span><span class="sxs-lookup"><span data-stu-id="d17ec-299">An example of the HTTP response:</span></span>

```http
HTTP/1.1 202 Accepted
Date: Fri, 15 Jul 2005 08:56:07 GMT
Server: Microsoft-IIS/6.0
MicrosoftOfficeWebServer: 5.0_Pub
X-Powered-By: ASP.NET
X-AspNet-Version: 2.0.50215
Cache-Control: private
Content-Length: 0
```

## <a name="soap-message-transmission-optimization-mechanism"></a><span data-ttu-id="d17ec-300">Mechanizm optymalizacji transmisji komunikatów SOAP</span><span class="sxs-lookup"><span data-stu-id="d17ec-300">SOAP Message Transmission Optimization Mechanism</span></span>
<span data-ttu-id="d17ec-301">W tej sekcji opisano szczegóły implementacji programu WCF dotyczące protokołu SOAP protokołu HTTP.</span><span class="sxs-lookup"><span data-stu-id="d17ec-301">This section describes the WCF implementation details for the HTTP SOAP MTOM.</span></span> <span data-ttu-id="d17ec-302">Technologia MTOM to mechanizm kodowania komunikatów protokołu SOAP tej samej klasy, co tradycyjne kodowanie tekstu/XML lub kodowanie binarne WCF.</span><span class="sxs-lookup"><span data-stu-id="d17ec-302">MTOM technology is SOAP message encoding mechanism of the same class as traditional text/XML encoding or WCF Binary encoding.</span></span> <span data-ttu-id="d17ec-303">MTOM obejmuje następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="d17ec-303">MTOM includes the following:</span></span>

- <span data-ttu-id="d17ec-304">Mechanizm kodowania i pakowania XML opisany przez [XOP], który optymalizuje elementy informacji XML zawierające dane binarne kodowane algorytmem Base64 do oddzielnych części binarnych.</span><span class="sxs-lookup"><span data-stu-id="d17ec-304">An XML encoding and packaging mechanism described by [XOP] that optimizes XML information items containing base64-encoded binary data into separate binary parts.</span></span>

- <span data-ttu-id="d17ec-305">Hermetyzacja MIME pakietu XOP, która serializować sprawdzonych XML i każdej binarnej części pakietu XOP do oddzielnej części MIME.</span><span class="sxs-lookup"><span data-stu-id="d17ec-305">A MIME encapsulation of the XOP package that serializes the XML Infoset and each binary part of the XOP package into a separate MIME part.</span></span>

- <span data-ttu-id="d17ec-306">Kodowanie MIME XOP zastosowane do koperty SOAP 1. x.</span><span class="sxs-lookup"><span data-stu-id="d17ec-306">A MIME XOP encoding applied to SOAP 1.x Envelope.</span></span>

- <span data-ttu-id="d17ec-307">Powiązanie transportu HTTP.</span><span class="sxs-lookup"><span data-stu-id="d17ec-307">An HTTP transport binding.</span></span>

<span data-ttu-id="d17ec-308">Możliwe jest korzystanie z mechanizmu MTOM z transportem innym niż HTTP z funkcją WCF.</span><span class="sxs-lookup"><span data-stu-id="d17ec-308">It is possible to use MTOM with non-HTTP transports with WCF.</span></span> <span data-ttu-id="d17ec-309">Jednak w tym temacie będziemy skupić się na protokole HTTP.</span><span class="sxs-lookup"><span data-stu-id="d17ec-309">However, in this topic we will focus on HTTP.</span></span>

<span data-ttu-id="d17ec-310">Format MTOM wykorzystuje duży zestaw specyfikacji obejmujących sam MTOM, XOP i MIME.</span><span class="sxs-lookup"><span data-stu-id="d17ec-310">The MTOM format leverages a large set of specifications covering MTOM itself, XOP, and MIME.</span></span> <span data-ttu-id="d17ec-311">Modularność tego zestawu specyfikacji sprawia, że jest nieco trudno odtworzyć dokładne wymagania dotyczące formatu i semantyki przetwarzania.</span><span class="sxs-lookup"><span data-stu-id="d17ec-311">Modularity of this specification set makes it somewhat difficult to reconstruct exact requirements on the format and processing semantics.</span></span> <span data-ttu-id="d17ec-312">W tej sekcji opisano wymagania dotyczące formatu i przetwarzania dla powiązania HTTP MTOM.</span><span class="sxs-lookup"><span data-stu-id="d17ec-312">This section describes the format and processing requirements for MTOM HTTP binding.</span></span>

### <a name="mtom-message-encoding"></a><span data-ttu-id="d17ec-313">Kodowanie komunikatów MTOM</span><span class="sxs-lookup"><span data-stu-id="d17ec-313">MTOM Message Encoding</span></span>

#### <a name="generating-mtom-messages"></a><span data-ttu-id="d17ec-314">Generowanie komunikatów mechanizmu MTOM</span><span class="sxs-lookup"><span data-stu-id="d17ec-314">Generating MTOM messages</span></span>
<span data-ttu-id="d17ec-315">Sekcja [XOP] 3,1 opisuje proces kodowania XML z elementami informacji o elementach, które zawierają wartości Base64 do zdefiniowanego w sposób abstrakcyjny pakietu XOP.</span><span class="sxs-lookup"><span data-stu-id="d17ec-315">The [XOP] section 3.1 describes the process of encoding XML with element information items that contain base64 values into an abstractly defined XOP package.</span></span>

<span data-ttu-id="d17ec-316">Poniższa sekwencja kroków opisuje proces kodowania dotyczący mechanizmu MTOM:</span><span class="sxs-lookup"><span data-stu-id="d17ec-316">The following sequence of steps describes the MTOM-specific encoding process:</span></span>

1. <span data-ttu-id="d17ec-317">Upewnij się, że koperta protokołu SOAP do zakodowania nie zawiera elementu informacji o elemencie z `[namespace name]` `http://www.w3.org/2004/08/xop/include` i z `[local name]` `Include` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-317">Ensure that the SOAP Envelope to be encoded contains no element information item with a `[namespace name]` of `http://www.w3.org/2004/08/xop/include` and a `[local name]` of `Include`.</span></span>

2. <span data-ttu-id="d17ec-318">Utwórz pusty pakiet MIME.</span><span class="sxs-lookup"><span data-stu-id="d17ec-318">Create an empty MIME package.</span></span>

3. <span data-ttu-id="d17ec-319">Zidentyfikuj w oryginalnym kodzie XML sprawdzonych elementy informacji, które mają być zoptymalizowane.</span><span class="sxs-lookup"><span data-stu-id="d17ec-319">Identify within the Original XML Infoset the element information items to be optimized.</span></span> <span data-ttu-id="d17ec-320">W przypadku elementów, które mają być optymalizowane, znaki wchodzące w `[children]` skład elementu informacji o elemencie muszą mieć postać kanoniczną `xs:base64Binary` (patrz XSD-2, 3.2.16 base64Binary) i nie może zawierać żadnych znaków białych poprzedzających, wbudowanych w lub następujących niebiałych zawartości.</span><span class="sxs-lookup"><span data-stu-id="d17ec-320">For the items to be optimized, the characters that make up the `[children]` of the element information item must be in the canonical form of `xs:base64Binary` (see XSD-2, 3.2.16 base64Binary) and must not contain any white-space characters preceding, inline with, or following the non-white-space content.</span></span>

4. <span data-ttu-id="d17ec-321">Utwórz kopertę protokołu SOAP XOP, która jest kopią oryginalnej koperty protokołu SOAP, ale z elementami podrzędnymi każdego elementu informacji o elemencie zidentyfikowanym w poprzednim kroku zamienionym przez `xop:Include` element informacji o elemencie utworzony w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="d17ec-321">Create an XOP SOAP Envelope that is a copy of the Original SOAP Envelope, but with the children of each element information item identified in the previous step replaced by an `xop:Include` element information item constructed as follows:</span></span>

    1. <span data-ttu-id="d17ec-322">Przekształć zamienione znaki na dane binarne, przetwarzając je jako dane zakodowane algorytmem Base64.</span><span class="sxs-lookup"><span data-stu-id="d17ec-322">Transform the replaced characters into binary data by processing them as base64-encoded data.</span></span>

    2. <span data-ttu-id="d17ec-323">Wygeneruj unikatową wartość nagłówka Content-ID spełniającą wymagania R3133 i R3134.</span><span class="sxs-lookup"><span data-stu-id="d17ec-323">Generate a unique Content-ID header value that satisfies requirements R3133 and R3134.</span></span>

    3. <span data-ttu-id="d17ec-324">Wygeneruj nagłówek MIME Content-Transfer-Encoding z wartością binarną.</span><span class="sxs-lookup"><span data-stu-id="d17ec-324">Generate a Content-Transfer-Encoding MIME header with the value binary.</span></span>

    4. <span data-ttu-id="d17ec-325">Jeśli element informacji o elemencie, który jest zoptymalizowany ([nadrzędny] nowo wstawionego elementu `xop:Include` informacji o elemencie) zawiera `xmime:contentType` element informacji o atrybucie, wygeneruj nagłówek MIME typu zawartości z wartością `xmime:contentType` atrybutu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-325">If the element information item being optimized (the [parent] of the newly inserted `xop:Include` element information item) has an `xmime:contentType` attribute information item, generate a Content-Type MIME header with the value of the `xmime:contentType` attribute.</span></span>

    5. <span data-ttu-id="d17ec-326">Generowanie nowej binarnej części MIME z zawartością utworzoną przez dane binarne, zdekodowaną od zastąpionych znaków przetworzonych jako algorytm Base64, Content-ID z nagłówka 4B, Content-Transfer-Encoding z 4.</span><span class="sxs-lookup"><span data-stu-id="d17ec-326">Generate a new binary MIME part with content formed by binary data decoded from the replaced characters processed as base64, Content-ID header from 4b, Content- Transfer-Encoding header from 4c, Content-Type header if generated in step 4d.</span></span>

    6. <span data-ttu-id="d17ec-327">Dodaj `href` atrybut do `xop:Include` elementu z wartością CID: URI pochodzącą z wartości nagłówka Content-ID wygenerowanej w kroku 4B.</span><span class="sxs-lookup"><span data-stu-id="d17ec-327">Add an `href` attribute to the `xop:Include` element with the value cid: uri derived from Content-ID header value generated in step 4b.</span></span> <span data-ttu-id="d17ec-328">Usuń otaczające znaki " \<" and "> ", adres URL-Escape pozostałego ciągu i Dodaj prefiks `cid:` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-328">Remove the enclosing "\<" and ">" characters, URL-escape the remaining string, and add the prefix `cid:`.</span></span> <span data-ttu-id="d17ec-329">Następujący minimalny zestaw znaków musi być zmieniony przez RFC1738 i RFC2396.</span><span class="sxs-lookup"><span data-stu-id="d17ec-329">The following minimum character set is required to be escaped by RFC1738 and RFC2396.</span></span> <span data-ttu-id="d17ec-330">Inne znaki można zmienić.</span><span class="sxs-lookup"><span data-stu-id="d17ec-330">Other characters can be escaped.</span></span>

        ```
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"
        ```

5. <span data-ttu-id="d17ec-331">Utwórz główną część MIME z kopertą protokołu SOAP XOP z kroku 4.</span><span class="sxs-lookup"><span data-stu-id="d17ec-331">Create a root MIME part with the XOP SOAP Envelope from step 4.</span></span>

6. <span data-ttu-id="d17ec-332">Napisz nagłówki HTTP, w tym nagłówek Content-Type.</span><span class="sxs-lookup"><span data-stu-id="d17ec-332">Write the HTTP headers, including the HTTP Content-Type header.</span></span>

7. <span data-ttu-id="d17ec-333">Napisz pakiet MIME.</span><span class="sxs-lookup"><span data-stu-id="d17ec-333">Write the MIME package.</span></span>

#### <a name="processing-mtom-messages"></a><span data-ttu-id="d17ec-334">Przetwarzanie komunikatów MTOM</span><span class="sxs-lookup"><span data-stu-id="d17ec-334">Processing MTOM messages</span></span>
<span data-ttu-id="d17ec-335">Przetwarzanie komunikatu MTOM to dokładne odwrócenie procesu opisanego w poprzedniej sekcji "Generowanie komunikatów mechanizmu MTOM":</span><span class="sxs-lookup"><span data-stu-id="d17ec-335">Processing of an MTOM message is the exact reverse of the process described in the preceding "Generating MTOM messages" section:</span></span>

1. <span data-ttu-id="d17ec-336">Upewnij się, że główna część MIME ma typ Content-Type `application/xop+xml` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-336">Ensure the root MIME part has the Content-Type `application/xop+xml`.</span></span>

2. <span data-ttu-id="d17ec-337">Konstruowanie koperty protokołu SOAP przez przeanalizowanie głównej części MIME pakietu jako dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="d17ec-337">Construct a SOAP Envelope by parsing the root MIME part of the package as an XML document.</span></span> <span data-ttu-id="d17ec-338">Kodowanie znaków jest określane przez `charset` parametr typu zawartości głównej części MIME.</span><span class="sxs-lookup"><span data-stu-id="d17ec-338">Character encoding is determined by the `charset` parameter of the Content-Type of the root MIME part.</span></span>

3. <span data-ttu-id="d17ec-339">Dla każdego elementu informacji o elemencie w konstruowanej kopercie SOAP, która ma jako jedyny element członkowski właściwości [Children] elementu `xop:Include` informacji o elemencie:</span><span class="sxs-lookup"><span data-stu-id="d17ec-339">For each element information item in the constructed SOAP Envelope, which has, as the sole member of its [children] property, an `xop:Include` element information item:</span></span>

    1. <span data-ttu-id="d17ec-340">Usuń `cid:` prefiks i Anuluj ucieczkę wszystkich sekwencji URI i ucieczki (RFC 2396) w wartości `@href` atrybutu `xop:Include` elementu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-340">Remove the `cid:` prefix and unescape all URI-escape sequences (RFC 2396) in the value of the `@href` attribute of the `xop:Include` element.</span></span> <span data-ttu-id="d17ec-341">Ujmij ciąg wynikowy w " \<", "> ".</span><span class="sxs-lookup"><span data-stu-id="d17ec-341">Enclose the result string in "\<", ">".</span></span>

    2. <span data-ttu-id="d17ec-342">Znajdź część MIME z wartością nagłówka Content-ID zgodną z ciągiem pochodzącym z kroku 3a.</span><span class="sxs-lookup"><span data-stu-id="d17ec-342">Locate the MIME part with the Content-ID header value that matches the string derived in step 3a.</span></span>

    3. <span data-ttu-id="d17ec-343">Zastąp `xop:Include` element informacji o elemencie, który pojawia się we `children` właściwości każdego elementu z elementami informacji o znakach, które reprezentują kanoniczne kodowanie Base64 (patrz XSD-2, 3.2.16 base64Binary) treści jednostki części MIME wymienionej w kroku 3B (efektywnie Zastąp `xop:Include` element informacji o elemencie danymi przetworzonymi z części pakietu).</span><span class="sxs-lookup"><span data-stu-id="d17ec-343">Replace the `xop:Include` element information item that appears in the `children` property of each item with the character information items that represent the canonical base64 encoding (see XSD-2, 3.2.16 base64Binary) of the entity body of the MIME part identified in step 3b (effectively replace the `xop:Include` element information item with the data reconstructed from the package part).</span></span>

#### <a name="http-content-type-header"></a><span data-ttu-id="d17ec-344">Nagłówek zawartości HTTP-Type</span><span class="sxs-lookup"><span data-stu-id="d17ec-344">HTTP Content-Type Header</span></span>
<span data-ttu-id="d17ec-345">Poniżej znajduje się lista wyjaśnień programu WCF dla formatu nagłówka Content-Type w formacie SOAP 1. x zakodowanych na podstawie wymagań określonych w samej specyfikacji MTOM i pochodzących od MTOM i RFC 2387.</span><span class="sxs-lookup"><span data-stu-id="d17ec-345">The following is a list of WCF clarifications for the format of the HTTP Content-Type header of a SOAP 1.x MTOM-encoded message derived from requirements stated in the MTOM specification itself and are derived from MTOM and RFC 2387.</span></span>

- <span data-ttu-id="d17ec-346">R4131: nagłówek Content-Type typu HTTP musi mieć wartość wieloczęściowego/powiązanego (bez uwzględniania wielkości liter) i jego parametrów.</span><span class="sxs-lookup"><span data-stu-id="d17ec-346">R4131: An HTTP Content-Type header must have the value of multipart/related (case-insensitive) and its parameters.</span></span> <span data-ttu-id="d17ec-347">W nazwach parametrów jest rozróżniana wielkość liter.</span><span class="sxs-lookup"><span data-stu-id="d17ec-347">Parameter names are case-insensitive.</span></span> <span data-ttu-id="d17ec-348">Kolejność parametrów nie jest istotna.</span><span class="sxs-lookup"><span data-stu-id="d17ec-348">Parameter order is not significant.</span></span>

- <span data-ttu-id="d17ec-349">Pełna kopia zapasowa-Naura (BNF) nagłówka Content-Type dla komunikatów MIME jest wymieniona w dokumencie RFC 2045, sekcja 5,1.</span><span class="sxs-lookup"><span data-stu-id="d17ec-349">The full Backus-Naur Form (BNF) of the Content-Type header for MIME messages is listed in RFC 2045, section 5.1.</span></span>

- <span data-ttu-id="d17ec-350">R4132: nagłówek Content-Type typu HTTP musi mieć parametr typu z wartością `application/xop+xml` ujętą w znaki podwójnego cudzysłowu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-350">R4132: An HTTP Content-Type header must have a type parameter with the value `application/xop+xml` enclosed in double quotation marks.</span></span>

<span data-ttu-id="d17ec-351">Chociaż wymóg używania podwójnego cudzysłowu nie jest jawny w dokumencie RFC 2387, tekst przestrzega, że wszystkie parametry typu nośnika wieloczęściowego/powiązanego najprawdopodobniej zawierają zastrzeżone znaki, takie jak " \@ " lub "/", a w związku z tym potrzebują podwójnych cudzysłowów.</span><span class="sxs-lookup"><span data-stu-id="d17ec-351">While the requirement to use double quotation marks is not explicit in RFC 2387, the text observes that all of the multipart/related media type parameters most likely contain reserved characters like "\@" or "/" and therefore need double quotation marks.</span></span>

- <span data-ttu-id="d17ec-352">R4133: nagłówek Content-Type w formacie HTTP powinien mieć parametr początkowy z wartością nagłówka Content-ID części MIME, która zawiera kopertę SOAP 1. x ujętą w znaki podwójnego cudzysłowu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-352">R4133: An HTTP Content-Type header should have a start parameter with the value of the Content-ID header of the MIME part that contains the SOAP 1.x Envelope, enclosed in double quotation marks.</span></span> <span data-ttu-id="d17ec-353">Jeśli parametr Start zostanie pominięty, pierwsza część MIME musi zawierać kopertę SOAP 1. x.</span><span class="sxs-lookup"><span data-stu-id="d17ec-353">If the start parameter is omitted, the first MIME part must contain the SOAP 1.x Envelope.</span></span>

- <span data-ttu-id="d17ec-354">R4134: nagłówek Content-Type typu HTTP dla komunikatu zakodowanego za pomocą mechanizmu MTOM protokołu SOAP 1,1 musi zawierać parametr Start-info z wartością text/xml ujętą w znaki podwójnego cudzysłowu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-354">R4134: An HTTP Content-Type header for a SOAP 1.1 MTOM encoded message must include the start-info parameter with the value of text/xml, enclosed in double quotation marks.</span></span>

- <span data-ttu-id="d17ec-355">R4135: nagłówek Content-Type typu HTTP dla komunikatu kodowanego przy użyciu mechanizmu MTOM protokołu SOAP 1,2 musi zawierać parametr Start-info z wartością `application/soap+xml` ujętą w znaki podwójnego cudzysłowu.</span><span class="sxs-lookup"><span data-stu-id="d17ec-355">R4135: An HTTP Content-Type header for a SOAP 1.2 MTOM-encoded message must include the start-info parameter with the value of `application/soap+xml`, enclosed in double quotation marks.</span></span>

- <span data-ttu-id="d17ec-356">R4136: nagłówek Content-Type dla protokołu SOAP 1. x kodowany algorytmem MTOM musi mieć parametr granicy z wartością (ujętą w znaki podwójnego cudzysłowu), która pasuje do granicy MIME BNF zdefiniowanej w dokumencie RFC 2046, sekcja 5.1.1</span><span class="sxs-lookup"><span data-stu-id="d17ec-356">R4136: HTTP Content-Type header for a SOAP 1.x MTOM-encoded message must have the boundary parameter with the value (enclosed in double quotation marks) that matches the MIME boundary BNF defined in RFC 2046, section 5.1.1</span></span>

    ```
    boundary := 0*69<bchars> bcharsnospace
    bchars := bcharsnospace / " "
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+"
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"
    ```

     <span data-ttu-id="d17ec-357">Przykłady:</span><span class="sxs-lookup"><span data-stu-id="d17ec-357">Examples:</span></span>

     <span data-ttu-id="d17ec-358">NIEPOPRAWNE</span><span class="sxs-lookup"><span data-stu-id="d17ec-358">CORRECT</span></span>

    ```http
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"
    ```

     <span data-ttu-id="d17ec-359">NIEPOPRAWNE</span><span class="sxs-lookup"><span data-stu-id="d17ec-359">CORRECT</span></span>

    ```http
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
    ```

     <span data-ttu-id="d17ec-360">PRAWIDŁOWY</span><span class="sxs-lookup"><span data-stu-id="d17ec-360">INCORRECT</span></span>

    ```http
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
    ```

#### <a name="infoset-mime-part"></a><span data-ttu-id="d17ec-361">Sprawdzonych — składnik MIME</span><span class="sxs-lookup"><span data-stu-id="d17ec-361">Infoset MIME Part</span></span>
<span data-ttu-id="d17ec-362">Koperta protokołu SOAP 1. x jest hermetyzowana jako część główna pakietu XOP MIME i jest często nazywana `infoset` częścią.</span><span class="sxs-lookup"><span data-stu-id="d17ec-362">The SOAP 1.x Envelope is encapsulated as a root part of the XOP MIME package and is often called the `infoset` part.</span></span>

- <span data-ttu-id="d17ec-363">R4141: Koperta protokołu SOAP 1. x musi być hermetyzowana jako część główna pakietu XOP MIME, nazywana `infoset` częścią i przywoływaną przez typ zawartości http.</span><span class="sxs-lookup"><span data-stu-id="d17ec-363">R4141: The SOAP 1.x Envelope must be encapsulated as a root part of the XOP MIME package, called the `infoset` part and referenced from the HTTP Content-Type.</span></span>

- <span data-ttu-id="d17ec-364">R4142: część protokołu SOAP `Infoset` musi zawierać następujące nagłówki MIME: `Content-ID` , `Content-Transfer-Encoding` , i `Content-Type` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-364">R4142: The SOAP `Infoset` part must include the following MIME headers: `Content-ID`, `Content-Transfer-Encoding`, and `Content-Type`.</span></span>

<span data-ttu-id="d17ec-365">Format nagłówka Content-ID jest definiowany przez RFC 2045 jako</span><span class="sxs-lookup"><span data-stu-id="d17ec-365">The format of the Content-ID header is defined by RFC 2045 as</span></span>

```
"Content-ID" ":" msg-id
```

<span data-ttu-id="d17ec-366">gdzie `msg-id` jest zdefiniowana w dokumencie rfc 2822 (zastępuje dokument rfc 822, do którego odwołuje się dokument rfc 2045) jako:</span><span class="sxs-lookup"><span data-stu-id="d17ec-366">where `msg-id` is defined in RFC 2822 (that supersedes RFC 822, referenced in RFC 2045) as:</span></span>

```
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]
```

<span data-ttu-id="d17ec-367">i efektywnie jest adresem e-mail ujętym w " \<" and  "> ".</span><span class="sxs-lookup"><span data-stu-id="d17ec-367">and is effectively an email address enclosed within "\<" and  ">".</span></span> <span data-ttu-id="d17ec-368">`[CFWS]`Prefiks i sufiks zostały dodane w dokumencie RFC 2822 do przenoszenia komentarzy i nie powinny być używane w celu zachowania współdziałania.</span><span class="sxs-lookup"><span data-stu-id="d17ec-368">The `[CFWS]` prefix and suffix were added in RFC 2822 to carry comments and should not be used to preserve interoperability.</span></span>

<span data-ttu-id="d17ec-369">R4143: wartość nagłówka Content-ID dla części MIME sprawdzonych musi być zgodna `msg-id` z produkcją RFC 2822 z `[CFWS]` pominiętymi częściami prefiksu i sufiksów.</span><span class="sxs-lookup"><span data-stu-id="d17ec-369">R4143: The value of the Content-ID header for the Infoset MIME part must follow `msg-id` production from RFC 2822 with the `[CFWS]` prefix and suffix parts omitted.</span></span>

<span data-ttu-id="d17ec-370">Wiele implementacji MIME spełnia wymagania dotyczące wartości ujętej w nawiasy " \<" and "> " jako adresu e-mail, a nie `absoluteURI` \<" , "> adresu e-mail.</span><span class="sxs-lookup"><span data-stu-id="d17ec-370">A number of MIME implementations relaxed requirements for the value enclosed within "\<" and ">" to be an email address and used `absoluteURI` enclosed in "\<" , ">" in addition to the email address.</span></span> <span data-ttu-id="d17ec-371">Ta wersja programu WCF używa wartości nagłówka MIME Content-ID formularza:</span><span class="sxs-lookup"><span data-stu-id="d17ec-371">This version of WCF uses values of the Content-ID MIME header of the form:</span></span>

```
Content-ID: <http://tempuri.org/0>
```

<span data-ttu-id="d17ec-372">R4144: procesor MTOM powinien akceptować wartości nagłówka Content-ID, które pasują do poniższego swobodnego `msg-id` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-372">R4144: MTOM processors should accept Content-ID header values that match the following relaxed `msg-id`.</span></span>

```
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]
mail-address   =     id-left "@" id-right
```

<span data-ttu-id="d17ec-373">MIME (RFC 2045) zawiera nagłówek Content-Transfer-Encoding do przekazywania kodowania zawartości części MIME.</span><span class="sxs-lookup"><span data-stu-id="d17ec-373">MIME (RFC 2045) provides the Content-Transfer-Encoding header to communicate encoding of the content of the MIME part.</span></span> <span data-ttu-id="d17ec-374">Domyślnie zdefiniowane dla kodowania Content-Transfer-Encoding to 7-bitowe, które nie jest odpowiednie dla większości komunikatów protokołu SOAP, więc nagłówek Content-Transfer-Encoding jest wymagany w celu uzyskania większej współdziałania:</span><span class="sxs-lookup"><span data-stu-id="d17ec-374">The default defined for Content-Transfer-Encoding is 7-bit, which is not suitable for most SOAP messages, so the Content-Transfer-Encoding header is needed for greater interoperability:</span></span>

- <span data-ttu-id="d17ec-375">R4145: część sprawdzonych protokołu SOAP musi zawierać nagłówek Content-Transfer-Encoding.</span><span class="sxs-lookup"><span data-stu-id="d17ec-375">R4145: The SOAP Infoset part must contain the Content-Transfer-Encoding header.</span></span>

- <span data-ttu-id="d17ec-376">R4146: Jeśli kodowanie znaków koperty protokołu SOAP to UTF-8, wartość nagłówka Content-Transfer-Encoding musi być 8-bitowa.</span><span class="sxs-lookup"><span data-stu-id="d17ec-376">R4146: If the SOAP Envelope character encoding is UTF-8, the value of the Content-Transfer-Encoding header must be 8-bit.</span></span>

- <span data-ttu-id="d17ec-377">R4147: Jeśli kodowanie znaków koperty protokołu SOAP to UTF-16, wartość nagłówka Content-Transfer-Encoding musi być binarna.</span><span class="sxs-lookup"><span data-stu-id="d17ec-377">R4147: If the SOAP Envelope character encoding is UTF-16, the value of the Content-Transfer-Encoding header must be binary.</span></span>

- <span data-ttu-id="d17ec-378">Zgodnie z sekcją [XOP] 5,</span><span class="sxs-lookup"><span data-stu-id="d17ec-378">According to [XOP] section 5,</span></span>

- <span data-ttu-id="d17ec-379">R4148: część sprawdzonych protokołu SOAP 1.1 musi zawierać nagłówek Content-Type z typem nośnika Application/XOP + XML i Parameters Type = "text/xml" i charset</span><span class="sxs-lookup"><span data-stu-id="d17ec-379">R4148: SOAP1.1 Infoset part must contain Content-Type header with media type application/xop+xml and parameters type="text/xml" and charset</span></span>

    ```http
    Content-Type: application/xop+xml;
                  charset=utf-8;type="text/xml"
    ```

- <span data-ttu-id="d17ec-380">R4149: część sprawdzonych protokołu SOAP 1,2 musi zawierać nagłówek Content-Type z typem nośnika `application/xop+xml` i parametrami Type = " `application/soap+xml` " i `charset` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-380">R4149: The SOAP 1.2 Infoset part must contain the Content-Type header with media type `application/xop+xml` and parameters type="`application/soap+xml`" and `charset`.</span></span>

    ```http
    Content-Type: application/xop+xml;
                  charset=utf-8;type="application/soap+xml"
    ```

     <span data-ttu-id="d17ec-381">Chociaż XOP definiuje `charset` parametr jako `application/xop+xml` opcjonalny, jest wymagany do współdziałania podobnej do wymagania 1,1 BP dla `charset` `text/xml` typu nośnika.</span><span class="sxs-lookup"><span data-stu-id="d17ec-381">While XOP defines the `charset` parameter for `application/xop+xml` to be optional, it is needed for interoperability similar to the BP 1.1 requirement on the `charset` parameter for the `text/xml` media type.</span></span>

- <span data-ttu-id="d17ec-382">R41410: `type` Parametry i `charset` muszą być obecne w nagłówku Content-Type składnika SOAP 1. x sprawdzonych.</span><span class="sxs-lookup"><span data-stu-id="d17ec-382">R41410: The `type` and `charset` parameters must be present on the Content-Type header of the SOAP 1.x Infoset part.</span></span>

#### <a name="wcf-endpoint-support-for-mtom"></a><span data-ttu-id="d17ec-383">Obsługa punktów końcowych WCF dla mechanizmu MTOM</span><span class="sxs-lookup"><span data-stu-id="d17ec-383">WCF Endpoint Support for MTOM</span></span>
<span data-ttu-id="d17ec-384">Celem MTOM jest zakodowanie komunikatu protokołu SOAP w celu zoptymalizowania danych zakodowanych algorytmem Base64.</span><span class="sxs-lookup"><span data-stu-id="d17ec-384">The purpose of MTOM is to encode a SOAP message to optimize base64-encoded data.</span></span> <span data-ttu-id="d17ec-385">Poniżej znajduje się lista ograniczeń:</span><span class="sxs-lookup"><span data-stu-id="d17ec-385">The following is a list of constraints:</span></span>

- <span data-ttu-id="d17ec-386">R4151: każdy element informacji o elemencie, który zawiera dane zakodowane w formacie Base64, może być zoptymalizowany.</span><span class="sxs-lookup"><span data-stu-id="d17ec-386">R4151: Any element information item that contains base64-encoded data may be optimized.</span></span>

- <span data-ttu-id="d17ec-387">B4152: Funkcja WCF optymalizuje elementy informacji o elementach, które zawierają dane zakodowane w formacie base64 i przekracza 1024 bajtów.</span><span class="sxs-lookup"><span data-stu-id="d17ec-387">B4152: WCF optimizes element information items that contain base64-encoded data and exceed 1024 bytes in length.</span></span>

<span data-ttu-id="d17ec-388">Punkt końcowy programu WCF skonfigurowany do korzystania z mechanizmu MTOM zawsze będzie wysyłać komunikaty kodowane przez MTOM.</span><span class="sxs-lookup"><span data-stu-id="d17ec-388">A WCF endpoint configured to use MTOM will always send MTOM-encoded messages.</span></span> <span data-ttu-id="d17ec-389">Nawet jeśli żadna część nie spełnia wymaganych kryteriów, komunikat jest nadal zakodowany za pomocą mechanizmu MTOM (Serializacja jako pakiet MIME z pojedynczą częścią MIME zawierającą kopertę protokołu SOAP).</span><span class="sxs-lookup"><span data-stu-id="d17ec-389">Even if no parts meet the required criteria, the message is still MTOM-encoded (serialized as a MIME package with a single MIME part containing the SOAP envelope).</span></span>

### <a name="ws-policy-assertion-for-mtom"></a><span data-ttu-id="d17ec-390">Potwierdzenie usługi WS-Policy dla mechanizmu MTOM</span><span class="sxs-lookup"><span data-stu-id="d17ec-390">WS-Policy Assertion for MTOM</span></span>
<span data-ttu-id="d17ec-391">W celu wskazania użycia usługi MTOM przez punkt końcowy w programie WCF jest stosowane następujące potwierdzenie zasad:</span><span class="sxs-lookup"><span data-stu-id="d17ec-391">WCF uses the following policy assertion to indicate MTOM usage by endpoint:</span></span>

```xml
<wsoma:OptimizedMimeSerialization />
```

- <span data-ttu-id="d17ec-392">R4211: powyższe potwierdzenie zasad ma podmiot zasad punktu końcowego i określa, że wszystkie komunikaty wysyłane do i odbierane z punktu końcowego muszą być zoptymalizowane przy użyciu mechanizmu MTOM.</span><span class="sxs-lookup"><span data-stu-id="d17ec-392">R4211: The preceding policy assertion has an Endpoint Policy Subject and specifies that all messages sent to and received from the endpoint must be optimized using MTOM.</span></span>

- <span data-ttu-id="d17ec-393">B4212: Jeśli skonfigurowano używanie optymalizacji MTOM, punkt końcowy programu WCF dodaje potwierdzenie zasad MTOM do zasad dołączonych do odpowiednich `wsdl:binding` .</span><span class="sxs-lookup"><span data-stu-id="d17ec-393">B4212: When configured to use MTOM optimization, an WCF endpoint adds an MTOM Policy assertion to the policy attached to the corresponding `wsdl:binding`.</span></span>

### <a name="composition-with-ws-security"></a><span data-ttu-id="d17ec-394">Tworzenie kompozycji przy użyciu protokołu WS-Security</span><span class="sxs-lookup"><span data-stu-id="d17ec-394">Composition with WS-Security</span></span>
<span data-ttu-id="d17ec-395">MTOM jest mechanizmem kodowania podobnym do `text/xml` kodu XML danych binarnych WCF.</span><span class="sxs-lookup"><span data-stu-id="d17ec-395">MTOM is an encoding mechanism that is similar to `text/xml` and WCF Binary XML.</span></span> <span data-ttu-id="d17ec-396">MTOM oferuje naturalną kompozycję przy użyciu protokołu WS-Security i innych protokołów WS-\*: komunikat zabezpieczony przy użyciu protokołu WS-Security można zoptymalizować za pomocą mechanizmu MTOM.</span><span class="sxs-lookup"><span data-stu-id="d17ec-396">MTOM offers natural composition with WS-Security and other WS-\* protocols: a message secured using WS-Security can be optimized using MTOM.</span></span>

### <a name="examples"></a><span data-ttu-id="d17ec-397">Przykłady</span><span class="sxs-lookup"><span data-stu-id="d17ec-397">Examples</span></span>

#### <a name="wcf-soap-11-message-encoded-using-mtom"></a><span data-ttu-id="d17ec-398">Komunikat protokołu SOAP 1,1 WCF zakodowany przy użyciu mechanizmu MTOM</span><span class="sxs-lookup"><span data-stu-id="d17ec-398">WCF SOAP 1.1 Message Encoded Using MTOM</span></span>

```http
POST http://131.107.72.15/Mtom/svc/service.svc/Soap11MtomUTF8 HTTP/1.1
SOAPAction: "http://xmlsoap.org/echoBinaryAsString"
Content-Type: multipart/related;type="application/xop+xml";
              start="<http://tempuri.org/0>";start-info="text/xml";
       boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"
Host: 131.107.72.15
Content-Length: 1501
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="text/xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Body>
    <EchoBinaryAsString xmlns="http://xmlsoap.org/Ping">
      <array>
        <xop:Include
         href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206521093670"
         xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </array>
    </EchoBinaryAsString>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
Content-ID: <http://tempuri.org/1/632618206521093670>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
…Binary Content..
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1
```

#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a><span data-ttu-id="d17ec-399">Bezpieczny komunikat protokołu SOAP 1,2 WCF zakodowany przy użyciu mechanizmu MTOM</span><span class="sxs-lookup"><span data-stu-id="d17ec-399">WCF Secure SOAP 1.2 Message Encoded Using MTOM</span></span>
<span data-ttu-id="d17ec-400">W tym przykładzie komunikat jest szyfrowany przy użyciu mechanizmu MTOM i protokołu SOAP 1,2, który jest chroniony przy użyciu protokołu WS-Security.</span><span class="sxs-lookup"><span data-stu-id="d17ec-400">In this example, a message is encoded using MTOM and SOAP 1.2 that is protected using WS-Security.</span></span> <span data-ttu-id="d17ec-401">Części binarne identyfikowane na potrzeby kodowania to zawartość `BinarySecurityToken` , `CipherValue` `EncryptedData` odpowiadająca zaszyfrowanemu podpisowi i treści zaszyfrowanej.</span><span class="sxs-lookup"><span data-stu-id="d17ec-401">The binary parts identified for encoding are the contents of the `BinarySecurityToken`, `CipherValue` of the `EncryptedData` corresponding to the encrypted signature and encrypted body.</span></span> <span data-ttu-id="d17ec-402">Należy zauważyć, że program `CipherValue` `EncryptedKey` nie został zidentyfikowany do optymalizacji przez WCF, ponieważ jego długość jest mniejsza niż 1024 bajtów.</span><span class="sxs-lookup"><span data-stu-id="d17ec-402">Note that the `CipherValue` of the `EncryptedKey` was not identified for optimization by WCF, because its length is less then 1024 bytes.</span></span>

```http
POST http://131.107.72.15/Mtom/service.svc/Soap12MtomSecureSignEncrypt HTTP/1.1
Content-Type: multipart/related; type="application/xop+xml";
              start="<http://tempuri.org/0>";
            boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3";
              start-info="application/soap+xml";
              action="http://xmlsoap.org/echoBinaryAsString"
Host: 131.107.72.15
Content-Length: 1941
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/0>
Content-Transfer-Encoding: 8bit
Content-Type: application/xop+xml;charset=utf-8;type="application/soap+xml"
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/" xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">
  <s:Header>
    <o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
      <u:Timestamp u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-5">
        <u:Created>2005-09-09T06:57:32.488Z</u:Created>
        <u:Expires>2005-09-09T07:02:32.488Z</u:Expires>
      </u:Timestamp>
      <o:BinarySecurityToken u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-2" ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3" EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">
        <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
      </o:BinarySecurityToken>
      <e:EncryptedKey Id="_1" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#rsa-oaep-mgf1p"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:KeyIdentifier ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509SubjectKeyIdentifier">Xeg55vRyK3ZhAEhEf+YT0z986L0=</o:KeyIdentifier>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>          <e:CipherValue>oQfpxwT8/SAGyZQzKE2b4yO6dXuQj7pwJ+5CGL3Rf7C06bQ5ttMoQ9GLJcQYkXTzin+WwHEgs5bj5ml9HKTW9QAU5JJ6lksdymmQvWP5ZtGPBVchO4sofEGoCKmBiZL/DYS/cnbzgnc/3a6NYnc10y2fWGaGLiqa00zijAw7o0Y=</e:CipherValue>
        </e:CipherData>
      </e:EncryptedKey>
      <c:DerivedKeyToken u:Id="_2" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc">
        <o:SecurityTokenReference>
          <o:Reference URI="#_1"/>
        </o:SecurityTokenReference>
        <c:Nonce>OrEPRX7fISIS4sXYWPMv3g==</c:Nonce>
      </c:DerivedKeyToken>
      <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:DataReference URI="#_3"/>
        <e:DataReference URI="#_4"/>
      </e:ReferenceList>
      <e:EncryptedData Id="_4" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
          <o:SecurityTokenReference>
            <o:Reference URI="#_2"/>
          </o:SecurityTokenReference>
        </KeyInfo>
        <e:CipherData>
          <e:CipherValue>
            <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F2%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
          </e:CipherValue>
        </e:CipherData>
      </e:EncryptedData>
    </o:Security>
  </s:Header>
  <s:Body u:Id="_0">
    <e:EncryptedData Id="_3" Type="http://www.w3.org/2001/04/xmlenc#Content" xmlns:e="http://www.w3.org/2001/04/xmlenc#">
      <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>
      <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">
        <o:SecurityTokenReference xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
          <o:Reference URI="#_2"/>
        </o:SecurityTokenReference>
      </KeyInfo>
      <e:CipherData>
        <e:CipherValue>
          <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F3%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>
        </e:CipherValue>
      </e:CipherData>
    </e:EncryptedData>
  </s:Body>
</s:Envelope>
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/1/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary content of BinarySecurityToken - X509 Certificate...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/2/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted primary signature...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3
Content-ID: <http://tempuri.org/3/632618206525089430>
Content-Transfer-Encoding: binary
Content-Type: application/octet-stream
...Binary serialization of the encrypted Body...
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3--
```
