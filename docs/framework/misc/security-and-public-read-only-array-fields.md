---
title: Bezpieczeństwo i publiczne pola tablicy tylko do odczytu
description: Przeczytaj, dlaczego należy unikać używania publicznych pól tablicy tylko do odczytu, aby zdefiniować zachowanie granicy lub bezpieczeństwo aplikacji.
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
ms.openlocfilehash: 5e499f8052306cd1ad063c9f44a2a0f1d0b365ef
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855741"
---
# <a name="security-and-public-read-only-array-fields"></a>Bezpieczeństwo i publiczne pola tablicy tylko do odczytu

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

Nie używaj pól tablicy publicznej tylko do odczytu z bibliotek zarządzanych, aby zdefiniować zachowanie granic lub zabezpieczenia aplikacji, ponieważ można modyfikować pola tablicy publicznej tylko do odczytu.  
  
## <a name="remarks"></a>Uwagi  

Niektóre klasy .NET zawierają pola publiczne tylko do odczytu, które zawierają parametry graniczne specyficzne dla platformy. Na przykład <xref:System.IO.Path.InvalidPathChars> pole jest tablicą opisującą znaki, które nie są dozwolone w ciągu ścieżki do pliku. W środowisku .NET są obecne wiele podobnych pól.  
  
 Wartości publicznych pól tylko do odczytu, takich jak <xref:System.IO.Path.InvalidPathChars> mogą być modyfikowane przez kod lub kod, który współużytkują domenę aplikacji kodu.  Nie należy używać pól tablic publicznych tylko do odczytu, takich jak to, aby zdefiniować zachowanie granic aplikacji.  Jeśli to zrobisz, złośliwy kod może zmienić definicje granic i użyć kodu w nieoczekiwany sposób.  
  
 W wersji 2,0 i nowszych .NET Framework należy używać metod, które zwracają nową tablicę zamiast używać publicznych pól tablic.  Na przykład zamiast używać <xref:System.IO.Path.InvalidPathChars> pola, należy użyć <xref:System.IO.Path.GetInvalidPathChars%2A> metody.  
  
 Należy zauważyć, że typy .NET Framework nie używają publicznych pól do wewnętrznego definiowania typów granic.  Zamiast tego .NET Framework używa oddzielnych pól prywatnych.  Zmiana wartości tych pól publicznych nie powoduje zmiany zachowania typów .NET Framework.  
  
## <a name="see-also"></a>Zobacz także

- [Wytyczne dotyczące bezpiecznego programowania](../../standard/security/secure-coding-guidelines.md)
