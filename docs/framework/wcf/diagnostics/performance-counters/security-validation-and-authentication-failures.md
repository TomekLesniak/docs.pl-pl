---
title: Błędy walidacji zabezpieczeń i uwierzytelniania
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
ms.openlocfilehash: 3bcc6111f322a3bd8169567e8f436871eb19f879
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96253053"
---
# <a name="security-validation-and-authentication-failures"></a><span data-ttu-id="26b5f-102">Błędy walidacji zabezpieczeń i uwierzytelniania</span><span class="sxs-lookup"><span data-stu-id="26b5f-102">Security Validation and Authentication Failures</span></span>

<span data-ttu-id="26b5f-103">Nazwa licznika: Błędy walidacji zabezpieczeń i uwierzytelniania</span><span class="sxs-lookup"><span data-stu-id="26b5f-103">Counter name: Security Validation and Authentication Failures</span></span>  
  
## <a name="description"></a><span data-ttu-id="26b5f-104">Opis</span><span class="sxs-lookup"><span data-stu-id="26b5f-104">Description</span></span>  

 <span data-ttu-id="26b5f-105">Ten licznik jest zwiększany za każdym razem, gdy komunikat zostanie odrzucony z powodu problemu z zabezpieczeniami, którego nie dotyczy licznik "wywołania zabezpieczeń bez autoryzacji".</span><span class="sxs-lookup"><span data-stu-id="26b5f-105">This counter is incremented whenever a message is rejected due to a security problem not covered by the "Security Calls Not Authorized" counter.</span></span> <span data-ttu-id="26b5f-106">Takie problemy obejmują:</span><span class="sxs-lookup"><span data-stu-id="26b5f-106">Such problems include:</span></span>  
  
- <span data-ttu-id="26b5f-107">Nie można odczytać z komunikatu tokenu klienta.</span><span class="sxs-lookup"><span data-stu-id="26b5f-107">Client token cannot be read from the message.</span></span>  
  
- <span data-ttu-id="26b5f-108">Uwierzytelnianie tokenu klienta nie powiodło się (na przykład złe hasło).</span><span class="sxs-lookup"><span data-stu-id="26b5f-108">Client token has failed authentication (for example, bad password).</span></span>  
  
- <span data-ttu-id="26b5f-109">Weryfikacja podpisu nie powiodła się (na przykład komunikat został naruszony).</span><span class="sxs-lookup"><span data-stu-id="26b5f-109">Signature verification has failed (for example, the message has been tampered).</span></span>  
  
- <span data-ttu-id="26b5f-110">Komunikat jest duplikatem z poprzedniego, który może wystąpić podczas ataku metodą powtórzeń.</span><span class="sxs-lookup"><span data-stu-id="26b5f-110">The message is a duplicate from a previous one, which can happen during a replay attack.</span></span>  
  
- <span data-ttu-id="26b5f-111">Wystąpił błąd odszyfrowywania.</span><span class="sxs-lookup"><span data-stu-id="26b5f-111">A decryption failure has occurred.</span></span>  
  
- <span data-ttu-id="26b5f-112">W komunikacie brakuje niektórych wymaganych elementów (na przykład braku sygnatury czasowej lub zaszyfrowanego bloku danych).</span><span class="sxs-lookup"><span data-stu-id="26b5f-112">Some required elements (for example, missing timestamp or encrypted data block) are missing from the message.</span></span>  
  
- <span data-ttu-id="26b5f-113">Wystąpiły błędy podczas uzgadniania TLSNEGO/SPNEGO.</span><span class="sxs-lookup"><span data-stu-id="26b5f-113">Errors have occurred during TLSNEGO/SPNEGO handshake.</span></span>
