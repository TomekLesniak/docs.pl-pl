---
title: Sekcja konfiguracji programu Windows Forms
ms.date: 04/07/2017
ms.assetid: 6eb142d5-fc98-40e2-9d90-84733f2a27ba
ms.openlocfilehash: 8a6f13da9bf05d87c45d86a09261d0c7245f5b00
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546911"
---
# <a name="windows-forms-configuration-section"></a><span data-ttu-id="73952-102">Sekcja konfiguracji programu Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73952-102">Windows Forms Configuration Section</span></span>
<span data-ttu-id="73952-103">Windows Forms ustawienia konfiguracji umożliwiają aplikacji Windows Forms przechowywanie i pobieranie informacji o niestandardowych ustawieniach aplikacji, takich jak obsługa wielomonitorów, obsługa wysokiej rozdzielczości DPI i inne wstępnie zdefiniowane ustawienia konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="73952-103">Windows Forms configuration settings allow a Windows Forms app to store and retrieve information about customized application settings such as multi-monitor support, high DPI support, and other predefined configuration settings.</span></span>

<span data-ttu-id="73952-104">Ustawienia konfiguracji aplikacji Windows Forms są przechowywane w pliku konfiguracji aplikacji `System.Windows.Forms.ApplicationConfigurationSection` .</span><span class="sxs-lookup"><span data-stu-id="73952-104">Windows Forms application configuration settings are stored in an application configuration file's `System.Windows.Forms.ApplicationConfigurationSection` element.</span></span>

## <a name="syntax"></a><span data-ttu-id="73952-105">Składnia</span><span class="sxs-lookup"><span data-stu-id="73952-105">Syntax</span></span>

```xml
<configuration>
  <System.Windows.Forms.ApplicationConfigurationSection>
  ...
  </System.Windows.Forms.ApplicationConfigurationSection>
</configuration>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="73952-106">Atrybuty i elementy</span><span class="sxs-lookup"><span data-stu-id="73952-106">Attributes and elements</span></span>

<span data-ttu-id="73952-107">W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.</span><span class="sxs-lookup"><span data-stu-id="73952-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="73952-108">Atrybuty</span><span class="sxs-lookup"><span data-stu-id="73952-108">Attributes</span></span>

<span data-ttu-id="73952-109">Brak.</span><span class="sxs-lookup"><span data-stu-id="73952-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="73952-110">Elementy podrzędne</span><span class="sxs-lookup"><span data-stu-id="73952-110">Child elements</span></span>

<span data-ttu-id="73952-111">Element</span><span class="sxs-lookup"><span data-stu-id="73952-111">Element</span></span>  |<span data-ttu-id="73952-112">Opis</span><span class="sxs-lookup"><span data-stu-id="73952-112">Description</span></span> |
---------|---------|
[`<add>`](windows-forms-add-configuration-element.md) | <span data-ttu-id="73952-113">Dodaje klucz ustawienia konfiguracji z określoną wartością</span><span class="sxs-lookup"><span data-stu-id="73952-113">Adds a configuration setting key with a specified value</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="73952-114">Elementy nadrzędne</span><span class="sxs-lookup"><span data-stu-id="73952-114">Parent elements</span></span>

<span data-ttu-id="73952-115">Element</span><span class="sxs-lookup"><span data-stu-id="73952-115">Element</span></span>  |<span data-ttu-id="73952-116">Opis</span><span class="sxs-lookup"><span data-stu-id="73952-116">Description</span></span> |
---------|---------|
[\<configuration>](../configuration-element.md) | <span data-ttu-id="73952-117">Element główny w każdym pliku konfiguracji używanym przez środowisko uruchomieniowe języka wspólnego i aplikacje Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73952-117">The root element in every configuration file used by the common language runtime and Windows Forms applications</span></span> |

## <a name="remarks"></a><span data-ttu-id="73952-118">Uwagi</span><span class="sxs-lookup"><span data-stu-id="73952-118">Remarks</span></span>

<span data-ttu-id="73952-119">Począwszy od .NET Framework 4,7, `<System.Windows.Forms.ApplicationConfigurationSection>` element pozwala konfigurować aplikacje Windows Forms, aby korzystać z funkcji dodanych w ostatnich wersjach .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="73952-119">Starting with the .NET Framework 4.7, the `<System.Windows.Forms.ApplicationConfigurationSection>` element allows you to configure Windows Forms applications to take advantage of features added in recent releases of the .NET Framework.</span></span>

<span data-ttu-id="73952-120">`<System.Windows.Forms.ApplicationConfigurationSection>`Element może zawierać jeden lub więcej elementów podrzędnych [`<add>`](windows-forms-add-configuration-element.md) , z których każda definiuje określone ustawienie konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="73952-120">The `<System.Windows.Forms.ApplicationConfigurationSection>` element can include one or more child [`<add>`](windows-forms-add-configuration-element.md) elements, each of which defines a specific configuration setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="73952-121">Zobacz także</span><span class="sxs-lookup"><span data-stu-id="73952-121">See also</span></span>

- [<span data-ttu-id="73952-122">Schemat pliku konfiguracji</span><span class="sxs-lookup"><span data-stu-id="73952-122">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="73952-123">Obsługa wysokiej rozdzielczości DPI w Windows Forms</span><span class="sxs-lookup"><span data-stu-id="73952-123">High DPI Support in Windows Forms</span></span>](/dotnet/desktop/winforms/high-dpi-support-in-windows-forms)
