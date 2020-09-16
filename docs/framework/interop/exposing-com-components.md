---
title: Udostępnianie składników COM programowi.NET Framework
description: Poznaj proces udostępniania składników COM na platformie .NET. Składniki COM są cenne w kodzie zarządzanym jako aplikacje biznesowe warstwy środkowej lub izolowane.
ms.date: 03/30/2017
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
ms.openlocfilehash: 34dda58d9513874169927164706fafdd95e8ed84
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554185"
---
# <a name="exposing-com-components-to-the-net-framework"></a>Udostępnianie składników COM programowi.NET Framework
Ta sekcja podsumowuje proces, który jest wymagany, aby uwidocznić istniejący składnik COM w kodzie zarządzanym. Aby uzyskać szczegółowe informacje na temat pisania serwerów COM, które ścisłie integrują się z .NET Framework, zobacz [zagadnienia dotyczące projektowania współdziałania](/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100)).
  
 Istniejące składniki modelu COM są cennymi zasobami w kodzie zarządzanym jako aplikacje biznesowe warstwy środkowej lub jako izolowane funkcje. Idealny składnik ma podstawowy zestaw międzyoperacyjny i jest zgodny ze standardami programistycznymi nałożonymi przez model COM.  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a>Aby uwidocznić składniki COM .NET Framework  
  
1. [Zaimportuj bibliotekę typów jako zestaw](importing-a-type-library-as-an-assembly.md).  
  
     Środowisko uruchomieniowe języka wspólnego wymaga metadanych dla wszystkich typów, w tym typów COM. Istnieje kilka sposobów uzyskania zestawu zawierającego typy COM zaimportowane jako metadane.  
  
2. [Używaj typów com w kodzie zarządzanym](/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).  
  
     Można sprawdzić typy COM, uaktywnić wystąpienia i wywołać metody obiektu COM w taki sam sposób, jak w przypadku dowolnego typu zarządzanego.  
  
3. [Kompiluj projekt międzyoperacyjności](compiling-an-interop-project.md).  
  
     Windows SDK zapewnia kompilatory dla kilku języków zgodnych z Common Language Specification (CLS), w tym Visual Basic, C# i C++.  
  
4. [Wdróż aplikację międzyoperacyjną](deploying-an-interop-application.md).  
  
     Aplikacje międzyoperacyjności najlepiej wdrożyć jako podpisane zestawy [o silnych nazwach](../../standard/assembly/strong-named.md)w globalnej pamięci podręcznej zestawów.  
  
## <a name="see-also"></a>Zobacz także

- [Współdziałanie z kodem niezarządzanym](index.md)
- [Zagadnienia dotyczące projektowania operacji międzyoperacyjnych](/previous-versions/dotnet/netframework-4.0/61aax4kh(v=vs.100))
- [Przykład międzyoperacyjnego modelu COM: klient modelu COM i serwer COM](com-interop-sample-net-client-and-com-server.md)
- [Niezależność od języka i składniki niezależne od języka](../../standard/language-independence-and-language-independent-components.md)
- [Gacutil.exe (Global Assembly Cache Tool)](../tools/gacutil-exe-gac-tool.md)
