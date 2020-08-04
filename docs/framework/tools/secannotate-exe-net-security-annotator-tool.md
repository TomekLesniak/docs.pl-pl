---
title: SecAnnotate.exe (Narzędzie adnotacji dotyczące zabezpieczeń w programach .NET)
description: Użyj SecAnnotate.exe, narzędzia do dodawania adnotacji zabezpieczeń platformy .NET. Zidentyfikuj fragmenty SecurityCritical i SecuritySafeCritical jednego lub kilku zestawów.
ms.date: 03/30/2017
helpviewer_keywords:
- SecAnnotate.exe
- Security Annotator tool
ms.assetid: 8104d208-7813-4a1d-8a75-58f9a7bcb8c9
ms.openlocfilehash: 440ad39f1afb54ad517bc73f05d1e60748b7b520
ms.sourcegitcommit: b4f8849c47c1a7145eb26ce68bc9f9976e0dbec3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2020
ms.locfileid: "87517220"
---
# <a name="secannotateexe-net-security-annotator-tool"></a>SecAnnotate.exe (Narzędzie adnotacji dotyczące zabezpieczeń w programach .NET)
Narzędzie do dodawania adnotacji zabezpieczeń .NET (SecAnnotate.exe) jest aplikacją wiersza polecenia, która identyfikuje `SecurityCritical` i `SecuritySafeCritical` części jednego lub kilku zestawów.  
  
 Rozszerzenie programu Visual Studio, [Dodawanie adnotacji do zabezpieczeń](https://marketplace.visualstudio.com/items?itemName=sheldonb.SecurityAnnotator), udostępnia graficzny interfejs użytkownika do SecAnnotate.exe i umożliwia uruchamianie narzędzia z programu Visual Studio.  
  
 To narzędzie jest instalowane automatycznie z programem Visual Studio. Aby uruchomić narzędzie, użyj wiersz polecenia dla deweloperów dla programu Visual Studio (lub wiersza polecenia programu Visual Studio w systemie Windows 7). Aby uzyskać więcej informacji, zobacz [wiersza polecenia](developer-command-prompt-for-vs.md).  
  
 W wierszu polecenia wpisz następujące polecenie, gdzie *Parametry* są opisane w poniższej sekcji, a *zestawy* składają się z co najmniej jednej nazwy zestawu oddzielonej pustymi danymi:  
  
## <a name="syntax"></a>Składnia  
  
```console  
SecAnnotate.exe [parameters] [assemblies]  
```  
  
## <a name="parameters"></a>Parametry  
  
|Opcja|Opis|  
|------------|-----------------|  
|`/a`<br /><br /> lub<br /><br /> `/showstatistics`|Pokazuje statystykę użycia przezroczystości w analizowanych w ten sposób zestawach.|  
|`/d:`*katalog*<br /><br /> lub<br /><br /> `/referencedir:`*katalog*|Określa katalog, w którym mają być wyszukiwanie zależne zestawy podczas oznaczania adnotacjami.|  
|`/i`<br /><br /> lub<br /><br /> `/includesignatures`|Umieszcza rozszerzone informacje podpisu w pliku raportu oznaczania adnotacjami.|  
|`/n`<br /><br /> lub<br /><br /> `/nogac`|Pomija wyszukiwanie zestawów, których dotyczą odwołania, w globalnej pamięci podręcznej zestawów.|  
|`/o:`*output.xml*<br /><br /> lub<br /><br /> `/out:`*output.xml*|Określa wyjściowy plik adnotacji.|  
|`/p:`*maxpasses*<br /><br /> lub<br /><br /> `/maximumpasses:`*maxpasses*|Określa maksymalną liczbę adnotacji, które można przekazać do zestawów przed zatrzymaniem generowania nowych adnotacji.|  
|`/q`<br /><br /> lub<br /><br /> `/quiet`|Określa tryb cichy, w którym moduł oznaczający adnotacjami nie wyświetla komunikatów o stanie, ale tylko informacje o błędach.|  
|`/r:`*zestaw*<br /><br /> lub<br /><br /> `/referenceassembly:`*zestaw*|Dołącza określony zestaw podczas rozpoznawania zestawów zależnych w trakcie oznaczania adnotacjami. Zestawy, do których występują odwołania, otrzymują większy priorytet niż zestawy znajdujące się w ścieżce odwołania.|  
|`/s:`*reguła*<br /><br /> lub<br /><br /> `/suppressrule:`*reguła*|Pomija uruchamianie określonych reguł przezroczystości w zestawach wejściowych.|  
|`/t`<br /><br /> lub<br /><br /> `/forcetransparent`|Wymusza, aby narzędzie Annotator traktowało wszystkie zestawy, które nie mają adnotacji przezroczystości, tak jakby były całkowicie przezroczyste.|  
|`/t`:*zestaw*<br /><br /> lub<br /><br /> `/forcetransparent`:*zestaw*|Wymusza przezroczystość danego zestawu, niezależnie od jego bieżących adnotacji na poziomie zestawu.|  
|||  
|`/v`<br /><br /> lub<br /><br /> `/verify`|Sprawdza tylko, czy adnotacje zestawu są poprawne; nie podejmuje próby wykonania wielu przebiegów w celu znalezienia wszystkich wymaganych adnotacji, jeśli zestaw tego nie weryfikuje.|  
|`/x`<br /><br /> lub<br /><br /> `/verbose`|Określa pełne dane wyjściowe podczas oznaczania adnotacjami.|  
|`/y:`*katalog*<br /><br /> lub<br /><br /> `/symbolpath:`*katalog*|Uwzględnia określony katalog podczas wyszukiwania plików symboli w trakcie oznaczania adnotacjami.|  
  
## <a name="remarks"></a>Uwagi  
 Parametry i zestawy można także podać w pliku odpowiedzi, który jest określany w wierszu polecenia i poprzedzany znakiem (@). Każdy wiersz w pliku odpowiedzi musi zawierać pojedynczy parametr lub nazwę zestawu.  
  
 Aby uzyskać więcej informacji na temat adnotacji zabezpieczeń .NET, zobacz wpis [przy użyciu SecAnnotate, aby analizować zestawy pod kątem naruszeń przejrzystości w blogu dotyczącym](https://docs.microsoft.com/archive/blogs/shawnfa/using-secannotate-to-analyze-your-assemblies-for-transparency-violations-an-example) zabezpieczeń platformy .NET.  
  
## <a name="examples"></a>Przykłady
