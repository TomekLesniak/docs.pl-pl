---
title: Zarządzanie zależnościami w programie .NET Core
description: Wyjaśnia, jak zarządzać zależnościami projektu dla aplikacji .NET Core.
no-loc:
- dotnet add package
- dotnet remove package
- dotnet list package
ms.topic: how-to
ms.date: 02/25/2020
ms.openlocfilehash: 2aeedb56f774b51076764c2772eb02b2fa095d92
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062863"
---
# <a name="manage-dependencies-in-net-core-applications"></a>Zarządzanie zależnościami w aplikacjach .NET Core

W tym artykule wyjaśniono, jak dodawać i usuwać zależności, edytując plik projektu lub korzystając z interfejsu wiersza polecenia.

## <a name="the-packagereference-element"></a>\<PackageReference>Element

`<PackageReference>`Element pliku projektu ma następującą strukturę:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" />
```

Ten `Include` atrybut określa identyfikator pakietu, który ma zostać dodany do projektu. Ten `Version` atrybut określa wersję do pobrania. Wersje są określone jako [reguły wersji programu NuGet](/nuget/create-packages/dependency-versions#version-ranges).

> [!NOTE]
> Jeśli nie znasz składni pliku projektu, zapoznaj się z dokumentacją [projektu programu MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference) , aby uzyskać więcej informacji.

Użyj warunków, aby dodać zależność, która jest dostępna tylko w konkretnym miejscu docelowym, jak pokazano w następującym przykładzie:

```xml
<PackageReference Include="PACKAGE_ID" Version="PACKAGE_VERSION" Condition="'$(TargetFramework)' == 'netcoreapp2.1'" />
```

Zależność w poprzednim przykładzie będzie prawidłowa tylko wtedy, gdy kompilacja ma miejsce dla danego elementu docelowego. `$(TargetFramework)`W warunku jest właściwość programu MSBuild, która jest ustawiana w projekcie. W przypadku najczęściej używanych aplikacji platformy .NET Core nie trzeba tego robić.

## <a name="add-a-dependency-by-editing-the-project-file"></a>Dodaj zależność, edytując plik projektu

Aby dodać zależność, Dodaj `<PackageReference>` element wewnątrz `<ItemGroup>` elementu. Można dodać do istniejącej `<ItemGroup>` lub utworzyć nową. W poniższym przykładzie zastosowano domyślny projekt aplikacji konsolowej utworzony przez `dotnet new console` :

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.EntityFrameworkCore" Version="3.1.2" />
  </ItemGroup>

</Project>
```

## <a name="add-a-dependency-by-using-the-cli"></a>Dodawanie zależności przy użyciu interfejsu wiersza polecenia

Aby dodać zależność, uruchom [dotnet add package](dotnet-add-package.md) polecenie, jak pokazano w następującym przykładzie:

```dotnetcli
dotnet add package Microsoft.EntityFrameworkCore
```

## <a name="remove-a-dependency-by-editing-the-project-file"></a>Usuń zależność, edytując plik projektu

Aby usunąć zależność, Usuń jej `<PackageReference>` element z pliku projektu.

## <a name="remove-a-dependency-by-using-the-cli"></a>Usuwanie zależności przy użyciu interfejsu wiersza polecenia

Aby usunąć zależność, uruchom [dotnet remove package](dotnet-remove-package.md) polecenie, jak pokazano w następującym przykładzie:

```dotnetcli
dotnet remove package Microsoft.EntityFrameworkCore
```

## <a name="see-also"></a>Zobacz także

* [Odwołania do pakietu w plikach projektu](../project-sdk/msbuild-props.md#reference-properties-and-items)
* [dotnet list packagedotyczące](dotnet-list-package.md)
