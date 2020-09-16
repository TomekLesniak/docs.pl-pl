---
title: Narzędzie klienta usługi danych WCF (DataSvcUtil.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 600cb9a4f91ff2051f60ee86d4cb80cc5b404c61
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544300"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>Narzędzie klienta usługi danych WCF (DataSvcUtil.exe)

DataSvcUtil.exe to narzędzie wiersza polecenia zapewniane przez Usługi danych programu WCF, które korzysta z kanału informacyjnego protokołu Open Data Protocol (OData) i generuje klasy usługi danych klienta, które są konieczne w celu uzyskania dostępu do usługi danych z .NET Framework aplikacji klienckiej. To narzędzie może generować klasy danych przy użyciu następujących źródeł metadanych:

- Główny identyfikator URI usługi danych. Narzędzie żąda dokumentu metadanych usługi, który opisuje model danych uwidoczniony przez usługę danych. Aby uzyskać więcej informacji, zobacz [AtomPub (RFC5023)](https://tools.ietf.org/html/rfc5023#section-8).

- Plik modelu danych (. csdl) zdefiniowany przy użyciu języka definicji schematu koncepcyjnego (CSDL), zgodnie z definicją w temacie [ \[ MC-CSDL \] : Specification format pliku definicji schematu](/openspecs/windows_protocols/mc-csdl/c03ad8c3-e8b7-4306-af96-a9e52bb3df12) .

- Plik. edmx utworzony przy użyciu narzędzi Entity Data Model, które są dostarczane z Entity Framework. Aby uzyskać więcej informacji, zobacz sekcję [ \[ MC-EDMX \] : Entity Data Model dla specyfikacji formatu pakietu Data Services](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16) .

Aby uzyskać więcej informacji, zobacz [jak: ręczne generowanie klas usługi danych klienta](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).

Narzędzie DataSvcUtil.exe jest zainstalowane w katalogu .NET Framework. W wielu przypadkach znajduje się to w *C:\Windows\Microsoft.NET\Framework\v4.0*. W przypadku systemów 64-bitowych ten program znajduje się w *C:\Windows\Microsoft.NET\Framework64\v4.0*. Możesz również uzyskać dostęp do narzędzia DataSvcUtil.exe z wiersz polecenia dla deweloperów dla programu Visual Studio.

## <a name="syntax"></a>Składnia

```console
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a>Parametry

|Opcja|Opis|
|------------|-----------------|
|`/dataservicecollection`|Określa, że jest również generowany kod wymagany do powiązania obiektów z kontrolkami.|
|`/help`<br /><br /> -lub-<br /><br /> `/?`|Wyświetla składnię polecenia i opcje narzędzia.|
|`/in:` *\<file>*|Określa plik CSDL lub edmx lub katalog, w którym znajduje się plik.|
|`/language:`[VB&#124;CSharp]|Określa język generowanych plików kodu źródłowego. Język domyślny języka C#.|
|`/nologo`|Pomija wyświetlanie komunikatu o prawach autorskich.|
|`/out:` *\<file>*|Określa nazwę pliku kodu źródłowego, który zawiera wygenerowane klasy usługi danych klienta.|
|`/uri:` *\<string>*|Identyfikator URI źródła danych OData.|
|`/version:`[1,0&#124;2,0]|Określa najwyższą zaakceptowaną wersję usługi OData. Wersja jest określana na podstawie `DataServiceVersion` atrybutu elementu DataService w metadanych zwracanej usługi danych. Aby uzyskać więcej informacji, zobacz [przechowywanie wersji usługi danych](data-service-versioning-wcf-data-services.md). Po określeniu `/dataservicecollection` parametru należy również określić, `/version:2.0` Aby włączyć powiązanie danych.|

## <a name="see-also"></a>Zobacz także

- [Generowanie biblioteki klienta usługi danych](generating-the-data-service-client-library-wcf-data-services.md)
- [Instrukcje: Dodawanie odwołania do usługi danych](how-to-add-a-data-service-reference-wcf-data-services.md)
