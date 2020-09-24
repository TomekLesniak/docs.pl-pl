---
title: Usługa Azure Active Directory
description: Tworzenie architektury natywnych aplikacji .NET w chmurze dla platformy Azure | Azure Active Directory
ms.date: 06/30/2019
ms.openlocfilehash: 55787f3565fc15bb25cf1a101aa5c1e3ddefe5e7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161116"
---
# <a name="azure-active-directory"></a>Usługa Azure Active Directory

Usługa Microsoft Azure Active Directory (Azure AD) oferuje funkcje zarządzania tożsamościami i dostępem jako usługi. Klienci używają IT, aby konfigurować i obsługiwać użytkowników, jakie informacje są przechowywane na ich temat, kto może uzyskać dostęp do tych informacji, kto może je zarządzać i jakie aplikacje mają do nich dostęp. Usługa AAD może uwierzytelniać użytkowników aplikacji skonfigurowanych do korzystania z niej przy użyciu logowania jednokrotnego (SSO). Może być używana samodzielnie lub zintegrowana z usługą Windows AD działającą lokalnie.

Usługa Azure AD została skompilowana dla chmury. Jest to natywne rozwiązanie do obsługi tożsamości w chmurze, które używa interfejs API programu Graph opartej na protokole REST i składni OData dla zapytań, w przeciwieństwie do usługi Windows AD, która używa protokołu LDAP. Lokalne Active Directory mogą synchronizować atrybuty użytkownika z chmurą przy użyciu usług synchronizacji tożsamości, co pozwala na przeprowadzanie wszystkich uwierzytelnień w chmurze przy użyciu usługi Azure AD. Alternatywnie uwierzytelnianie można skonfigurować za pośrednictwem połączenia, aby przejść z powrotem do lokalnego Active Directory za pomocą usług ADFS, które mają być wykonywane przez usługi Windows AD lokalnie.

Usługa Azure AD obsługuje firmowe ekrany logowania, uwierzytelnianie wieloskładnikowe i serwery proxy aplikacji opartych na chmurze, które są używane do zapewnienia logowania jednokrotnego dla aplikacji hostowanych lokalnie. Oferuje różne rodzaje funkcji raportowania zabezpieczeń i alertów.

## <a name="references"></a>Odwołania

- [Platforma tożsamości firmy Microsoft](/azure/active-directory/develop/)

>[!div class="step-by-step"]
>[Poprzedni](authentication-authorization.md) 
> [Dalej](identity-server.md)
