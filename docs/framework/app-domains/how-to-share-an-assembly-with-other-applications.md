---
title: 'Instrukcje: udostępnianie zestawu innym aplikacjom'
description: Zobacz, jak udostępnić zestaw innym aplikacjom w programie .NET. Zestawy mogą być prywatne (domyślne) lub udostępnione. Aby udostępnić zestaw, umieść go w pamięci podręcznej GAC.
ms.date: 08/19/2019
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: 1056f8b555713d5d67488537e6c06cc457c4d312
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242542"
---
# <a name="how-to-share-an-assembly-with-other-applications"></a>Instrukcje: udostępnianie zestawu innym aplikacjom

Zestawy mogą być prywatne lub udostępnione: Domyślnie większość prostych programów składa się z zestawu prywatnego, ponieważ nie są przeznaczone do użytku przez inne aplikacje.  

W celu udostępnienia zestawu innym aplikacjom należy umieścić je w [globalnej pamięci podręcznej zestawów (GAC)](gac.md).  
  
Aby udostępnić zestaw:
  
1. Utwórz zestaw. Aby uzyskać więcej informacji, zobacz [Tworzenie zestawów](../../standard/assembly/create.md).  
  
2. Przypisz silną nazwę do zestawu. Aby uzyskać więcej informacji, zobacz [jak: podpisywanie zestawu za pomocą silnej nazwy](../../standard/assembly/sign-strong-name.md).  
  
3. Przypisz informacje o wersji do Twojego zestawu. Aby uzyskać więcej informacji, zobacz [przechowywanie wersji zestawu](../../standard/assembly/versioning.md).  
  
4. Dodaj swój zestaw do globalnej pamięci podręcznej zestawów. Aby uzyskać więcej informacji, zobacz [jak: Instalowanie zestawu w globalnej pamięci podręcznej zestawów](install-assembly-into-gac.md).  
  
5. Uzyskaj dostęp do typów zawartych w zestawie z innych aplikacji. Aby uzyskać więcej informacji, zobacz [jak: odwołanie do zestawu o silnej nazwie](../../standard/assembly/reference-strong-named.md).  
  
## <a name="see-also"></a>Zobacz też

- [Przewodnik programowania w języku C#](../../../api/index.md)
- [Koncepcje programowania (Visual Basic)](../../../api/index.md)
- [Programowanie przy użyciu zestawów](../../standard/assembly/index.md)
