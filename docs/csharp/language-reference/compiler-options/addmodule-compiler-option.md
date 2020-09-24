---
description: -addmodule (opcje kompilatora C#)
title: -addmodule (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
ms.openlocfilehash: ec72fc76b3d550029b1286f64b8f86e69e721468
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150573"
---
# <a name="-addmodule-c-compiler-options"></a>-addmodule (opcje kompilatora C#)

Ta opcja dodaje moduł, który został utworzony za pomocą elementu docelowego: przełączenie modułu do bieżącej kompilacji.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a>Argumenty  

 `file`, `file2`  
 Plik wyjściowy zawierający metadane. Plik nie może zawierać manifestu zestawu. Aby zaimportować więcej niż jeden plik, oddziel nazwy plików przecinkami lub średnikami.  
  
## <a name="remarks"></a>Uwagi  

 Wszystkie moduły dodane za pomocą polecenia **-addmodule** muszą znajdować się w tym samym katalogu co plik wyjściowy w czasie wykonywania. Oznacza to, że można określić moduł w dowolnym katalogu w czasie kompilacji, ale moduł musi znajdować się w katalogu aplikacji w czasie wykonywania. Jeśli moduł nie znajduje się w katalogu aplikacji w czasie wykonywania, otrzymasz <xref:System.TypeLoadException> .  
  
 `file` nie może zawierać zestawu. Na przykład jeśli plik wyjściowy został utworzony za pomocą [elementu-target: module](./target-module-compiler-option.md), jego metadane można zaimportować za pomocą polecenia **-addmodule**.  
  
 Jeśli plik wyjściowy został utworzony z opcją **-Target** inną niż **-target: module**, nie można zaimportować jej metadanych przy użyciu parametru **-addmodule** , ale można go zaimportować z [-Reference](./reference-compiler-option.md).  
  
 Ta opcja kompilatora jest niedostępna w programie Visual Studio; projekt nie może odwoływać się do modułu. Ponadto nie można programowo zmienić tej opcji kompilatora.  
  
## <a name="example"></a>Przykład  

 Kompiluj plik źródłowy `input.cs` i Dodaj metadane z `metad1.netmodule` i `metad2.netmodule` do produkcji `out.exe` :  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
- [Zestawy wieloplikowe](../../../framework/app-domains/multifile-assemblies.md)
- [Instrukcje: kompilowanie zestawu wieloplikowego](../../../framework/app-domains/build-multifile-assembly.md)
