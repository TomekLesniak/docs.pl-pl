---
title: 'Punkt końcowy: Błędy weryfikacji zabezpieczeń i uwierzytelniania'
ms.date: 03/30/2017
ms.assetid: 5bad60aa-6084-4c7b-aefd-9b581f04382e
ms.openlocfilehash: a9a4758b26c744c55af200aee22a7e90c5a5cf57
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256472"
---
# <a name="endpoint-security-validation-and-authentication-failures"></a>Punkt końcowy: Błędy weryfikacji zabezpieczeń i uwierzytelniania

Nazwa licznika: Błędy walidacji zabezpieczeń i uwierzytelniania  
  
## <a name="description"></a>Opis  

 Ten licznik jest zwiększany za każdym razem, gdy komunikat zostanie odrzucony z powodu problemu z zabezpieczeniami, którego nie dotyczy licznik "wywołania zabezpieczeń bez autoryzacji". Takie problemy obejmują:  
  
- Nie można odczytać z komunikatu tokenu klienta.  
  
- Uwierzytelnianie tokenu klienta nie powiodło się (nieprawidłowe hasło).  
  
- Weryfikacja podpisu nie powiodła się (komunikat został naruszony).  
  
- Komunikat jest duplikatem z poprzedniego, który może wystąpić podczas ataku metodą powtórzeń.  
  
- Wystąpił błąd odszyfrowywania.  
  
- W komunikacie brakuje niektórych wymaganych elementów (Brak znacznika czasu lub zaszyfrowanego bloku danych).  
  
- Wystąpiły błędy podczas uzgadniania TLSNEGO/SPNEGO.
