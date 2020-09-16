---
title: Schemat ustawień aplikacji
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: a67689bd9757f7586881fd910ef6103b1dffeab8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90550452"
---
# <a name="app-settings-schema"></a><span data-ttu-id="24aa7-102">Schemat ustawień aplikacji</span><span class="sxs-lookup"><span data-stu-id="24aa7-102">App Settings schema</span></span>

<span data-ttu-id="24aa7-103">Zawiera niestandardowe ustawienia aplikacji, takie jak ścieżki plików, adresy URL usług sieci Web XML lub inne niestandardowe informacje o konfiguracji dla aplikacji.</span><span class="sxs-lookup"><span data-stu-id="24aa7-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)

| <span data-ttu-id="24aa7-104">Element</span><span class="sxs-lookup"><span data-stu-id="24aa7-104">Element</span></span> | <span data-ttu-id="24aa7-105">Opis</span><span class="sxs-lookup"><span data-stu-id="24aa7-105">Description</span></span> |
| ------- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="24aa7-106">Zawiera **\<add>** **\<clear>** Tagi, i **\<remove>** do kontrolowania ustawień aplikacji.</span><span class="sxs-lookup"><span data-stu-id="24aa7-106">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="24aa7-107">Ma opcjonalny atrybut **pliku** .</span><span class="sxs-lookup"><span data-stu-id="24aa7-107">Has an optional **file** attribute.</span></span> |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="24aa7-108">Definiuje ustawienie.</span><span class="sxs-lookup"><span data-stu-id="24aa7-108">Defines a setting.</span></span> <span data-ttu-id="24aa7-109">Element podrzędny **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="24aa7-109">Child of **\<appSettings>**.</span></span> <span data-ttu-id="24aa7-110">Wymaga atrybutów **klucza** i **wartości** .</span><span class="sxs-lookup"><span data-stu-id="24aa7-110">Requires **key** and **value** attributes.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="24aa7-111">Czyści wszystkie ustawienia.</span><span class="sxs-lookup"><span data-stu-id="24aa7-111">Clears all settings.</span></span> <span data-ttu-id="24aa7-112">Element podrzędny **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="24aa7-112">Child of **\<appSettings>**.</span></span> <span data-ttu-id="24aa7-113">Nie ma atrybutów.</span><span class="sxs-lookup"><span data-stu-id="24aa7-113">Has no attributes.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="24aa7-114">Usuwa ustawienie.</span><span class="sxs-lookup"><span data-stu-id="24aa7-114">Removes a setting.</span></span> <span data-ttu-id="24aa7-115">Element podrzędny **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="24aa7-115">Child of **\<appSettings>**.</span></span> <span data-ttu-id="24aa7-116">Wymaga atrybutu **klucza** .</span><span class="sxs-lookup"><span data-stu-id="24aa7-116">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="24aa7-117">\<appSettings>, element</span><span class="sxs-lookup"><span data-stu-id="24aa7-117">\<appSettings> element</span></span>

<span data-ttu-id="24aa7-118">Ten element zawiera **\<add>** **\<clear>** Tagi,, i **\<remove>** do kontrolowania ustawień aplikacji.</span><span class="sxs-lookup"><span data-stu-id="24aa7-118">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="24aa7-119">Definiuje opcjonalny atrybut dla **pliku**.</span><span class="sxs-lookup"><span data-stu-id="24aa7-119">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="24aa7-120">\<add>, element</span><span class="sxs-lookup"><span data-stu-id="24aa7-120">\<add> element</span></span>

<span data-ttu-id="24aa7-121">Dodaje niestandardowe ustawienie aplikacji jako parę nazwa/wartość do kolekcji ustawień aplikacji.</span><span class="sxs-lookup"><span data-stu-id="24aa7-121">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="24aa7-122">Definiuje atrybuty **klucza** i **wartości**.</span><span class="sxs-lookup"><span data-stu-id="24aa7-122">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="24aa7-123">\<clear>, element</span><span class="sxs-lookup"><span data-stu-id="24aa7-123">\<clear> element</span></span>

<span data-ttu-id="24aa7-124">Usuwa wszystkie odwołania do dziedziczonych ustawień aplikacji niestandardowych i zezwala tylko na odwołania, które są dodawane przez **\<add>** elementy po **\<clear>** elemencie.</span><span class="sxs-lookup"><span data-stu-id="24aa7-124">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="24aa7-125">Nie definiuje żadnych atrybutów.</span><span class="sxs-lookup"><span data-stu-id="24aa7-125">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="24aa7-126">\<remove>, element</span><span class="sxs-lookup"><span data-stu-id="24aa7-126">\<remove> element</span></span>

<span data-ttu-id="24aa7-127">Usuwa odwołanie do dziedziczonego ustawienia aplikacji niestandardowej z kolekcji ustawień aplikacji.</span><span class="sxs-lookup"><span data-stu-id="24aa7-127">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="24aa7-128">Definiuje atrybut dla **klucza**.</span><span class="sxs-lookup"><span data-stu-id="24aa7-128">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="24aa7-129">Przykład</span><span class="sxs-lookup"><span data-stu-id="24aa7-129">Example</span></span>

<span data-ttu-id="24aa7-130">W poniższym przykładzie przedstawiono zewnętrzny plik ustawień aplikacji (*custom.config*) definiujący niestandardowe ustawienie aplikacji:</span><span class="sxs-lookup"><span data-stu-id="24aa7-130">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="24aa7-131">Poniższy przykład przedstawia plik konfiguracji aplikacji, który używa ustawienia w pliku ustawień zewnętrznych i ustawia własne ustawienie aplikacji:</span><span class="sxs-lookup"><span data-stu-id="24aa7-131">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="24aa7-132">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="24aa7-132">See also</span></span>

- [<span data-ttu-id="24aa7-133">Przegląd ustawień aplikacji</span><span class="sxs-lookup"><span data-stu-id="24aa7-133">Application Settings Overview</span></span>](/dotnet/desktop/winforms/advanced/application-settings-overview)
- [<span data-ttu-id="24aa7-134">Architektura ustawień aplikacji</span><span class="sxs-lookup"><span data-stu-id="24aa7-134">Application Settings Architecture</span></span>](/dotnet/desktop/winforms/advanced/application-settings-architecture)
