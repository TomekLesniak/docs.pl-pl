---
title: Śledzenie sieci w .NET Framework
description: Dowiedz się więcej na temat śledzenia sieci w .NET Framework, który zawiera informacje o wywołaniach metod i ruchu sieciowym dla aplikacji zarządzanej.
ms.date: 03/30/2017
helpviewer_keywords:
- debugging [.NET Framework], network tracing
- methods, network tracing
- Networking
- trace enabled debugging
- network tracing, about network tracing
- network tracing
- network, network tracing
- traffic tracing
- tracing [.NET Framework], network
- deploying applications [.NET Framework], network traffic
- capturing network traffic
- Internet, network tracing
- Network Resources
- output, network tracing
- method invocations
ms.assetid: e993b7c3-087f-45d8-9c02-9dded936d804
ms.openlocfilehash: c3c710d99c9597120b0c4d9674439a27c3bedfcc
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96261686"
---
# <a name="network-tracing-in-the-net-framework"></a>Śledzenie sieci w .NET Framework

Mechanizm śledzenia sieci w środowisku .NET Framework umożliwia dostęp do informacji o wywołaniach metod i ruchu sieciowym generowanym przez zarządzaną aplikację. Funkcja ułatwia debugowanie aplikacji na etapie ich tworzenia oraz analizowanie już wdrożonych aplikacji. Dane wyjściowe funkcji śledzenia sieci można adaptować, dostosowując je do różnych scenariuszy fazy programowania i środowiska produkcyjnego.  
  
 Aby włączyć śledzenie sieci w środowisku .NET Framework, należy wskazać miejsce docelowe danych wyjściowych funkcji oraz dodać jej ustawienia konfiguracyjne do pliku konfiguracyjnego aplikacji lub maszyny. Opisy plików konfiguracji i sposobu ich użycia można znaleźć w temacie [pliki konfiguracji](../configure-apps/index.md). Informacje o sposobie włączania funkcji śledzenia sieci znajdują się w temacie [Włączanie śledzenia sieci](enabling-network-tracing.md). Aby uzyskać informacje o ustawieniach, które należy dodać do pliku konfiguracji, zobacz [How to: Configure Network Tracing](how-to-configure-network-tracing.md).  
  
 Po włączeniu śledzenia można przechwytywać informacje o śledzeniu, które są wyprowadzane przez klasy **System.NET** . Do składowych klasy sieciowej generujących dane ze śledzenia obowiązuje następująca uwaga zawarta w sekcji Uwaga w dokumentacji biblioteki klas środowiska NET Framework:  
  
> [!NOTE]
> Ten element członkowski generuje informacje ze śledzenia pod warunkiem włączenia funkcji śledzenia sieci w aplikacji. Aby dowiedzieć się więcej, zobacz Śledzenie sieci.  
  
## <a name="see-also"></a>Zobacz też

- [Włączanie śledzenia sieci](enabling-network-tracing.md)
- [Instrukcje: konfigurowanie funkcji śledzenia sieci](how-to-configure-network-tracing.md)
- [Interpretowanie śledzenia sieci](interpreting-network-tracing.md)
- [Śledzenie i instrumentowanie aplikacji](../debug-trace-profile/tracing-and-instrumenting-applications.md)
