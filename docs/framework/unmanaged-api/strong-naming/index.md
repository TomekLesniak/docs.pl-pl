---
title: Silne nazewnictwo (Niezarządzany wykaz interfejsów API)
ms.date: 03/30/2017
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
ms.openlocfilehash: 7e431f3a41fadb7247f20d7ab9bb9120e827b0cd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732297"
---
# <a name="strong-naming-unmanaged-api-reference"></a><span data-ttu-id="a215c-102">Silne nazewnictwo (Niezarządzany wykaz interfejsów API)</span><span class="sxs-lookup"><span data-stu-id="a215c-102">Strong Naming (Unmanaged API Reference)</span></span>

<span data-ttu-id="a215c-103">Interfejs API silnego nazewnictwa pozwala klientowi administrować podpisywaniem silnych nazw dla zestawów.</span><span class="sxs-lookup"><span data-stu-id="a215c-103">The strong naming API enables a client to administer strong name signing for assemblies.</span></span>  
  
 <span data-ttu-id="a215c-104">Podpisanie zestawu silną nazwą dodaje szyfrowanie kluczem publicznym do pliku zawierającego manifest zestawu.</span><span class="sxs-lookup"><span data-stu-id="a215c-104">Signing an assembly with a strong name adds a public key encryption to the file containing the assembly manifest.</span></span> <span data-ttu-id="a215c-105">Podpisywanie silnej nazwy pomaga weryfikować unikatowość nazw, zapobiega fałszowaniu nazw i zapewnia wywołującym unikatową tożsamość, gdy odwołanie jest rozwiązane.</span><span class="sxs-lookup"><span data-stu-id="a215c-105">Strong name signing helps verify name uniqueness, prevents name spoofing, and provides callers with a unique identity when a reference is resolved.</span></span> <span data-ttu-id="a215c-106">Jednak żaden poziom zaufania nie jest skojarzony z silną nazwą.</span><span class="sxs-lookup"><span data-stu-id="a215c-106">However, no level of trust is associated with a strong name.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a215c-107">W tej sekcji</span><span class="sxs-lookup"><span data-stu-id="a215c-107">In This Section</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a215c-108">Wszystkie te funkcje są przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-108">All of these functions have been deprecated starting with the .NET Framework 4.</span></span> <span data-ttu-id="a215c-109">W przypadku sugerowanych alternatyw należy zapoznać się z interfejsem [ICLRStrongName](../hosting/iclrstrongname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="a215c-109">For suggested alternatives, see the [ICLRStrongName](../hosting/iclrstrongname-interface.md) interface.</span></span>  
  
 [<span data-ttu-id="a215c-110">GetHashFromAssemblyFile — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-110">GetHashFromAssemblyFile Function</span></span>](gethashfromassemblyfile-function.md)  
 <span data-ttu-id="a215c-111">Pobiera skrót określonego pliku zestawu przy użyciu określonego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="a215c-111">Gets a hash of the specified assembly file, using the specified hash algorithm.</span></span> <span data-ttu-id="a215c-112">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-112">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-113">GetHashFromAssemblyFileW — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-113">GetHashFromAssemblyFileW Function</span></span>](gethashfromassemblyfilew-function.md)  
 <span data-ttu-id="a215c-114">Pobiera skrót pliku zestawu określony jako ciąg Unicode przy użyciu określonego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="a215c-114">Gets a hash of the assembly file specified as a Unicode string, using the specified hash algorithm.</span></span> <span data-ttu-id="a215c-115">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-115">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-116">GetHashFromBlob — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-116">GetHashFromBlob Function</span></span>](gethashfromblob-function.md)  
 <span data-ttu-id="a215c-117">Pobiera skrót zestawu pod określonym adresem pamięci przy użyciu określonego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="a215c-117">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span> <span data-ttu-id="a215c-118">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-118">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-119">GetHashFromFile — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-119">GetHashFromFile Function</span></span>](gethashfromfile-function.md)  
 <span data-ttu-id="a215c-120">Generuje skrót do zawartości określonego pliku.</span><span class="sxs-lookup"><span data-stu-id="a215c-120">Generates a hash over the contents of the specified file.</span></span>  <span data-ttu-id="a215c-121">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-121">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-122">GetHashFromFileW — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-122">GetHashFromFileW Function</span></span>](gethashfromfilew-function.md)  
 <span data-ttu-id="a215c-123">Generuje skrót do zawartości pliku określonego przez ciąg Unicode.</span><span class="sxs-lookup"><span data-stu-id="a215c-123">Generates a hash over the contents of the file specified by a Unicode string.</span></span> <span data-ttu-id="a215c-124">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-124">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-125">GetHashFromHandle — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-125">GetHashFromHandle Function</span></span>](gethashfromhandle-function.md)  
 <span data-ttu-id="a215c-126">Generuje skrót do zawartości pliku z określonym dojściem do pliku przy użyciu określonego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="a215c-126">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  <span data-ttu-id="a215c-127">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-127">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-128">StrongNameCompareAssemblies — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-128">StrongNameCompareAssemblies Function</span></span>](strongnamecompareassemblies-function.md)  
 <span data-ttu-id="a215c-129">Określa, czy dwa zestawy różnią się tylko sygnaturami silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="a215c-129">Determines whether two assemblies differ only by their strong name signatures.</span></span> <span data-ttu-id="a215c-130">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-130">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-131">StrongNameErrorInfo — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-131">StrongNameErrorInfo Function</span></span>](strongnameerrorinfo-function.md)  
 <span data-ttu-id="a215c-132">Pobiera kod ostatniego błędu, który został zgłoszony przez jedną z funkcji silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="a215c-132">Gets the last error code that was raised by one of the strong name functions.</span></span>  
  
 [<span data-ttu-id="a215c-133">StrongNameFreeBuffer — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-133">StrongNameFreeBuffer Function</span></span>](strongnamefreebuffer-function.md)  
 <span data-ttu-id="a215c-134">Zwalnia pamięć, która została przypisana przy użyciu poprzedniego wywołania funkcji silnej nazwy, takiej jak [StrongNameGetPublicKey —](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey —](strongnametokenfrompublickey-function.md)lub [StrongNameSignatureGeneration —](strongnamesignaturegeneration-function.md).</span><span class="sxs-lookup"><span data-stu-id="a215c-134">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md).</span></span>   <span data-ttu-id="a215c-135">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-135">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-136">StrongNameGetBlob — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-136">StrongNameGetBlob Function</span></span>](strongnamegetblob-function.md)  
 <span data-ttu-id="a215c-137">Wypełnia określony bufor reprezentacją binarną pliku wykonywalnego pod określonym adresem.</span><span class="sxs-lookup"><span data-stu-id="a215c-137">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span> <span data-ttu-id="a215c-138">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-138">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-139">StrongNameGetBlobFromImage — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-139">StrongNameGetBlobFromImage Function</span></span>](strongnamegetblobfromimage-function.md)  
 <span data-ttu-id="a215c-140">Pobiera binarną reprezentację obrazu zestawu pod określonym adresem pamięci.</span><span class="sxs-lookup"><span data-stu-id="a215c-140">Gets a binary representation of the assembly image at the specified memory address.</span></span> <span data-ttu-id="a215c-141">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-141">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-142">StrongNameGetPublicKey — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-142">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)  
 <span data-ttu-id="a215c-143">Pobiera klucz publiczny z pary kluczy prywatnych/publicznych.</span><span class="sxs-lookup"><span data-stu-id="a215c-143">Gets the public key from a private/public key pair.</span></span> <span data-ttu-id="a215c-144">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-144">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-145">StrongNameHashSize — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-145">StrongNameHashSize Function</span></span>](strongnamehashsize-function.md)  
 <span data-ttu-id="a215c-146">Pobiera rozmiar buforu wymagany dla skrótu przy użyciu określonego algorytmu wyznaczania wartości skrótu.</span><span class="sxs-lookup"><span data-stu-id="a215c-146">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  <span data-ttu-id="a215c-147">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-147">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-148">StrongNameKeyDelete — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-148">StrongNameKeyDelete Function</span></span>](strongnamekeydelete-function.md)  
 <span data-ttu-id="a215c-149">Usuwa określony kontener kluczy.</span><span class="sxs-lookup"><span data-stu-id="a215c-149">Deletes the specified key container.</span></span> <span data-ttu-id="a215c-150">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-150">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-151">StrongNameKeyGen — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-151">StrongNameKeyGen Function</span></span>](strongnamekeygen-function.md)  
 <span data-ttu-id="a215c-152">Tworzy nową parę kluczy publiczny/prywatny w celu użycia silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="a215c-152">Creates a new public/private key pair for strong name use.</span></span>  <span data-ttu-id="a215c-153">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-153">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-154">StrongNameKeyGenEx — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-154">StrongNameKeyGenEx Function</span></span>](strongnamekeygenex-function.md)  
 <span data-ttu-id="a215c-155">Generuje nową parę kluczy publicznych/prywatnych z określonym rozmiarem klucza w celu użycia silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="a215c-155">Generates a new public/private key pair with the specified key size for strong name use.</span></span> <span data-ttu-id="a215c-156">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-156">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-157">StrongNameKeyInstall — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-157">StrongNameKeyInstall Function</span></span>](strongnamekeyinstall-function.md)  
 <span data-ttu-id="a215c-158">Importuje parę kluczy publiczny/prywatny do kontenera.</span><span class="sxs-lookup"><span data-stu-id="a215c-158">Imports a public/private key pair into a container.</span></span>  <span data-ttu-id="a215c-159">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-159">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-160">StrongNameSignatureGeneration — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-160">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)  
 <span data-ttu-id="a215c-161">Generuje podpis silnej nazwy dla określonego zestawu.</span><span class="sxs-lookup"><span data-stu-id="a215c-161">Generates a strong name signature for the specified assembly.</span></span>   <span data-ttu-id="a215c-162">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-162">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-163">StrongNameSignatureGenerationEx — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-163">StrongNameSignatureGenerationEx Function</span></span>](strongnamesignaturegenerationex-function.md)  
 <span data-ttu-id="a215c-164">Generuje podpis silnej nazwy dla określonego zestawu, na podstawie określonych flag.</span><span class="sxs-lookup"><span data-stu-id="a215c-164">Generates a strong name signature for the specified assembly, based on the specified flags.</span></span>    <span data-ttu-id="a215c-165">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-165">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-166">StrongNameSignatureSize — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-166">StrongNameSignatureSize Function</span></span>](strongnamesignaturesize-function.md)  
 <span data-ttu-id="a215c-167">Zwraca rozmiar sygnatury silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="a215c-167">Returns the size of the strong name signature.</span></span> <span data-ttu-id="a215c-168">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-168">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-169">StrongNameSignatureVerification — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-169">StrongNameSignatureVerification Function</span></span>](strongnamesignatureverification-function.md)  
 <span data-ttu-id="a215c-170">Pobiera wartość wskazującą, czy manifest zestawu w podanej ścieżce zawiera sygnaturę silnej nazwy, która jest sprawdzana według określonych flag.</span><span class="sxs-lookup"><span data-stu-id="a215c-170">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature, which is verified according to the specified flags.</span></span> <span data-ttu-id="a215c-171">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-171">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-172">StrongNameSignatureVerificationEx — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-172">StrongNameSignatureVerificationEx Function</span></span>](strongnamesignatureverificationex-function.md)  
 <span data-ttu-id="a215c-173">Pobiera wartość wskazującą, czy manifest zestawu w podanej ścieżce zawiera podpis silnej nazwy.</span><span class="sxs-lookup"><span data-stu-id="a215c-173">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  <span data-ttu-id="a215c-174">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-174">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-175">StrongNameSignatureVerificationFromImage — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-175">StrongNameSignatureVerificationFromImage Function</span></span>](strongnamesignatureverificationfromimage-function.md)  
 <span data-ttu-id="a215c-176">Sprawdza, czy zestaw, który został już zamapowany na pamięć, jest prawidłowy dla skojarzonego klucza publicznego.</span><span class="sxs-lookup"><span data-stu-id="a215c-176">Verifies that an assembly that has already been mapped to memory is valid for the associated public key.</span></span> <span data-ttu-id="a215c-177">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-177">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-178">StrongNameTokenFromAssembly — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-178">StrongNameTokenFromAssembly Function</span></span>](strongnametokenfromassembly-function.md)  
 <span data-ttu-id="a215c-179">Tworzy token silnej nazwy z określonego pliku zestawu.</span><span class="sxs-lookup"><span data-stu-id="a215c-179">Creates a strong name token from the specified assembly file.</span></span>  <span data-ttu-id="a215c-180">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-180">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-181">StrongNameTokenFromAssemblyEx — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-181">StrongNameTokenFromAssemblyEx Function</span></span>](strongnametokenfromassemblyex-function.md)  
 <span data-ttu-id="a215c-182">Tworzy token silnej nazwy z określonego pliku zestawu i zwraca klucz publiczny.</span><span class="sxs-lookup"><span data-stu-id="a215c-182">Creates a strong name token from the specified assembly file, and returns the public key.</span></span> <span data-ttu-id="a215c-183">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-183">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-184">StrongNameTokenFromPublicKey — Funkcja</span><span class="sxs-lookup"><span data-stu-id="a215c-184">StrongNameTokenFromPublicKey Function</span></span>](strongnametokenfrompublickey-function.md)  
 <span data-ttu-id="a215c-185">Pobiera token reprezentujący klucz publiczny.</span><span class="sxs-lookup"><span data-stu-id="a215c-185">Gets a token representing a public key.</span></span> <span data-ttu-id="a215c-186">Przestarzałe, począwszy od .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="a215c-186">Deprecated starting with the .NET Framework 4.</span></span>  
  
 [<span data-ttu-id="a215c-187">PublicKeyBlob — Struktura</span><span class="sxs-lookup"><span data-stu-id="a215c-187">PublicKeyBlob Structure</span></span>](publickeyblob-structure.md)  
 <span data-ttu-id="a215c-188">Reprezentuje klucz publiczny pary kluczy publiczny/prywatny w formacie binarnym.</span><span class="sxs-lookup"><span data-stu-id="a215c-188">Represents the public key of a public/private key pair in binary format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a215c-189">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="a215c-189">See also</span></span>

- [<span data-ttu-id="a215c-190">ICLRStrongName — Interfejs</span><span class="sxs-lookup"><span data-stu-id="a215c-190">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="a215c-191">Niezarządzana dokumentacja interfejsu API</span><span class="sxs-lookup"><span data-stu-id="a215c-191">Unmanaged API Reference</span></span>](../index.md)
