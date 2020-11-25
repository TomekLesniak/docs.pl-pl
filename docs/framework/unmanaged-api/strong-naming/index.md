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
# <a name="strong-naming-unmanaged-api-reference"></a>Silne nazewnictwo (Niezarządzany wykaz interfejsów API)

Interfejs API silnego nazewnictwa pozwala klientowi administrować podpisywaniem silnych nazw dla zestawów.  
  
 Podpisanie zestawu silną nazwą dodaje szyfrowanie kluczem publicznym do pliku zawierającego manifest zestawu. Podpisywanie silnej nazwy pomaga weryfikować unikatowość nazw, zapobiega fałszowaniu nazw i zapewnia wywołującym unikatową tożsamość, gdy odwołanie jest rozwiązane. Jednak żaden poziom zaufania nie jest skojarzony z silną nazwą.  
  
## <a name="in-this-section"></a>W tej sekcji  
  
> [!NOTE]
> Wszystkie te funkcje są przestarzałe, począwszy od .NET Framework 4. W przypadku sugerowanych alternatyw należy zapoznać się z interfejsem [ICLRStrongName](../hosting/iclrstrongname-interface.md) .  
  
 [GetHashFromAssemblyFile — Funkcja](gethashfromassemblyfile-function.md)  
 Pobiera skrót określonego pliku zestawu przy użyciu określonego algorytmu wyznaczania wartości skrótu. Przestarzałe, począwszy od .NET Framework 4.  
  
 [GetHashFromAssemblyFileW — Funkcja](gethashfromassemblyfilew-function.md)  
 Pobiera skrót pliku zestawu określony jako ciąg Unicode przy użyciu określonego algorytmu wyznaczania wartości skrótu. Przestarzałe, począwszy od .NET Framework 4.  
  
 [GetHashFromBlob — Funkcja](gethashfromblob-function.md)  
 Pobiera skrót zestawu pod określonym adresem pamięci przy użyciu określonego algorytmu wyznaczania wartości skrótu. Przestarzałe, począwszy od .NET Framework 4.  
  
 [GetHashFromFile — Funkcja](gethashfromfile-function.md)  
 Generuje skrót do zawartości określonego pliku.  Przestarzałe, począwszy od .NET Framework 4.  
  
 [GetHashFromFileW — Funkcja](gethashfromfilew-function.md)  
 Generuje skrót do zawartości pliku określonego przez ciąg Unicode. Przestarzałe, począwszy od .NET Framework 4.  
  
 [GetHashFromHandle — Funkcja](gethashfromhandle-function.md)  
 Generuje skrót do zawartości pliku z określonym dojściem do pliku przy użyciu określonego algorytmu wyznaczania wartości skrótu.  Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameCompareAssemblies — Funkcja](strongnamecompareassemblies-function.md)  
 Określa, czy dwa zestawy różnią się tylko sygnaturami silnej nazwy. Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameErrorInfo — Funkcja](strongnameerrorinfo-function.md)  
 Pobiera kod ostatniego błędu, który został zgłoszony przez jedną z funkcji silnej nazwy.  
  
 [StrongNameFreeBuffer — Funkcja](strongnamefreebuffer-function.md)  
 Zwalnia pamięć, która została przypisana przy użyciu poprzedniego wywołania funkcji silnej nazwy, takiej jak [StrongNameGetPublicKey —](strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey —](strongnametokenfrompublickey-function.md)lub [StrongNameSignatureGeneration —](strongnamesignaturegeneration-function.md).   Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameGetBlob — Funkcja](strongnamegetblob-function.md)  
 Wypełnia określony bufor reprezentacją binarną pliku wykonywalnego pod określonym adresem. Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameGetBlobFromImage — Funkcja](strongnamegetblobfromimage-function.md)  
 Pobiera binarną reprezentację obrazu zestawu pod określonym adresem pamięci. Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameGetPublicKey — Funkcja](strongnamegetpublickey-function.md)  
 Pobiera klucz publiczny z pary kluczy prywatnych/publicznych. Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameHashSize — Funkcja](strongnamehashsize-function.md)  
 Pobiera rozmiar buforu wymagany dla skrótu przy użyciu określonego algorytmu wyznaczania wartości skrótu.  Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameKeyDelete — Funkcja](strongnamekeydelete-function.md)  
 Usuwa określony kontener kluczy. Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameKeyGen — Funkcja](strongnamekeygen-function.md)  
 Tworzy nową parę kluczy publiczny/prywatny w celu użycia silnej nazwy.  Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameKeyGenEx — Funkcja](strongnamekeygenex-function.md)  
 Generuje nową parę kluczy publicznych/prywatnych z określonym rozmiarem klucza w celu użycia silnej nazwy. Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameKeyInstall — Funkcja](strongnamekeyinstall-function.md)  
 Importuje parę kluczy publiczny/prywatny do kontenera.  Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameSignatureGeneration — Funkcja](strongnamesignaturegeneration-function.md)  
 Generuje podpis silnej nazwy dla określonego zestawu.   Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameSignatureGenerationEx — Funkcja](strongnamesignaturegenerationex-function.md)  
 Generuje podpis silnej nazwy dla określonego zestawu, na podstawie określonych flag.    Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameSignatureSize — Funkcja](strongnamesignaturesize-function.md)  
 Zwraca rozmiar sygnatury silnej nazwy. Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameSignatureVerification — Funkcja](strongnamesignatureverification-function.md)  
 Pobiera wartość wskazującą, czy manifest zestawu w podanej ścieżce zawiera sygnaturę silnej nazwy, która jest sprawdzana według określonych flag. Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameSignatureVerificationEx — Funkcja](strongnamesignatureverificationex-function.md)  
 Pobiera wartość wskazującą, czy manifest zestawu w podanej ścieżce zawiera podpis silnej nazwy.  Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameSignatureVerificationFromImage — Funkcja](strongnamesignatureverificationfromimage-function.md)  
 Sprawdza, czy zestaw, który został już zamapowany na pamięć, jest prawidłowy dla skojarzonego klucza publicznego. Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameTokenFromAssembly — Funkcja](strongnametokenfromassembly-function.md)  
 Tworzy token silnej nazwy z określonego pliku zestawu.  Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameTokenFromAssemblyEx — Funkcja](strongnametokenfromassemblyex-function.md)  
 Tworzy token silnej nazwy z określonego pliku zestawu i zwraca klucz publiczny. Przestarzałe, począwszy od .NET Framework 4.  
  
 [StrongNameTokenFromPublicKey — Funkcja](strongnametokenfrompublickey-function.md)  
 Pobiera token reprezentujący klucz publiczny. Przestarzałe, począwszy od .NET Framework 4.  
  
 [PublicKeyBlob — Struktura](publickeyblob-structure.md)  
 Reprezentuje klucz publiczny pary kluczy publiczny/prywatny w formacie binarnym.  
  
## <a name="see-also"></a>Zobacz także

- [ICLRStrongName — Interfejs](../hosting/iclrstrongname-interface.md)
- [Niezarządzana dokumentacja interfejsu API](../index.md)
