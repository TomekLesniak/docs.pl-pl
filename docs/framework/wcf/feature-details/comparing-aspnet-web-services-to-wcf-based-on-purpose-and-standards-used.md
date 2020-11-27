---
title: Porównanie usług sieci Web platformy ASP.NET i architektury WCF na podstawie przeznaczenia oraz stosowanych standardów
ms.date: 03/30/2017
ms.assetid: d3890278-fa9b-4902-91ea-8da73b7143cc
ms.openlocfilehash: 62917d7a188d0863f6ebcb7dd3531ef2dd6a5132
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295070"
---
# <a name="comparing-aspnet-web-services-to-wcf-based-on-purpose-and-standards-used"></a>Porównanie usług sieci Web platformy ASP.NET i architektury WCF na podstawie przeznaczenia oraz stosowanych standardów

Usługi sieci Web ASP.NET zostały opracowane do tworzenia aplikacji wysyłających i odbierających komunikaty przy użyciu Simple Object Access Protocol (SOAP) za pośrednictwem protokołu HTTP. Strukturę komunikatów można zdefiniować za pomocą schematu XML, a narzędzie jest udostępniane, aby ułatwić Serializowanie komunikatów do i z obiektów .NET Framework. Technologia może automatycznie generować metadane opisujące usługi sieci Web w Web Services Description Language (WSDL), a drugie narzędzie do generowania klientów dla usług sieci Web z poziomu języka WSDL.  
  
 Usługa WCF służy do włączania .NET Framework aplikacji do wymiany komunikatów z innymi jednostkami oprogramowania. Protokół SOAP jest używany domyślnie, ale komunikaty mogą być w dowolnym formacie i przekazywane przy użyciu dowolnego protokołu transportowego. Strukturę komunikatów można zdefiniować przy użyciu schematu XML, a istnieją różne opcje serializowania komunikatów do i z obiektów .NET Framework. Funkcja WCF może automatycznie generować metadane, aby opisywać Aplikacje skompilowane przy użyciu technologii w języku WSDL, a także udostępnia narzędzie do generowania klientów dla tych aplikacji z poziomu języka WSDL.  
  
 Standardy obsługiwane przez usługi sieci Web ASP.NET są udokumentowane w [zalety usług sieci Web XML utworzonych przy użyciu ASP.NET](/previous-versions/dotnet/netframework-4.0/0859ebft(v=vs.100)). Bardziej obszerna lista standardów obsługiwanych przez program WCF jest wymieniona w obszarze [Protokoły usług sieci Web obsługiwane przez System-Provided powiązania współdziałania](web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
## <a name="see-also"></a>Zobacz też

- [Porównywanie usług sieci Web na platformie ASP.NET z programem WCF na podstawie procesów programistycznych](comparing-aspnet-web-services-to-wcf-based-on-development.md)
