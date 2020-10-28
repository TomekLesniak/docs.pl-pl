---
title: Zestawy i wykonywanie równoczesne
description: Dowiedz się więcej o wykonywaniu równoczesnym, które jest możliwość przechowywania i uruchamiania wielu wersji aplikacji lub składnika na tym samym komputerze.
ms.date: 08/20/2019
helpviewer_keywords:
- side-by-side execution [.NET]
- assemblies [.NET], side-by-side execution
ms.assetid: e42036ee-7590-47d1-b884-cc856e39bd5d
ms.openlocfilehash: 7bedd5a384ceace014412eb894adad5c92c00b05
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687981"
---
# <a name="assemblies-and-side-by-side-execution"></a>Zestawy i wykonywanie równoczesne

Wykonywanie równoczesne to możliwość przechowywania i wykonywania wielu wersji aplikacji lub składnika na tym samym komputerze. Oznacza to, że można korzystać z wielu wersji środowiska uruchomieniowego oraz wielu wersji aplikacji i składników, które używają wersji środowiska uruchomieniowego, na tym samym komputerze w tym samym czasie. Wykonywanie równoczesne daje większą kontrolę nad wersjami składnika, z którym jest powiązana aplikacja, oraz większą kontrolę nad wersją środowiska uruchomieniowego używaną przez aplikację.  
  
Obsługa magazynu Side-by-Side i wykonywania różnych wersji tego samego zestawu jest integralną częścią silnego nazewnictwa i jest wbudowana w infrastrukturę środowiska uruchomieniowego. Ponieważ numer wersji zestawu o silnej nazwie jest częścią swojej tożsamości, środowisko uruchomieniowe może przechowywać wiele wersji tego samego zestawu w globalnej pamięci podręcznej zestawów i ładować te zestawy w czasie wykonywania.  
  
Chociaż środowisko uruchomieniowe zapewnia możliwość tworzenia aplikacji obok siebie, wykonywanie równoczesne nie jest automatyczne. Aby uzyskać więcej informacji na temat tworzenia aplikacji do wykonywania równoczesnego, zobacz [wskazówki dotyczące tworzenia składników do wykonywania równoczesnego](../../framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).  
  
## <a name="see-also"></a>Zobacz także

- [Jak środowisko uruchomieniowe lokalizuje zestawy](../../framework/deployment/how-the-runtime-locates-assemblies.md)
- [Zestawy w środowisku .NET](index.md)
