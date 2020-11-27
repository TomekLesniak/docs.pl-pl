---
title: Uwierzytelnianie NTLM i uwierzytelnianie Kerberos
description: Dowiedz się, jak domyślne uwierzytelnianie NTLM i uwierzytelnianie Kerberos działają dla aplikacji .NET Framework i Poznaj inne niż domyślne uwierzytelnianie NTLM.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [.NET Framework], NTLM
- authentication [.NET Framework], Kerberos
- user authentication, Kerberos
- user authentication, NTLM
- Kerberos authentication
- receiving data, authentication
- NTLM authentication
- Internet, authentication
- client authentication, Kerberos
- sending data, authentication
- network resources, authentication
- classes [.NET Framework], authentication
- client authentication, NTLM
ms.assetid: 9ef65560-f596-4469-bcce-f4d5407b55cd
ms.openlocfilehash: 3fcd39f5414bca9bfcb368f6962ae36891458151
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262830"
---
# <a name="ntlm-and-kerberos-authentication"></a><span data-ttu-id="39409-103">Uwierzytelnianie NTLM i uwierzytelnianie Kerberos</span><span class="sxs-lookup"><span data-stu-id="39409-103">NTLM and Kerberos Authentication</span></span>

<span data-ttu-id="39409-104">Domyślne uwierzytelnianie NTLM i uwierzytelnianie Kerberos używają poświadczeń użytkownika systemu Microsoft Windows NT skojarzonych z aplikacją wywołującą, aby próbować uwierzytelniać się za pomocą serwera.</span><span class="sxs-lookup"><span data-stu-id="39409-104">Default NTLM authentication and Kerberos authentication use the Microsoft Windows NT user credentials associated with the calling application to attempt authentication with the server.</span></span> <span data-ttu-id="39409-105">W przypadku korzystania z uwierzytelniania NTLM innego niż domyślne aplikacja ustawia typ uwierzytelniania na NTLM i używa <xref:System.Net.NetworkCredential> obiektu do przekazania nazwy użytkownika, hasła i domeny do hosta, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="39409-105">When using non-default NTLM authentication, the application sets the authentication type to NTLM and uses a <xref:System.Net.NetworkCredential> object to pass the user name, password, and domain to the host, as shown in the following example.</span></span>  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = _  
    New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials =
    new NetworkCredential(UserName, SecurelyStoredPassword, Domain);  
```  
  
 <span data-ttu-id="39409-106">Aplikacje, które muszą łączyć się z usługami internetowymi przy użyciu poświadczeń użytkownika aplikacji, mogą to zrobić przy użyciu poświadczeń domyślnych użytkownika, jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="39409-106">Applications that need to connect to Internet services using the credentials of the application user can do so with the user's default credentials, as shown in the following example.</span></span>  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = CredentialCache.DefaultCredentials  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials = CredentialCache.DefaultCredentials;  
```  
  
 <span data-ttu-id="39409-107">Moduł uwierzytelnianie negocjowane określa, czy serwer zdalny używa uwierzytelniania NTLM, czy Kerberos, i wysyła odpowiednią odpowiedź.</span><span class="sxs-lookup"><span data-stu-id="39409-107">The negotiate authentication module determines whether the remote server is using NTLM or Kerberos authentication, and sends the appropriate response.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="39409-108">Uwierzytelnianie NTLM nie działa przez serwer proxy.</span><span class="sxs-lookup"><span data-stu-id="39409-108">NTLM authentication does not work through a proxy server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39409-109">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="39409-109">See also</span></span>

- [<span data-ttu-id="39409-110">Uwierzytelnianie podstawowe i szyfrowane</span><span class="sxs-lookup"><span data-stu-id="39409-110">Basic and Digest Authentication</span></span>](basic-and-digest-authentication.md)
- [<span data-ttu-id="39409-111">Uwierzytelnianie internetowe</span><span class="sxs-lookup"><span data-stu-id="39409-111">Internet Authentication</span></span>](internet-authentication.md)
