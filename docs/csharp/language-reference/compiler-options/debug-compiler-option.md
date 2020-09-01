---
description: -Debug (opcje kompilatora C#)
title: -Debug (opcje kompilatora C#)
ms.date: 07/20/2015
f1_keywords:
- /debug
helpviewer_keywords:
- debug compiler option [C#]
- -debug compiler option [C#]
- /debug compiler option [C#]
ms.assetid: e2b48c07-01bc-45cc-a52c-92e9085eb969
ms.openlocfilehash: 164530a5ec99e7d5b9f34dbcdfb18d80f3102308
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125920"
---
# <a name="-debug-c-compiler-options"></a>-Debug (opcje kompilatora C#)
Opcja **-Debug** powoduje, że kompilator generuje informacje o debugowaniu i umieszcza je w pliku wyjściowym lub plikach.  
  
## <a name="syntax"></a>Składnia  
  
```console  
-debug[+ | -]  
-debug:{full | pdbonly}  
```  
  
## <a name="arguments"></a>Argumenty  
 `+` &#124; `-`  
 Określenie `+` lub tylko **debugowanie**powoduje, że kompilator generuje informacje o debugowaniu i umieszcza je w bazie danych programu (plik. pdb). Określenie `-` , która obowiązuje, jeśli nie określono **-Debug**nie powoduje, że żadne informacje debugowania nie zostaną utworzone.  
  
 `full` &#124; `pdbonly`  
 Określa typ informacji o debugowaniu generowanych przez kompilator. Pełny argument, który obowiązuje, jeśli nie określono **-Debug: pdbonly**, umożliwia dołączenie debugera do uruchomionego programu. Określenie pdbonly umożliwia debugowanie kodu źródłowego, gdy program jest uruchamiany w debugerze, ale wyświetla tylko asembler, gdy uruchomiony program zostanie dołączony do debugera.  
  
## <a name="remarks"></a>Uwagi  
 Użyj tej opcji, aby utworzyć kompilacje debugowania. Jeśli nie określono polecenia **-Debug**, **-Debug +** lub **-Debug: Full** , nie będzie możliwe debugowanie pliku wyjściowego programu.  
  
 Jeśli używasz **-Debug: Full**, pamiętaj, że występuje pewien wpływ na szybkość i rozmiar kodu zoptymalizowanego pod kątem JIT oraz niewielki wpływ na jakość kodu z **-Debug: Full**. Zalecamy **debugowanie: pdbonly** lub brak pliku PDB do generowania kodu wydania.  
  
> [!NOTE]
> Jedna różnica między **debugowaniem: pdbonly** i **-Debug: Full** to the **-Debug: Full** kompilator emituje <xref:System.Diagnostics.DebuggableAttribute> , który jest używany do informowania kompilatora JIT, że dostępne są informacje debugowania. W związku z tym zostanie wyświetlony komunikat o błędzie, jeśli kod zawiera wartość <xref:System.Diagnostics.DebuggableAttribute> false, jeśli używasz **-Debug: Full**.  
  
 Aby uzyskać więcej informacji na temat konfigurowania wydajności debugowania aplikacji, zobacz [ułatwianie debugowania obrazu](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
 Aby zmienić lokalizację pliku. pdb, zobacz [-PDB (opcje kompilatora C#)](./pdb-compiler-option.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję kompilatora w środowisku programowania Visual Studio  
  
1. Otwórz stronę **Właściwości** projektu.  
  
2. Kliknij stronę właściwości **kompilacja** .  
  
3. Kliknij przycisk **Zaawansowane** .  
  
4. Zmodyfikuj właściwość **informacji o debugowaniu** .  
  
 Aby uzyskać informacje na temat sposobu, w jaki można programowo ustawić tę opcję kompilatora, zobacz <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DebugSymbols%2A> .  
  
## <a name="example"></a>Przykład  
 Umieść informacje o debugowaniu w pliku wyjściowym `app.pdb` :  
  
```console  
csc -debug -pdb:app.pdb test.cs  
```  
  
## <a name="see-also"></a>Zobacz też

- [Opcje kompilatora C#](./index.md)
- [Zarządzanie właściwościami projektów i rozwiązań](/visualstudio/ide/managing-project-and-solution-properties)
