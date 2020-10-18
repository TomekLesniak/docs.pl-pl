---
title: 'Nie można wyemitować zestawu: <error message>'
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: c088f273c100b1a7eefcf74047865093f378e970
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161663"
---
# <a name="bc30145-unable-to-emit-assembly-error-message"></a>BC30145: nie można wyemitować zestawu: \<error message>

Kompilator Visual Basic wywołuje konsolidator zestawu (*Al.exe*, znany również jako ALink) w celu wygenerowania zestawu z manifestem, a konsolidator raportuje błąd w fazie emisji tworzenia zestawu.

**Identyfikator błędu:** BC30145

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

1. Sprawdź cytowany komunikat o błędzie i zapoznaj się z tematem [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) w celu uzyskania dalszych wyjaśnień i porad.

2. Spróbuj podpisać zestaw ręcznie przy użyciu [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) lub [Sn.exe (narzędzia silnej nazwy)](../../../framework/tools/sn-exe-strong-name-tool.md).

3. Jeśli błąd będzie się powtarzać, Zbierz informacje o okolicznościach i powiadom usługi pomocy technicznej firmy Microsoft.

### <a name="to-sign-the-assembly-manually"></a>Aby ręcznie podpisać zestaw

1. Użyj [Sn.exe (Narzędzie silnej nazwy)](../../../framework/tools/sn-exe-strong-name-tool.md), aby utworzyć plik pary kluczy publicznych/prywatnych.

   Ten plik ma rozszerzenie *. snk* .

2. Usuń odwołanie COM, które generuje błąd z projektu.

3. Otwórz [wiersz polecenia dla deweloperów dla programu Visual Studio](../../../framework/tools/developer-command-prompt-for-vs.md).

   W systemie Windows 10 wprowadź **wiersz polecenia programisty** w polu wyszukiwania na pasku zadań. Następnie wybierz pozycję **wiersz polecenia dla deweloperów dla programu VS 2017** z listy wyników.

4. Zmień katalog na katalog, w którym chcesz umieścić otokę zestawu.

5. Wprowadź następujące polecenie:

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   Przykładem rzeczywistego polecenia, które można wprowadzić:

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > Jeśli ścieżka lub plik zawiera spacje, należy użyć podwójnych cudzysłowów.

6. W programie Visual Studio Dodaj odwołanie do zestawu .NET do pliku, który właśnie został utworzony.

## <a name="see-also"></a>Zobacz też

- [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Sn.exe (Narzędzie silnej nazwy)](../../../framework/tools/sn-exe-strong-name-tool.md)
- [Instrukcje: Tworzenie pary kluczy Public-Private](../../../standard/assembly/create-public-private-key-pair.md)
- [Porozmawiaj z nami](/visualstudio/ide/feedback-options)
