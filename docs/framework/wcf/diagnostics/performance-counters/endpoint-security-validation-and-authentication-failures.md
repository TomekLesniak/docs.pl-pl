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
# <a name="endpoint-security-validation-and-authentication-failures"></a><span data-ttu-id="9e8fe-102">Punkt końcowy: Błędy weryfikacji zabezpieczeń i uwierzytelniania</span><span class="sxs-lookup"><span data-stu-id="9e8fe-102">Endpoint: Security Validation and Authentication Failures</span></span>

<span data-ttu-id="9e8fe-103">Nazwa licznika: Błędy walidacji zabezpieczeń i uwierzytelniania</span><span class="sxs-lookup"><span data-stu-id="9e8fe-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="9e8fe-104">Opis</span><span class="sxs-lookup"><span data-stu-id="9e8fe-104">Description</span></span>  

 <span data-ttu-id="9e8fe-105">Ten licznik jest zwiększany za każdym razem, gdy komunikat zostanie odrzucony z powodu problemu z zabezpieczeniami, którego nie dotyczy licznik "wywołania zabezpieczeń bez autoryzacji".</span><span class="sxs-lookup"><span data-stu-id="9e8fe-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="9e8fe-106">Takie problemy obejmują:</span><span class="sxs-lookup"><span data-stu-id="9e8fe-106">Such problems include:</span></span>  
  
- <span data-ttu-id="9e8fe-107">Nie można odczytać z komunikatu tokenu klienta.</span><span class="sxs-lookup"><span data-stu-id="9e8fe-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="9e8fe-108">Uwierzytelnianie tokenu klienta nie powiodło się (nieprawidłowe hasło).</span><span class="sxs-lookup"><span data-stu-id="9e8fe-108">Client token has failed authentication (bad password).</span></span>  
  
- <span data-ttu-id="9e8fe-109">Weryfikacja podpisu nie powiodła się (komunikat został naruszony).</span><span class="sxs-lookup"><span data-stu-id="9e8fe-109">Signature verification has failed (the message has been tampered).</span></span>  
  
- <span data-ttu-id="9e8fe-110">Komunikat jest duplikatem z poprzedniego, który może wystąpić podczas ataku metodą powtórzeń.</span><span class="sxs-lookup"><span data-stu-id="9e8fe-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="9e8fe-111">Wystąpił błąd odszyfrowywania.</span><span class="sxs-lookup"><span data-stu-id="9e8fe-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="9e8fe-112">W komunikacie brakuje niektórych wymaganych elementów (Brak znacznika czasu lub zaszyfrowanego bloku danych).</span><span class="sxs-lookup"><span data-stu-id="9e8fe-112">Some required elements (missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="9e8fe-113">Wystąpiły błędy podczas uzgadniania TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="9e8fe-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
