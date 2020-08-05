---
title: Model kryptografii .NET
description: Przejrzyj implementacje zwykłych algorytmów kryptograficznych w programie .NET. Zapoznaj się z rozszerzalnym modelem kryptografii dziedziczenia obiektów, projektem strumienia i konfiguracją &.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], model
- encryption [.NET], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
ms.openlocfilehash: 0b3e07238bf0932572c222f7b947cfa7ae0221a9
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556998"
---
# <a name="net-cryptography-model"></a><span data-ttu-id="09e0f-104">Model kryptografii .NET</span><span class="sxs-lookup"><span data-stu-id="09e0f-104">.NET Cryptography Model</span></span>

<span data-ttu-id="09e0f-105">Platforma .NET udostępnia implementacje wielu standardowych algorytmów kryptograficznych, a model kryptografii .NET jest rozszerzalny.</span><span class="sxs-lookup"><span data-stu-id="09e0f-105">.NET provides implementations of many standard cryptographic algorithms, and the .NET cryptography model is extensible.</span></span>

## <a name="object-inheritance"></a><span data-ttu-id="09e0f-106">Dziedziczenie obiektu</span><span class="sxs-lookup"><span data-stu-id="09e0f-106">Object Inheritance</span></span>

<span data-ttu-id="09e0f-107">System kryptograficzny platformy .NET implementuje rozszerzalny wzorzec dziedziczenia klasy pochodnej.</span><span class="sxs-lookup"><span data-stu-id="09e0f-107">The .NET cryptography system implements an extensible pattern of derived class inheritance.</span></span> <span data-ttu-id="09e0f-108">Hierarchia jest następująca:</span><span class="sxs-lookup"><span data-stu-id="09e0f-108">The hierarchy is as follows:</span></span>

- <span data-ttu-id="09e0f-109">Klasa typu algorytmu, taka jak <xref:System.Security.Cryptography.SymmetricAlgorithm> , <xref:System.Security.Cryptography.AsymmetricAlgorithm> , lub <xref:System.Security.Cryptography.HashAlgorithm> .</span><span class="sxs-lookup"><span data-stu-id="09e0f-109">Algorithm type class, such as <xref:System.Security.Cryptography.SymmetricAlgorithm>,  <xref:System.Security.Cryptography.AsymmetricAlgorithm>, or <xref:System.Security.Cryptography.HashAlgorithm>.</span></span> <span data-ttu-id="09e0f-110">Ten poziom jest abstrakcyjny.</span><span class="sxs-lookup"><span data-stu-id="09e0f-110">This level is abstract.</span></span>

- <span data-ttu-id="09e0f-111">Klasa algorytmu, która dziedziczy z klasy typu algorytmu; na przykład, <xref:System.Security.Cryptography.Aes> , <xref:System.Security.Cryptography.RSA> lub <xref:System.Security.Cryptography.ECDiffieHellman> .</span><span class="sxs-lookup"><span data-stu-id="09e0f-111">Algorithm class that inherits from an algorithm type class; for example, <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RSA>, or <xref:System.Security.Cryptography.ECDiffieHellman>.</span></span> <span data-ttu-id="09e0f-112">Ten poziom jest abstrakcyjny.</span><span class="sxs-lookup"><span data-stu-id="09e0f-112">This level is abstract.</span></span>

- <span data-ttu-id="09e0f-113">Implementacja klasy algorytmu, która dziedziczy z klasy algorytmu; na przykład, <xref:System.Security.Cryptography.AesManaged> , <xref:System.Security.Cryptography.RC2CryptoServiceProvider> lub <xref:System.Security.Cryptography.ECDiffieHellmanCng> .</span><span class="sxs-lookup"><span data-stu-id="09e0f-113">Implementation of an algorithm class that inherits from an algorithm class; for example, <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider>, or <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span></span> <span data-ttu-id="09e0f-114">Ten poziom jest w pełni zaimplementowany.</span><span class="sxs-lookup"><span data-stu-id="09e0f-114">This level is fully implemented.</span></span>

<span data-ttu-id="09e0f-115">Ten wzorzec klas pochodnych pozwala dodać nowy algorytm lub nową implementację istniejącego algorytmu.</span><span class="sxs-lookup"><span data-stu-id="09e0f-115">This pattern of derived classes lets you add a new algorithm or a new implementation of an existing algorithm.</span></span> <span data-ttu-id="09e0f-116">Na przykład, aby utworzyć nowy algorytm klucza publicznego, można dziedziczyć z <xref:System.Security.Cryptography.AsymmetricAlgorithm> klasy.</span><span class="sxs-lookup"><span data-stu-id="09e0f-116">For example, to create a new public-key algorithm, you would inherit from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class.</span></span> <span data-ttu-id="09e0f-117">Aby utworzyć nową implementację określonego algorytmu, należy utworzyć nieabstrakcyjną klasę pochodną tego algorytmu.</span><span class="sxs-lookup"><span data-stu-id="09e0f-117">To create a new implementation of a specific algorithm, you would create a non-abstract derived class of that algorithm.</span></span>

## <a name="how-algorithms-are-implemented-in-net"></a><span data-ttu-id="09e0f-118">Jak zaimplementowane są algorytmy w programie .NET</span><span class="sxs-lookup"><span data-stu-id="09e0f-118">How Algorithms Are Implemented in .NET</span></span>

<span data-ttu-id="09e0f-119">Przykładem różnych implementacji dla algorytmu, należy wziąć pod uwagę Algorytmy symetryczne.</span><span class="sxs-lookup"><span data-stu-id="09e0f-119">As an example of the different implementations available for an algorithm, consider symmetric algorithms.</span></span> <span data-ttu-id="09e0f-120">Podstawą dla wszystkich algorytmów symetrycznych jest <xref:System.Security.Cryptography.SymmetricAlgorithm> , która jest dziedziczona przez <xref:System.Security.Cryptography.Aes> , <xref:System.Security.Cryptography.TripleDES> i inne, które nie są już zalecane.</span><span class="sxs-lookup"><span data-stu-id="09e0f-120">The base for all symmetric algorithms is <xref:System.Security.Cryptography.SymmetricAlgorithm>, which is inherited by <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.TripleDES>, and others that are no longer recommended.</span></span>

<span data-ttu-id="09e0f-121"><xref:System.Security.Cryptography.Aes>jest dziedziczona przez <xref:System.Security.Cryptography.AesCryptoServiceProvider> , <xref:System.Security.Cryptography.AesCng> , i <xref:System.Security.Cryptography.AesManaged> .</span><span class="sxs-lookup"><span data-stu-id="09e0f-121"><xref:System.Security.Cryptography.Aes> is inherited by <xref:System.Security.Cryptography.AesCryptoServiceProvider>, <xref:System.Security.Cryptography.AesCng>, and <xref:System.Security.Cryptography.AesManaged>.</span></span>

<span data-ttu-id="09e0f-122">W .NET Framework w systemie Windows:</span><span class="sxs-lookup"><span data-stu-id="09e0f-122">In .NET Framework on Windows:</span></span>

* <span data-ttu-id="09e0f-123">`*CryptoServiceProvider`klasy algorytmu, takie jak <xref:System.Security.Cryptography.AesCryptoServiceProvider> , są otokami wokół implementacji algorytmu Windows CRYPTOGRAPHY API (CAPI).</span><span class="sxs-lookup"><span data-stu-id="09e0f-123">`*CryptoServiceProvider` algorithm classes, such as <xref:System.Security.Cryptography.AesCryptoServiceProvider>, are wrappers around the Windows Cryptography API (CAPI) implementation of an algorithm.</span></span>
* <span data-ttu-id="09e0f-124">`*Cng`klasy algorytmu, takie jak <xref:System.Security.Cryptography.ECDiffieHellmanCng> są otokami wokół implementacji Windows Cryptography Next Generation (CNG).</span><span class="sxs-lookup"><span data-stu-id="09e0f-124">`*Cng` algorithm classes, such as <xref:System.Security.Cryptography.ECDiffieHellmanCng> are wrappers around the Windows Cryptography Next Generation (CNG) implementation.</span></span>
* <span data-ttu-id="09e0f-125">`*Managed`klasy, takie jak <xref:System.Security.Cryptography.AesManaged> , są zapisywane w całości w kodzie zarządzanym.</span><span class="sxs-lookup"><span data-stu-id="09e0f-125">`*Managed` classes, such as <xref:System.Security.Cryptography.AesManaged>, are written entirely in managed code.</span></span> <span data-ttu-id="09e0f-126">`*Managed`implementacje nie są certyfikowane przez standardy FIPS (Federal Information Processing Standards) i mogą być wolniejsze niż `*CryptoServiceProvider` `*Cng` klasy otoki i.</span><span class="sxs-lookup"><span data-stu-id="09e0f-126">`*Managed` implementations are not certified by the Federal Information Processing Standards (FIPS), and may be slower than the `*CryptoServiceProvider` and `*Cng` wrapper classes.</span></span>

<span data-ttu-id="09e0f-127">W przypadku programów .NET Core i .NET 5 i nowszych wersje wszystkie klasy implementacji ( `*CryptoServiceProvider` , `*Managed` i `*Cng` ) są otokami dla algorytmów systemu operacyjnego (OS).</span><span class="sxs-lookup"><span data-stu-id="09e0f-127">In .NET Core and .NET 5 and later versions, all implementation classes (`*CryptoServiceProvider`, `*Managed`, and `*Cng`) are wrappers for the operating system (OS) algorithms.</span></span> <span data-ttu-id="09e0f-128">Jeśli algorytmy systemu operacyjnego są certyfikowane pod kątem zgodności ze standardem FIPS, .NET używa algorytmów certyfikowanych przez FIPS.</span><span class="sxs-lookup"><span data-stu-id="09e0f-128">If the OS algorithms are FIPS-certified, then .NET uses FIPS-certified algorithms.</span></span> <span data-ttu-id="09e0f-129">Aby uzyskać więcej informacji, zobacz [Kryptografia międzyplatformowa](cross-platform-cryptography.md).</span><span class="sxs-lookup"><span data-stu-id="09e0f-129">For more information, see [Cross-Platform Cryptography](cross-platform-cryptography.md).</span></span>

<span data-ttu-id="09e0f-130">W większości przypadków nie trzeba bezpośrednio odwoływać się do klasy implementacji algorytmu, takiej jak `AesCryptoServiceProvider` .</span><span class="sxs-lookup"><span data-stu-id="09e0f-130">In most cases, you don't need to directly reference an algorithm implementation class, such as `AesCryptoServiceProvider`.</span></span> <span data-ttu-id="09e0f-131">Metody i właściwości, które zazwyczaj są potrzebne, znajdują się w klasie algorytmu podstawowego, na przykład `Aes` .</span><span class="sxs-lookup"><span data-stu-id="09e0f-131">The methods and properties you typically need are on the base algorithm class, such as `Aes`.</span></span> <span data-ttu-id="09e0f-132">Utwórz wystąpienie domyślnej klasy implementacji przy użyciu metody fabryki w klasie algorytmu podstawowego i zapoznaj się z klasą algorytmu podstawowego.</span><span class="sxs-lookup"><span data-stu-id="09e0f-132">Create an instance of a default implementation class by using a factory method on the base algorithm class, and refer to the base algorithm class.</span></span> <span data-ttu-id="09e0f-133">Na przykład zobacz wyróżniony wiersz kodu w następującym przykładzie:</span><span class="sxs-lookup"><span data-stu-id="09e0f-133">For example, see the highlighted line of code in the following example:</span></span>

:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs" highlight="16":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb" highlight="12":::

## <a name="cryptographic-configuration"></a><span data-ttu-id="09e0f-134">Konfiguracja kryptograficzna</span><span class="sxs-lookup"><span data-stu-id="09e0f-134">Cryptographic Configuration</span></span>

<span data-ttu-id="09e0f-135">Konfiguracja kryptograficzna pozwala rozwiązać konkretną implementację algorytmu do nazwy algorytmu, umożliwiając rozszerzanie klas kryptografii platformy .NET.</span><span class="sxs-lookup"><span data-stu-id="09e0f-135">Cryptographic configuration lets you resolve a specific implementation of an algorithm to an algorithm name, allowing extensibility of the .NET cryptography classes.</span></span> <span data-ttu-id="09e0f-136">Możesz dodać własną implementację sprzętu lub oprogramowania do algorytmu i zmapować implementację do wybranej nazwy algorytmu.</span><span class="sxs-lookup"><span data-stu-id="09e0f-136">You can add your own hardware or software implementation of an algorithm and map the implementation to the algorithm name of your choice.</span></span> <span data-ttu-id="09e0f-137">Jeśli w pliku konfiguracji nie określono algorytmu, zostaną użyte ustawienia domyślne.</span><span class="sxs-lookup"><span data-stu-id="09e0f-137">If an algorithm is not specified in the configuration file, the default settings are used.</span></span>

## <a name="choosing-an-algorithm"></a><span data-ttu-id="09e0f-138">Wybieranie algorytmu</span><span class="sxs-lookup"><span data-stu-id="09e0f-138">Choosing an Algorithm</span></span>

<span data-ttu-id="09e0f-139">Istnieje możliwość wybrania algorytmu z różnych przyczyn: na przykład w celu zapewnienia integralności danych lub wygenerowania klucza.</span><span class="sxs-lookup"><span data-stu-id="09e0f-139">You can select an algorithm for different reasons: for example, for data integrity, for data privacy, or to generate a key.</span></span> <span data-ttu-id="09e0f-140">Algorytmy symetryczne i hash są przeznaczone do ochrony danych z powodów związanych z integralnością (ochrona przed zmianami) lub z przyczyn zachowania poufności informacji (ochrona przed wyświetlaniem).</span><span class="sxs-lookup"><span data-stu-id="09e0f-140">Symmetric and hash algorithms are intended for protecting data for either integrity reasons (protect from change) or privacy reasons (protect from viewing).</span></span> <span data-ttu-id="09e0f-141">Algorytmy wyznaczania wartości skrótu są używane głównie w celu zapewnienia integralności danych.</span><span class="sxs-lookup"><span data-stu-id="09e0f-141">Hash algorithms are used primarily for data integrity.</span></span>

<span data-ttu-id="09e0f-142">Poniżej znajduje się lista zalecanych algorytmów według aplikacji:</span><span class="sxs-lookup"><span data-stu-id="09e0f-142">Here is a list of recommended algorithms by application:</span></span>

- <span data-ttu-id="09e0f-143">Prywatność danych:</span><span class="sxs-lookup"><span data-stu-id="09e0f-143">Data privacy:</span></span>
  - <xref:System.Security.Cryptography.Aes>
- <span data-ttu-id="09e0f-144">Integralność danych:</span><span class="sxs-lookup"><span data-stu-id="09e0f-144">Data integrity:</span></span>
  - <xref:System.Security.Cryptography.HMACSHA256>
  - <xref:System.Security.Cryptography.HMACSHA512>
- <span data-ttu-id="09e0f-145">Podpis cyfrowy:</span><span class="sxs-lookup"><span data-stu-id="09e0f-145">Digital signature:</span></span>
  - <xref:System.Security.Cryptography.ECDsa>
  - <xref:System.Security.Cryptography.RSA>
- <span data-ttu-id="09e0f-146">Wymiana kluczy:</span><span class="sxs-lookup"><span data-stu-id="09e0f-146">Key exchange:</span></span>
  - <xref:System.Security.Cryptography.ECDiffieHellman>
  - <xref:System.Security.Cryptography.RSA>
- <span data-ttu-id="09e0f-147">Generowanie liczb losowych:</span><span class="sxs-lookup"><span data-stu-id="09e0f-147">Random number generation:</span></span>
  - <xref:System.Security.Cryptography.RandomNumberGenerator.Create%2A?displayProperty=nameWithType>
- <span data-ttu-id="09e0f-148">Generowanie klucza przy użyciu hasła:</span><span class="sxs-lookup"><span data-stu-id="09e0f-148">Generating a key from a password:</span></span>
  - <xref:System.Security.Cryptography.Rfc2898DeriveBytes>

## <a name="see-also"></a><span data-ttu-id="09e0f-149">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="09e0f-149">See also</span></span>

- [<span data-ttu-id="09e0f-150">Usługi kryptograficzne</span><span class="sxs-lookup"><span data-stu-id="09e0f-150">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="09e0f-151">Kryptografia międzyplatformowa</span><span class="sxs-lookup"><span data-stu-id="09e0f-151">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="09e0f-152">Ochrona danych ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="09e0f-152">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
