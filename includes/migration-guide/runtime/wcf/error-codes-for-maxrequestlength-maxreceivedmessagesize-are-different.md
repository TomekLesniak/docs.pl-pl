---
ms.openlocfilehash: 26facb645de175d7ef0432394fc2b84f59e8437d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497500"
---
### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a><span data-ttu-id="3d03f-101">Kody błędów dla 'Maxrequestlength lub maxReceivedMessageSize są różne</span><span class="sxs-lookup"><span data-stu-id="3d03f-101">Error codes for maxRequestLength or maxReceivedMessageSize are different</span></span>

#### <a name="details"></a><span data-ttu-id="3d03f-102">Szczegóły</span><span class="sxs-lookup"><span data-stu-id="3d03f-102">Details</span></span>

<span data-ttu-id="3d03f-103">Komunikaty w usługach sieci Web WCF hostowanych w Internet Information Services (IIS) lub ASP.NET Development Server, które przekraczają 'Maxrequestlength (w ASP.NET) lub maxReceivedMessageSize (w programie WCF), mają różne błędy codeThe kod stanu HTTP został zmieniony z 400 (złe żądanie) na 413 (jednostka żądania jest zbyt duża) i komunikaty, które przekraczają albo wartość parametru 'Maxrequestlength lub maxReceivedMessageSize, zgłaszają <xref:System.ServiceModel.ProtocolException?displayProperty=fullName> wyjątek.</span><span class="sxs-lookup"><span data-stu-id="3d03f-103">Messages in WCF web services hosted in Internet Information Services (IIS) or ASP.NET Development Server that exceed maxRequestLength (in ASP.NET) or maxReceivedMessageSize (in WCF) have different error codeThe HTTP status code has changed from 400 (Bad Request) to 413 (Request Entity Too Large), and messages that exceed either the maxRequestLength or the maxReceivedMessageSize setting throw a <xref:System.ServiceModel.ProtocolException?displayProperty=fullName> exception.</span></span> <span data-ttu-id="3d03f-104">Obejmuje to przypadki, w których tryb transferu jest przesyłany strumieniowo.</span><span class="sxs-lookup"><span data-stu-id="3d03f-104">This includes cases in which the transfer mode is Streamed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3d03f-105">Sugestia</span><span class="sxs-lookup"><span data-stu-id="3d03f-105">Suggestion</span></span>

<span data-ttu-id="3d03f-106">Ta zmiana ułatwia debugowanie w przypadkach, gdy długość komunikatu przekracza limity dozwolone przez ASP.NET lub WCF. Należy zmodyfikować każdy kod, który wykonuje przetwarzanie na podstawie kodu stanu HTTP 400.</span><span class="sxs-lookup"><span data-stu-id="3d03f-106">This change facilitates debugging in cases where the message length exceeds the limits allowed by ASP.NET or WCF.You must modify any code that performs processing based on an HTTP 400 status code.</span></span>

| <span data-ttu-id="3d03f-107">Nazwa</span><span class="sxs-lookup"><span data-stu-id="3d03f-107">Name</span></span>    | <span data-ttu-id="3d03f-108">Wartość</span><span class="sxs-lookup"><span data-stu-id="3d03f-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3d03f-109">Zakres</span><span class="sxs-lookup"><span data-stu-id="3d03f-109">Scope</span></span>   |<span data-ttu-id="3d03f-110">Edge</span><span class="sxs-lookup"><span data-stu-id="3d03f-110">Edge</span></span>|
|<span data-ttu-id="3d03f-111">Wersja</span><span class="sxs-lookup"><span data-stu-id="3d03f-111">Version</span></span>|<span data-ttu-id="3d03f-112">4.5</span><span class="sxs-lookup"><span data-stu-id="3d03f-112">4.5</span></span>|
|<span data-ttu-id="3d03f-113">Typ</span><span class="sxs-lookup"><span data-stu-id="3d03f-113">Type</span></span>|<span data-ttu-id="3d03f-114">Środowisko uruchomieniowe</span><span class="sxs-lookup"><span data-stu-id="3d03f-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="3d03f-115">Dotyczy interfejsów API</span><span class="sxs-lookup"><span data-stu-id="3d03f-115">Affected APIs</span></span>

<span data-ttu-id="3d03f-116">Nie wykrywalne za pośrednictwem analizy interfejsu API.</span><span class="sxs-lookup"><span data-stu-id="3d03f-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
