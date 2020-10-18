---
title: Wymagane odwołanie do zestawu „<assemblyname>” z klasą bazową „<classname>”
ms.date: 07/20/2015
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
ms.openlocfilehash: d2fb3498219dfe3318ec418ede250de818874ba9
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162339"
---
# <a name="bc30007-reference-required-to-assembly-assemblyname-containing-the-base-class-classname"></a>BC30007: odwołanie wymagane do zestawu " \<assemblyname> " zawierającego klasę bazową " \<classname> "

Wymagane odwołanie do zestawu " \<assemblyname> " zawierającego klasę bazową " \<classname> ". Dodaj je do projektu.

 Klasa jest definiowana w bibliotece dołączanej dynamicznie (DLL) lub w zestawie, który nie jest bezpośrednio przywoływany w projekcie. Kompilator Visual Basic wymaga odwołania, aby uniknąć niejednoznaczności na wypadek, gdyby Klasa została zdefiniowana w więcej niż jednej bibliotece DLL lub zestawie.

 **Identyfikator błędu:** BC30007

## <a name="to-correct-this-error"></a>Aby poprawić ten błąd

- Dołącz nazwę nieodwołania do biblioteki DLL lub zestawu w odwołaniach do projektu.

## <a name="see-also"></a>Zobacz też

- [Zarządzanie odwołaniami w projekcie](/visualstudio/ide/managing-references-in-a-project)
- [Rozwiązywanie problemów z przerwanymi odwołaniami](/visualstudio/ide/troubleshooting-broken-references)
