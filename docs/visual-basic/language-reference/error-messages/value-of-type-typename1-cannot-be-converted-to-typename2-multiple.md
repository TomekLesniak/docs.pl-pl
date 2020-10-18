---
title: Wartości typu „<typename1>” nie może zostać przekonwertowana na „<typename2>” (Odwołania do wielu plików)
ms.date: 07/20/2015
f1_keywords:
- vbc30961
- bc30961
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
ms.openlocfilehash: 23c051e57014d7479d1c1c522b1a8da1ead52c19
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161390"
---
# <a name="bc30961-value-of-type-typename1-cannot-be-converted-to-typename2-multiple-file-references"></a>BC30961: \<typename1> nie można przekonwertować wartości typu "" na " \<typename2> " (odwołania do wielu plików)

\<typename1>Nie można przekonwertować wartości typu "" na " \<typename2> ". Niezgodność typów może być spowodowana mieszaniem odwołania do pliku " \<filepath1> " w projekcie " \<projectname1> " z odwołaniem do pliku " \<filepath2> " w projekcie " \<projectname2> ". Jeśli oba zestawy są identyczne, spróbuj zastąpić te odwołania, aby oba odwołania były z tej samej lokalizacji.

 W sytuacji, gdy projekt składa więcej niż jedno odwołanie do zestawu, kompilator nie może zagwarantować, że jeden typ może być konwertowany na inny.

 Każde odwołanie do pliku Określa ścieżkę i nazwę pliku wyjściowego projektu (zazwyczaj jest to plik DLL). Kompilator nie może zagwarantować, że pliki wyjściowe pochodzą z tego samego źródła lub reprezentują te same wersje tego samego zestawu. W związku z tym nie może zagwarantować, że typy w różnych odwołaniach są tego samego typu, lub nawet że jeden z nich można przekonwertować na drugi.

 Można użyć jednego odwołania do pliku, Jeśli wiesz, że zestawy, do których istnieją odwołania, mają tę samą tożsamość zestawu. *Tożsamość zestawu* zawiera nazwę zestawu, wersję, klucz publiczny, jeśli istnieje, oraz kulturę. Te informacje jednoznacznie identyfikują zestaw.

 **Identyfikator błędu:** BC30961

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Jeśli zestawy, do których się odwołuje, mają tę samą tożsamość zestawu, Usuń lub Zastąp jedno z odwołań do pliku, tak że istnieje tylko jedno odwołanie do pliku.

- Jeśli zestawy, do których się odwoływano, nie mają tej samej tożsamości zestawu, a następnie Zmień kod, tak aby nie próbował skonwertować typu w jeden do typu w drugim.

## <a name="see-also"></a>Zobacz też

- [Konwersje plików w Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
- [Zarządzanie odwołaniami w projekcie](/visualstudio/ide/managing-references-in-a-project)
