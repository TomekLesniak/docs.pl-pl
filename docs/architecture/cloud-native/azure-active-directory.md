---
title: Azure Active Directory
description: Tworzenie architektury natywnych aplikacji .NET w chmurze dla platformy Azure | Azure Active Directory
ms.date: 06/30/2019
ms.openlocfilehash: 207043507a9052c47683383a98cef6417a1a2740
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "71183694"
---
# <a name="azure-active-directory"></a><span data-ttu-id="d1480-103">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d1480-103">Azure Active Directory</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="d1480-104">Usługa Microsoft Azure Active Directory (Azure AD) oferuje funkcje zarządzania tożsamościami i dostępem jako usługi.</span><span class="sxs-lookup"><span data-stu-id="d1480-104">Microsoft Azure Active Directory (Azure AD) offers identity and access management as a service.</span></span> <span data-ttu-id="d1480-105">Klienci używają IT, aby konfigurować i obsługiwać użytkowników, jakie informacje są przechowywane na ich temat, kto może uzyskać dostęp do tych informacji, kto może je zarządzać i jakie aplikacje mają do nich dostęp.</span><span class="sxs-lookup"><span data-stu-id="d1480-105">Customers use it to configure and maintain who users are, what information to store about them, who can access that information, who can manage it, and what apps can access it.</span></span> <span data-ttu-id="d1480-106">Usługa AAD może uwierzytelniać użytkowników aplikacji skonfigurowanych do korzystania z niej przy użyciu logowania jednokrotnego (SSO).</span><span class="sxs-lookup"><span data-stu-id="d1480-106">AAD can authenticate users for applications configured to use it, providing a single sign-on (SSO) experience.</span></span> <span data-ttu-id="d1480-107">Może być używana samodzielnie lub zintegrowana z usługą Windows AD działającą lokalnie.</span><span class="sxs-lookup"><span data-stu-id="d1480-107">It can be used on its own or be integrated with Windows AD running on premises.</span></span>

<span data-ttu-id="d1480-108">Usługa Azure AD została skompilowana dla chmury.</span><span class="sxs-lookup"><span data-stu-id="d1480-108">Azure AD is built for the cloud.</span></span> <span data-ttu-id="d1480-109">Jest to natywne rozwiązanie do obsługi tożsamości w chmurze, które używa interfejs API programu Graph opartej na protokole REST i składni OData dla zapytań, w przeciwieństwie do usługi Windows AD, która używa protokołu LDAP.</span><span class="sxs-lookup"><span data-stu-id="d1480-109">It's truly a cloud-native identity solution that uses a REST-based Graph API and OData syntax for queries, unlike Windows AD, which uses LDAP.</span></span> <span data-ttu-id="d1480-110">Lokalne Active Directory mogą synchronizować atrybuty użytkownika z chmurą przy użyciu usług synchronizacji tożsamości, co pozwala na przeprowadzanie wszystkich uwierzytelnień w chmurze przy użyciu usługi Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d1480-110">On premises Active Directory can sync user attributes to the cloud using Identity Sync Services, allowing all authentication to take place in the cloud using Azure AD.</span></span> <span data-ttu-id="d1480-111">Alternatywnie uwierzytelnianie można skonfigurować za pośrednictwem połączenia, aby przejść z powrotem do lokalnego Active Directory za pomocą usług ADFS, które mają być wykonywane przez usługi Windows AD lokalnie.</span><span class="sxs-lookup"><span data-stu-id="d1480-111">Alternately, authentication can be configured via Connect to pass back to local Active Directory via ADFS to be completed by Windows AD on premises.</span></span>

<span data-ttu-id="d1480-112">Usługa Azure AD obsługuje firmowe ekrany logowania, uwierzytelnianie wieloskładnikowe i serwery proxy aplikacji opartych na chmurze, które są używane do zapewnienia logowania jednokrotnego dla aplikacji hostowanych lokalnie.</span><span class="sxs-lookup"><span data-stu-id="d1480-112">Azure AD supports company branded sign-in screens, multi-factory authentication, and cloud-based application proxies that are used to provide SSO for applications hosted on premises.</span></span> <span data-ttu-id="d1480-113">Oferuje różne rodzaje funkcji raportowania zabezpieczeń i alertów.</span><span class="sxs-lookup"><span data-stu-id="d1480-113">It offers different kinds of security reporting and alert capabilities.</span></span>

## <a name="references"></a><span data-ttu-id="d1480-114">Odwołania</span><span class="sxs-lookup"><span data-stu-id="d1480-114">References</span></span>

- [<span data-ttu-id="d1480-115">Platforma tożsamości firmy Microsoft</span><span class="sxs-lookup"><span data-stu-id="d1480-115">Microsoft identity platform</span></span>](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
><span data-ttu-id="d1480-116">[Poprzedni](authentication-authorization.md)
>[Następny](identity-server.md)</span><span class="sxs-lookup"><span data-stu-id="d1480-116">[Previous](authentication-authorization.md)
[Next](identity-server.md)</span></span>