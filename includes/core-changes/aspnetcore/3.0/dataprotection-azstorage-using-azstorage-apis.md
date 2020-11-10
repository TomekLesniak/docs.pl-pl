---
ms.openlocfilehash: f6e4c3d5c5fd020562e48515554136e0f8b6785c
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440427"
---
### <a name="data-protection-dataprotectionblobs-uses-new-azure-storage-apis"></a>Ochrona danych: dataprotection. obiekty blob używają nowych interfejsów API usługi Azure Storage

`Azure.Extensions.AspNetCore.DataProtection.Blobs` zależy od [bibliotek usługi Azure Storage](https://github.com/Azure/azure-storage-net). Te biblioteki zmieniły swoje zestawy, pakiety i przestrzenie nazw. Począwszy od ASP.NET Core 3,0, program `Azure.Extensions.AspNetCore.DataProtection.Blobs` używa nowych `Azure.Storage.` prefiksów interfejsów API i pakietów.

Pytania dotyczące interfejsów API usługi Azure Storage można używać <https://github.com/Azure/azure-storage-net> . Aby zapoznać się z omówieniem tego problemu, zobacz [dotnet/aspnetcore # 19570](https://github.com/dotnet/aspnetcore/issues/19570).

#### <a name="version-introduced"></a>Wprowadzona wersja

3.0

#### <a name="old-behavior"></a>Stare zachowanie

Pakiet przywoływany do `WindowsAzure.Storage` pakietu NuGet.
Pakiet odwołuje się do `Microsoft.Azure.Storage.Blob` pakietu NuGet.

#### <a name="new-behavior"></a>Nowe zachowanie

Pakiet odwołuje się do `Azure.Storage.Blob` pakietu NuGet.

#### <a name="reason-for-change"></a>Przyczyna zmiany

Ta zmiana umożliwia `Azure.Extensions.AspNetCore.DataProtection.Blobs` Migrowanie do zalecanych pakietów usługi Azure Storage.

#### <a name="recommended-action"></a>Zalecana akcja

Jeśli nadal potrzebujesz użyć starszych interfejsów API usługi Azure Storage z ASP.NET Core 3,0, Dodaj bezpośrednią zależność do pakietu [windowsazure. Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) lub [Microsoft. Azure. Storage](https://www.nuget.org/packages/Microsoft.Azure.Storage.Blob/). Ten pakiet można zainstalować obok nowych `Azure.Storage` interfejsów API.

W wielu przypadkach uaktualnienie obejmuje jedynie zmianę `using` instrukcji w celu użycia nowych przestrzeni nazw:

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
- using Microsoft.Azure.Storage;
- using Microsoft.Azure.Storage.Blob;
+ using Azure.Storage;
+ using Azure.Storage.Blobs;
```

#### <a name="category"></a>Kategoria

ASP.NET Core

#### <a name="affected-apis"></a>Dotyczy interfejsów API

Brak

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
