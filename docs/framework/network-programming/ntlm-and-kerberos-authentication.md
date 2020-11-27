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
# <a name="ntlm-and-kerberos-authentication"></a>Uwierzytelnianie NTLM i uwierzytelnianie Kerberos

Domyślne uwierzytelnianie NTLM i uwierzytelnianie Kerberos używają poświadczeń użytkownika systemu Microsoft Windows NT skojarzonych z aplikacją wywołującą, aby próbować uwierzytelniać się za pomocą serwera. W przypadku korzystania z uwierzytelniania NTLM innego niż domyślne aplikacja ustawia typ uwierzytelniania na NTLM i używa <xref:System.Net.NetworkCredential> obiektu do przekazania nazwy użytkownika, hasła i domeny do hosta, jak pokazano w poniższym przykładzie.  
  
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
  
 Aplikacje, które muszą łączyć się z usługami internetowymi przy użyciu poświadczeń użytkownika aplikacji, mogą to zrobić przy użyciu poświadczeń domyślnych użytkownika, jak pokazano w poniższym przykładzie.  
  
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
  
 Moduł uwierzytelnianie negocjowane określa, czy serwer zdalny używa uwierzytelniania NTLM, czy Kerberos, i wysyła odpowiednią odpowiedź.  
  
> [!NOTE]
> Uwierzytelnianie NTLM nie działa przez serwer proxy.  
  
## <a name="see-also"></a>Zobacz też

- [Uwierzytelnianie podstawowe i szyfrowane](basic-and-digest-authentication.md)
- [Uwierzytelnianie internetowe](internet-authentication.md)
