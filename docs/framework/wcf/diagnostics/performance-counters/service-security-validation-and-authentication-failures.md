---
title: 'Usługa: Błędy walidacji i uwierzytelniania'
ms.date: 03/30/2017
ms.assetid: 55c98268-b1ad-459d-851b-25ef52248187
ms.openlocfilehash: d89419d7d579d29a1c57370d61eefb8b26333a40
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96236861"
---
# <a name="service-security-validation-and-authentication-failures"></a>Usługa: Błędy walidacji i uwierzytelniania

Nazwa licznika: Błędy walidacji zabezpieczeń i uwierzytelniania  
  
## <a name="description"></a>Opis  

 Ten licznik jest zwiększany za każdym razem, gdy komunikat zostanie odrzucony z powodu problemu z zabezpieczeniami, którego nie dotyczy licznik "wywołania zabezpieczeń bez autoryzacji". Takie problemy obejmują:  
  
- Nie można odczytać z komunikatu tokenu klienta.  
  
- Uwierzytelnianie tokenu klienta nie powiodło się (na przykład złe hasło).  
  
- Weryfikacja podpisu nie powiodła się (na przykład komunikat został naruszony).  
  
- Komunikat jest duplikatem z poprzedniego, który może wystąpić podczas ataku metodą powtórzeń.  
  
- Wystąpił błąd odszyfrowywania.  
  
- W komunikacie brakuje niektórych wymaganych elementów (na przykład braku sygnatury czasowej lub zaszyfrowanego bloku danych).  
  
- Wystąpiły błędy podczas uzgadniania TLSNEGO/SPNEGO.
