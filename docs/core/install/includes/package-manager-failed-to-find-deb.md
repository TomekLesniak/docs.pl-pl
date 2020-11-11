---
ms.openlocfilehash: aba7b473af7685aa45f7e093a2f75311687593df
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506984"
---

Jeśli zostanie wyświetlony komunikat o błędzie podobny do następującego: **nie można znaleźć pakietu {dotnet-Package}** lub nie można **zainstalować niektórych pakietów** , uruchom następujące polecenia.

W poniższym zestawie poleceń znajdują się dwa symbole zastępcze.

- `{dotnet-package}`\
Reprezentuje pakiet .NET, który instalujesz, na przykład `aspnetcore-runtime-3.1` . Ta wartość jest używana w poniższym `sudo apt-get install` poleceniu.

- `{os-version}`\
Oznacza to, że wersja systemu Linux jest włączona. Ta wartość jest używana w `wget` poniższym poleceniu.

Najpierw spróbuj wyczyszczenie listy pakietów:

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
```

Następnie spróbuj ponownie zainstalować platformę .NET. Jeśli to nie zadziała, można uruchomić instalację ręczną przy użyciu następujących poleceń:
