---
title: Zapewnianie integralności danych za pomocą wartości skrótu
description: Dowiedz się, jak zapewnić integralność danych przy użyciu kodów skrótu w programie .NET. Wartość skrótu to wartość liczbowa o stałej długości, która jednoznacznie identyfikuje dane.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- generating hash
- verifying hash codes
- cryptography [.NET], hash
- data integrity
- checking hash codes
- encryption [.NET], hash
- hash
ms.assetid: 33660f33-b70f-4dca-8c87-ab35cfc2961a
ms.openlocfilehash: 085a0ea387e3415e6e916bcdf9055ffaa6753fef
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831094"
---
# <a name="ensuring-data-integrity-with-hash-codes"></a><span data-ttu-id="83129-104">Zapewnianie integralności danych za pomocą wartości skrótu</span><span class="sxs-lookup"><span data-stu-id="83129-104">Ensuring Data Integrity with Hash Codes</span></span>
<span data-ttu-id="83129-105">Wartość skrótu to wartość liczbowa o stałej długości, która jednoznacznie identyfikuje dane.</span><span class="sxs-lookup"><span data-stu-id="83129-105">A hash value is a numeric value of a fixed length that uniquely identifies data.</span></span> <span data-ttu-id="83129-106">Wartości skrótu przedstawiają duże ilości danych jako dużo mniejsze wartości liczbowe, dlatego są używane z podpisami cyfrowymi.</span><span class="sxs-lookup"><span data-stu-id="83129-106">Hash values represent large amounts of data as much smaller numeric values, so they are used with digital signatures.</span></span> <span data-ttu-id="83129-107">Wartość skrótu można podpisywać bardziej wydajnie niż podpisywanie większej wartości.</span><span class="sxs-lookup"><span data-stu-id="83129-107">You can sign a hash value more efficiently than signing the larger value.</span></span> <span data-ttu-id="83129-108">Wartości skrótu są również przydatne do sprawdzania integralności danych wysyłanych za pomocą niezabezpieczonych kanałów.</span><span class="sxs-lookup"><span data-stu-id="83129-108">Hash values are also useful for verifying the integrity of data sent through insecure channels.</span></span> <span data-ttu-id="83129-109">Wartość skrótu odebranych danych może być porównywana z wartością skrótu danych, która została wysłana w celu określenia, czy dane zostały zmienione.</span><span class="sxs-lookup"><span data-stu-id="83129-109">The hash value of received data can be compared to the hash value of data as it was sent to determine whether the data was altered.</span></span>  
  
<span data-ttu-id="83129-110">W tym temacie opisano sposób generowania i weryfikowania kodów skrótów przy użyciu klas w <xref:System.Security.Cryptography> przestrzeni nazw.</span><span class="sxs-lookup"><span data-stu-id="83129-110">This topic describes how to generate and verify hash codes by using the classes in the <xref:System.Security.Cryptography> namespace.</span></span>  
  
## <a name="generating-a-hash"></a><span data-ttu-id="83129-111">Generowanie skrótu</span><span class="sxs-lookup"><span data-stu-id="83129-111">Generating a Hash</span></span>

 <span data-ttu-id="83129-112">Zarządzane klasy skrótów mogą mieszać tablicę bajtów lub obiekt strumienia zarządzanego.</span><span class="sxs-lookup"><span data-stu-id="83129-112">The managed hash classes can hash either an array of bytes or a managed stream object.</span></span> <span data-ttu-id="83129-113">W poniższym przykładzie jest używany algorytm skrótu SHA1 do tworzenia wartości skrótu dla ciągu.</span><span class="sxs-lookup"><span data-stu-id="83129-113">The following example uses the SHA1 hash algorithm to create a hash value for a string.</span></span> <span data-ttu-id="83129-114">W przykładzie użyto <xref:System.Text.UnicodeEncoding> klasy do przekonwertowania ciągu na tablicę bajtów, które są zmieszane przy użyciu <xref:System.Security.Cryptography.SHA256> klasy.</span><span class="sxs-lookup"><span data-stu-id="83129-114">The example uses the <xref:System.Text.UnicodeEncoding> class to convert the string into an array of bytes that are hashed by using the <xref:System.Security.Cryptography.SHA256> class.</span></span> <span data-ttu-id="83129-115">Wartość skrótu zostanie następnie wyświetlona w konsoli programu.</span><span class="sxs-lookup"><span data-stu-id="83129-115">The hash value is then displayed to the console.</span></span>  

 [!code-csharp[GeneratingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/generatingahash/cs/program.cs#1)]
 [!code-vb[GeneratingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/generatingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="83129-116">Ten kod będzie wyświetlał następujący ciąg do konsoli:</span><span class="sxs-lookup"><span data-stu-id="83129-116">This code will display the following string to the console:</span></span>  
  
 `185 203 236 22 3 228 27 130 87 23 244 15 87 88 14 43 37 61 106 224 81 172 224 211 104 85 194 197 194 25 120 217`  
  
## <a name="verifying-a-hash"></a><span data-ttu-id="83129-117">Weryfikowanie skrótu</span><span class="sxs-lookup"><span data-stu-id="83129-117">Verifying a Hash</span></span>

 <span data-ttu-id="83129-118">Dane można porównać do wartości skrótu, aby określić jej integralność.</span><span class="sxs-lookup"><span data-stu-id="83129-118">Data can be compared to a hash value to determine its integrity.</span></span> <span data-ttu-id="83129-119">Zwykle dane są zmieszane w określonym czasie, a wartość skrótu jest chroniona w jakiś sposób.</span><span class="sxs-lookup"><span data-stu-id="83129-119">Usually, data is hashed at a certain time and the hash value is protected in some way.</span></span> <span data-ttu-id="83129-120">Później można ponownie wykonać mieszanie danych i porównywać ją z wartością chronioną.</span><span class="sxs-lookup"><span data-stu-id="83129-120">At a later time, the data can be hashed again and compared to the protected value.</span></span> <span data-ttu-id="83129-121">W przypadku dopasowania wartości skrótu dane nie zostały zmienione.</span><span class="sxs-lookup"><span data-stu-id="83129-121">If the hash values match, the data has not been altered.</span></span> <span data-ttu-id="83129-122">Jeśli wartości nie są zgodne, dane zostały uszkodzone.</span><span class="sxs-lookup"><span data-stu-id="83129-122">If the values do not match, the data has been corrupted.</span></span> <span data-ttu-id="83129-123">Aby ten system działał, chroniony skrót musi być zaszyfrowany lub przechowywany jako wpis tajny ze wszystkich niezaufanych stron.</span><span class="sxs-lookup"><span data-stu-id="83129-123">For this system to work, the protected hash must be encrypted or kept secret from all untrusted parties.</span></span>  
  
 <span data-ttu-id="83129-124">Poniższy przykład porównuje poprzednią wartość skrótu ciągu z nową wartością skrótu.</span><span class="sxs-lookup"><span data-stu-id="83129-124">The following example compares the previous hash value of a string to a new hash value.</span></span> <span data-ttu-id="83129-125">Ten przykład powoduje pętlę przez każdy bajt wartości skrótu i wykonuje porównanie.</span><span class="sxs-lookup"><span data-stu-id="83129-125">This example loops through each byte of the hash values and makes a comparison.</span></span>  
  
 [!code-csharp[VerifyingAHash#1](../../../samples/snippets/csharp/VS_Snippets_CLR/verifyingahash/cs/program.cs#1)]
 [!code-vb[VerifyingAHash#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/verifyingahash/vb/program.vb#1)]  
  
 <span data-ttu-id="83129-126">Jeśli dwie wartości skrótów są zgodne, ten kod wyświetla następujące polecenie w konsoli programu:</span><span class="sxs-lookup"><span data-stu-id="83129-126">If the two hash values match, this code displays the following to the console:</span></span>  
  
```console  
The hash codes match.  
```  
  
 <span data-ttu-id="83129-127">Jeśli nie są zgodne, kod wyświetla następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="83129-127">If they do not match, the code displays the following:</span></span>  
  
```console  
The hash codes do not match.  
```  
  
## <a name="see-also"></a><span data-ttu-id="83129-128">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="83129-128">See also</span></span>

- [<span data-ttu-id="83129-129">Model kryptografii</span><span class="sxs-lookup"><span data-stu-id="83129-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="83129-130">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="83129-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="83129-131">Kryptografia międzyplatformowa</span><span class="sxs-lookup"><span data-stu-id="83129-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="83129-132">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="83129-132">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
