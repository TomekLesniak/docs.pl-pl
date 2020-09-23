---
title: -resource
ms.date: 03/13/2018
helpviewer_keywords:
- /resource compiler option [Visual Basic]
- -resource compiler option [Visual Basic]
- /res compiler option [Visual Basic]
- res compiler option [Visual Basic]
- -res compiler option [Visual Basic]
- resource compiler option [Visual Basic]
ms.assetid: eee2f227-91f2-4f2b-a9d6-1c51c5320858
ms.openlocfilehash: 726f3dd179aedb39b578c8580c9632182af2d5e0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085129"
---
# <a name="-resource-visual-basic"></a>-Resource (Visual Basic)

Osadza zasób zarządzany w zestawie.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-resource:filename[,identifier[,public|private]]  
```

lub  

```console
-res:filename[,identifier[,public|private]]  
```  
  
## <a name="arguments"></a>Argumenty  
  
|Termin|Definicja|  
|---|---|  
|`filename`|Wymagany. Nazwa pliku zasobu do osadzenia w pliku wyjściowym. Domyślnie jest on `filename` publiczny w zestawie. Nazwa pliku należy ująć w cudzysłów (""), jeśli zawiera spację.|  
|`identifier`|Opcjonalny. Nazwa logiczna zasobu; Nazwa użyta do załadowania. Wartość domyślna to nazwa pliku. Opcjonalnie można określić, czy zasób jest publiczny, czy prywatny w manifeście zestawu, tak jak w przypadku następujących: `-res:filename.res, myname.res, public`|  
  
## <a name="remarks"></a>Uwagi  

 Służy `-linkresource` do łączenia zasobu z zestawem bez umieszczania pliku zasobów w pliku wyjściowym.  
  
 Jeśli `filename` jest .NET Framework utworzony plik zasobów, na przykład przez [Resgen.exe (Generator plików zasobów)](../../../framework/tools/resgen-exe-resource-file-generator.md) lub w środowisku deweloperskim, dostęp do niego można uzyskać za pomocą elementów członkowskich w <xref:System.Resources> przestrzeni nazw (Zobacz, <xref:System.Resources.ResourceManager> Aby uzyskać więcej informacji). Aby uzyskać dostęp do wszystkich innych zasobów w czasie wykonywania, należy użyć jednej z następujących metod: <xref:System.Reflection.Assembly.GetManifestResourceInfo%2A> , <xref:System.Reflection.Assembly.GetManifestResourceNames%2A> , lub <xref:System.Reflection.Assembly.GetManifestResourceStream%2A> .  
  
 Krótka forma `-resource` to `-res` .  
  
 Aby uzyskać informacje na temat sposobu ustawiania `-resource` w środowisku IDE programu Visual Studio, zobacz [Zarządzanie zasobami aplikacji (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
## <a name="example"></a>Przykład  

 Poniższy kod kompiluje `In.vb` i dołącza plik zasobów `Rf.resource` .  
  
```console
vbc -res:rf.resource in.vb  
```  
  
## <a name="see-also"></a>Zobacz także

- [Kompilator wiersza polecenia Visual Basic](index.md)
- [-win32resource](win32resource.md)
- [-linkresource — (Visual Basic)](linkresource.md)
- [-Target (Visual Basic)](target.md)
- [Przykłady kompilacji — wiersze poleceń](sample-compilation-command-lines.md)
