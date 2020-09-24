---
title: Sekcja konfiguracji programu Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: 2d518ec03602580f3c5d00ef2901ff7d7ac1d81b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148506"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="66d6b-102">Sekcja konfiguracji programu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66d6b-102">Windows Forms Configuration Section</span></span>

<span data-ttu-id="66d6b-103">Windows Forms ustawienia konfiguracji umożliwiają aplikacji Windows Forms przechowywanie i pobieranie informacji o niestandardowych ustawieniach aplikacji, takich jak obsługa wielomonitorów, obsługa wysokiej rozdzielczości DPI i inne wstępnie zdefiniowane ustawienia konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="66d6b-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="66d6b-104">Ustawienia konfiguracji aplikacji Windows Forms są przechowywane w pliku konfiguracji aplikacji `System.Windows.Forms.ApplicationConfigurationSection` .</span><span class="sxs-lookup"><span data-stu-id="66d6b-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="66d6b-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="66d6b-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="66d6b-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="66d6b-106">Attributes and elements</span></span>

<span data-ttu-id="66d6b-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="66d6b-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="66d6b-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="66d6b-108">Attributes</span></span>

<span data-ttu-id="66d6b-109">Brak.</span><span class="sxs-lookup"><span data-stu-id="66d6b-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="66d6b-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="66d6b-110">Child elements</span></span>

<span data-ttu-id="66d6b-111">Element</span><span class="sxs-lookup"><span data-stu-id="66d6b-111">Element</span></span>  |<span data-ttu-id="66d6b-112">Opis</span><span class="sxs-lookup"><span data-stu-id="66d6b-112">Description</span></span> |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | <span data-ttu-id="66d6b-113">Dodaje klucz ustawienia konfiguracji z określoną wartością</span><span class="sxs-lookup"><span data-stu-id="66d6b-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="66d6b-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="66d6b-114">Parent elements</span></span>

<span data-ttu-id="66d6b-115">Element</span><span class="sxs-lookup"><span data-stu-id="66d6b-115">Element</span></span>  |<span data-ttu-id="66d6b-116">Opis</span><span class="sxs-lookup"><span data-stu-id="66d6b-116">Description</span></span> |
---------|---------|
[\<configuration>](../configuration-element.md) | <span data-ttu-id="66d6b-117">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66d6b-117">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="66d6b-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="66d6b-118">Remarks</span></span>

<span data-ttu-id="66d6b-119">Począwszy od .NET Framework 4,7, `<System.Windows.Forms.ApplicationConfigurationSection>` element pozwala konfigurować aplikacje Windows Forms, aby korzystać z funkcji dodanych w ostatnich wersjach .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="66d6b-119">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span>

<span data-ttu-id="66d6b-120">`<System.Windows.Forms.ApplicationConfigurationSection>`Element może zawierać jeden lub więcej elementów podrzędnych [`<add>`](windows-forms-add-configuration-element.md) , z których każda definiuje określone ustawienie konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="66d6b-120">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="66d6b-121">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="66d6b-121">See also</span></span>

- [<span data-ttu-id="66d6b-122">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="66d6b-122">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="66d6b-123">Obsługa wysokiej rozdzielczości DPI w Windows Forms</span><span class="sxs-lookup"><span data-stu-id="66d6b-123">High DPI Support in Windows Forms</span></span>](/dotnet/desktop/winforms/high-dpi-support-in-windows-forms)
