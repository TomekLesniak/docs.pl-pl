---
title: Debugowanie statycznych funkcji globalnych
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework debugging]
- debugging global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], debugging
ms.assetid: efc64414-77c3-48d0-881a-8594ed416aad
ms.openlocfilehash: 04906322e311b580abddeca7744cf3e75d471e05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722989"
---
# <a name="debugging-global-static-functions"></a>Debugowanie statycznych funkcji globalnych

W tej sekcji opisano niezarządzane globalne funkcje statyczne używane przez interfejs API debugowania.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [_EFN_GetManagedExcepStack — Funkcja](efn-getmanagedexcepstack-function.md)  
 Dany adres obiektu wyjątku zarządzanego zwraca wersję ciągu śledzenia stosu zawartych wewnątrz.  
  
 [_EFN_GetManagedObjectFieldInfo — Funkcja](efn-getmanagedobjectfieldinfo-function.md)  
 Pobiera przesunięcie od początku obiektu do pola i wartości pola przy użyciu podanego wskaźnika obiektu i nazwy pola.  
  
 [_EFN_GetManagedObjectName — Funkcja](efn-getmanagedobjectname-function.md)  
 Pobiera nazwę typu za pomocą podanego wskaźnika obiektu zarządzanego.  
  
 [_EFN_StackTrace — Funkcja](efn-stacktrace-function.md)  
 Przedstawia tekstową reprezentację zarządzanego śledzenia stosu i tablicę `CONTEXT` rekordów, jeden dla każdego przejścia między niezarządzanym i zarządzanym kodem.  
  
 [CLRDataCreateInstance — Funkcja](clrdatacreateinstance-function.md)  
 Wywoływane przez usługi dostępu do danych środowiska uruchomieniowego języka wspólnego (CLR) w celu utworzenia określonego obiektu interfejsu dla określonego procesu docelowego.  
  
 [PFN_CLRDataCreateInstance — Wskaźnik funkcji](pfn-clrdatacreateinstance-function-pointer.md)  
 Wskazuje funkcję, która jest wywoływana przez usługi dostępu do danych CLR w celu utworzenia określonego obiektu interfejsu dla określonego procesu docelowego.  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Klasy coclass debugowania](debugging-coclasses.md)  
  
 [Debugowanie — Interfejsy](debugging-interfaces.md)  
  
 [Debugowanie — wyliczenia](debugging-enumerations.md)  
  
 [Struktury debugowania](debugging-structures.md)
