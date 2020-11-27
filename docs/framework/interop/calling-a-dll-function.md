---
title: Wywołanie funkcji DLL
description: Przejrzyj problemy dotyczące wywoływania funkcji DLL, która może wydawać się myląca. Proces wywoływania funkcji różni się w zależności od tego, czy typem zwracanym jest danych kopiowalnych.
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
ms.openlocfilehash: 09dd9d30c29660231feee6c624a025ade1fda1d3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96282954"
---
# <a name="calling-a-dll-function"></a>Wywołanie funkcji DLL

Chociaż wywoływanie niezarządzanych funkcji DLL jest niemal identyczne z wywoływaniem innego kodu zarządzanego, istnieją różnice, które mogą sprawiać, że funkcje DLL pozornie pomyleją się w pierwszej kolejności. W tej sekcji przedstawiono tematy opisujące niektóre nietypowe problemy związane z wywoływaniem.  
  
 Struktury zwracane przez wywołania wywołania platformy muszą być typami danych, które mają taką samą reprezentację w kodzie zarządzanym i niezarządzanym. Typy takie są nazywane *danych kopiowalnych* , ponieważ nie wymagają konwersji (zobacz [typy danych kopiowalnych i danych kopiowalnych](blittable-and-non-blittable-types.md)). Aby wywołać funkcję, która ma strukturę niedanych kopiowalnychną jako typ zwracany, można zdefiniować typ pomocnika danych kopiowalnych o takim samym rozmiarze co typ inny niż danych kopiowalnych i przekonwertować dane po powrocie funkcji.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Przekazywanie struktur](passing-structures.md)  
 Identyfikuje problemy z przekazywaniem struktur danych ze wstępnie zdefiniowanym układem.  
  
 [Funkcje wywołania zwrotnego](callback-functions.md)  
 Zawiera podstawowe informacje na temat funkcji wywołania zwrotnego.  
  
 [Instrukcje: Implementowanie funkcji wywołania zwrotnego](how-to-implement-callback-functions.md)  
 Opisuje sposób implementowania funkcji wywołania zwrotnego w kodzie zarządzanym.  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Wykorzystywanie niezarządzanych funkcji DLL](consuming-unmanaged-dll-functions.md)  
 Opisuje sposób wywoływania niezarządzanych funkcji DLL przy użyciu wywołania platformy.  
  
 [Organizowanie danych w wywołaniu platformy](marshaling-data-with-platform-invoke.md)  
 Opisuje sposób deklarowania parametrów metody i przekazywania argumentów do funkcji wyeksportowanych przez niezarządzane biblioteki.
