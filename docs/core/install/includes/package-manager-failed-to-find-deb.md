---
ms.openlocfilehash: 9d4c031eda291b0a8832c824789efdffe4084926
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/30/2020
ms.locfileid: "89132950"
---

Jeśli zostanie wyświetlony komunikat o błędzie podobny do następującego: **nie można znaleźć pakietu {servicecore-Package}** lub nie można **zainstalować niektórych pakietów**, uruchom następujące polecenia.

W poniższym zestawie poleceń znajdują się dwa symbole zastępcze.

- `{dotnet-package}`\
Reprezentuje pakiet .NET Core, który instalujesz, na przykład `aspnetcore-runtime-3.1` . Ta wartość jest używana w `sudo apt-get install` poniższym poleceniu.

- `{os-version}`\
Oznacza to, że wersja systemu Linux jest włączona. Ta wartość jest używana w `wget` poniższym poleceniu.

Najpierw spróbuj wyczyszczenie listy pakietów:

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

Następnie spróbuj ponownie zainstalować platformę .NET Core. Jeśli to nie zadziała, można uruchomić instalację ręczną przy użyciu następujących poleceń:
