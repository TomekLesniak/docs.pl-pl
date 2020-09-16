---
title: 'Punkt końcowy: Niepowodzenia uwierzytelniania i weryfikacji zabezpieczeń na sekundę'
ms.date: 03/30/2017
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
ms.openlocfilehash: 8573c35f16d03e2f86310c054703c25a3175200c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541503"
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a>Punkt końcowy: Niepowodzenia uwierzytelniania i weryfikacji zabezpieczeń na sekundę
Nazwa licznika: Błędy walidacji zabezpieczeń i uwierzytelniania na sekundę  
  
## <a name="description"></a>Opis  
 Ten licznik jest zwiększany za każdym razem, gdy komunikat zostanie odrzucony z powodu problemu z zabezpieczeniami, którego nie dotyczy licznik "wywołania zabezpieczeń bez autoryzacji". Takie problemy obejmują:  
  
- Nie można odczytać z komunikatu tokenu klienta.  
  
- Uwierzytelnianie tokenu klienta nie powiodło się (na przykład złe hasło).  
  
- Weryfikacja podpisu nie powiodła się (na przykład komunikat został naruszony).  
  
- Komunikat jest duplikatem z poprzedniego, który może wystąpić podczas ataku metodą powtórzeń.  
  
- Wystąpił błąd odszyfrowywania.  
  
- W komunikacie brakuje niektórych wymaganych elementów (na przykład braku sygnatury czasowej lub zaszyfrowanego bloku danych).  
  
- Wystąpiły błędy podczas uzgadniania TLSNEGO/SPNEGO.  
  
 Ten licznik jest typem licznika wydajności [PERF_COUNTER_COUNTER](/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), którego wartość jest obliczana przy użyciu następującej formuły:  
  
 (N1-N0)/((D1-D0)/F)
