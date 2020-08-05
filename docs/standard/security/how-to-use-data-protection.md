---
title: 'Instrukcje: Stosowanie ochrony danych'
description: Dowiedz się, jak używać ochrony danych, uzyskując dostęp do interfejsu API ochrony danych (DPAPI) w środowisku .NET.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET], data protection API
- data [.NET], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET], data protection API
- data protection API [.NET]
- decryption
- data [.NET], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: 263a07ddf357734e819fffdd41cdff60657adf15
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557063"
---
# <a name="how-to-use-data-protection"></a><span data-ttu-id="ad10c-103">Instrukcje: Stosowanie ochrony danych</span><span class="sxs-lookup"><span data-stu-id="ad10c-103">How to: Use Data Protection</span></span>

> [!NOTE]
> <span data-ttu-id="ad10c-104">Ten artykuł dotyczy systemu Windows.</span><span class="sxs-lookup"><span data-stu-id="ad10c-104">This article applies to Windows.</span></span>
>
> <span data-ttu-id="ad10c-105">Aby uzyskać informacje na temat ASP.NET Core, zobacz [ASP.NET Core ochrony danych](/aspnet/core/security/data-protection/introduction).</span><span class="sxs-lookup"><span data-stu-id="ad10c-105">For information about ASP.NET Core, see [ASP.NET Core Data Protection](/aspnet/core/security/data-protection/introduction).</span></span>

<span data-ttu-id="ad10c-106">Platforma .NET zapewnia dostęp do interfejsu API ochrony danych (DPAPI), który umożliwia szyfrowanie danych przy użyciu informacji z bieżącego konta użytkownika lub komputera.</span><span class="sxs-lookup"><span data-stu-id="ad10c-106">.NET provides access to the data protection API (DPAPI), which allows you to encrypt data using information from the current user account or computer.</span></span>  <span data-ttu-id="ad10c-107">Korzystając z interfejsu DPAPI, można złagodzić trudne problemy związane z jawnym generowaniem i przechowywaniem klucza kryptograficznego.</span><span class="sxs-lookup"><span data-stu-id="ad10c-107">When you use the DPAPI, you alleviate the difficult problem of explicitly generating and storing a cryptographic key.</span></span>  
  
<span data-ttu-id="ad10c-108">Użyj <xref:System.Security.Cryptography.ProtectedData> klasy, aby zaszyfrować kopię tablicy bajtów.</span><span class="sxs-lookup"><span data-stu-id="ad10c-108">Use the <xref:System.Security.Cryptography.ProtectedData> class to encrypt a copy of an array of bytes.</span></span> <span data-ttu-id="ad10c-109">Ta funkcja jest dostępna w .NET Framework, .NET Core i .NET 5.</span><span class="sxs-lookup"><span data-stu-id="ad10c-109">This functionality is available in .NET Framework, .NET Core, and .NET 5.</span></span>  <span data-ttu-id="ad10c-110">Możesz określić, że dane zaszyfrowane przez bieżące konto użytkownika mogą zostać odszyfrowane tylko przez to samo konto użytkownika, lub możesz określić, że dane zaszyfrowane przez bieżące konto użytkownika mogą zostać odszyfrowane za pomocą dowolnego konta na komputerze.</span><span class="sxs-lookup"><span data-stu-id="ad10c-110">You can specify that data encrypted by the current user account can be decrypted only by the same user account, or you can specify that data encrypted by the current user account can be decrypted by any account on the computer.</span></span>  <span data-ttu-id="ad10c-111"><xref:System.Security.Cryptography.DataProtectionScope>Szczegółowy opis opcji można znaleźć w wyliczeniu <xref:System.Security.Cryptography.ProtectedData> .</span><span class="sxs-lookup"><span data-stu-id="ad10c-111">See the <xref:System.Security.Cryptography.DataProtectionScope> enumeration for a detailed description of <xref:System.Security.Cryptography.ProtectedData> options.</span></span>  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a><span data-ttu-id="ad10c-112">Aby zaszyfrować dane do pliku lub strumienia przy użyciu ochrony danych</span><span class="sxs-lookup"><span data-stu-id="ad10c-112">To encrypt data to a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="ad10c-113">Utwórz entropię losową.</span><span class="sxs-lookup"><span data-stu-id="ad10c-113">Create random entropy.</span></span>  
  
2. <span data-ttu-id="ad10c-114">Wywołaj metodę statyczną <xref:System.Security.Cryptography.ProtectedData.Protect%2A> podczas przekazywania tablicy bajtów do szyfrowania, entropii i zakresu ochrony danych.</span><span class="sxs-lookup"><span data-stu-id="ad10c-114">Call the static <xref:System.Security.Cryptography.ProtectedData.Protect%2A> method while passing an array of bytes to encrypt, the entropy, and the data protection scope.</span></span>  
  
3. <span data-ttu-id="ad10c-115">Zapisz dane zaszyfrowane do pliku lub strumienia.</span><span class="sxs-lookup"><span data-stu-id="ad10c-115">Write the encrypted data to a file or stream.</span></span>  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a><span data-ttu-id="ad10c-116">Aby odszyfrować dane z pliku lub strumienia przy użyciu ochrony danych</span><span class="sxs-lookup"><span data-stu-id="ad10c-116">To decrypt data from a file or stream using data protection</span></span>  
  
1. <span data-ttu-id="ad10c-117">Odczytaj zaszyfrowane dane z pliku lub strumienia.</span><span class="sxs-lookup"><span data-stu-id="ad10c-117">Read the encrypted data from a file or stream.</span></span>  
  
2. <span data-ttu-id="ad10c-118">Wywołaj metodę statyczną <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> podczas przekazywania tablicy bajtów do odszyfrowania i zakresu ochrony danych.</span><span class="sxs-lookup"><span data-stu-id="ad10c-118">Call the static <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> method while passing an array of bytes to decrypt and the data protection scope.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad10c-119">Przykład</span><span class="sxs-lookup"><span data-stu-id="ad10c-119">Example</span></span>

<span data-ttu-id="ad10c-120">Poniższy przykład kodu ilustruje dwie formy szyfrowania i odszyfrowywania.</span><span class="sxs-lookup"><span data-stu-id="ad10c-120">The following code example demonstrates two forms of encryption and decryption.</span></span>  <span data-ttu-id="ad10c-121">Najpierw kod szyfruje, a następnie odszyfrowuje tablicę bajtów w pamięci.</span><span class="sxs-lookup"><span data-stu-id="ad10c-121">First, the code example encrypts and then decrypts an in-memory array of bytes.</span></span>  <span data-ttu-id="ad10c-122">W przykładzie kod szyfruje kopię tablicy bajtowej, zapisuje ją w pliku, ładuje dane z powrotem z pliku, a następnie odszyfrowuje dane.</span><span class="sxs-lookup"><span data-stu-id="ad10c-122">Next, the code example encrypts a copy of a byte array, saves it to a file, loads the data back from the file, and then decrypts the data.</span></span>  <span data-ttu-id="ad10c-123">Przykład wyświetla oryginalne dane, zaszyfrowane dane i odszyfrowane dane.</span><span class="sxs-lookup"><span data-stu-id="ad10c-123">The example displays the original data, the encrypted data, and the decrypted data.</span></span>

[!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
[!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ad10c-124">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="ad10c-124">Compiling the Code</span></span>  

<span data-ttu-id="ad10c-125">Ten przykład kompiluje i działa tylko w przypadku .NET Framework i uruchamiania w systemie Windows.</span><span class="sxs-lookup"><span data-stu-id="ad10c-125">This example compiles and runs only when targeting .NET Framework and running on Windows.</span></span>

- <span data-ttu-id="ad10c-126">Dołącz odwołanie do `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="ad10c-126">Include a reference to `System.Security.dll`.</span></span>  
  
- <span data-ttu-id="ad10c-127">Dołącz <xref:System> <xref:System.IO> <xref:System.Security.Cryptography> przestrzeń nazw,,, i <xref:System.Text> .</span><span class="sxs-lookup"><span data-stu-id="ad10c-127">Include the <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography>, and <xref:System.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad10c-128">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ad10c-128">See also</span></span>

- [<span data-ttu-id="ad10c-129">Model kryptografii</span><span class="sxs-lookup"><span data-stu-id="ad10c-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="ad10c-130">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="ad10c-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="ad10c-131">Kryptografia międzyplatformowa</span><span class="sxs-lookup"><span data-stu-id="ad10c-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
- [<span data-ttu-id="ad10c-132">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="ad10c-132">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
