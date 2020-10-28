---
title: Lokalizacja zestawu
description: Lokalizacja zestawu .NET określa, w jaki sposób środowisko CLR znajduje je i czy może być współużytkowane z innymi zestawami.
ms.date: 08/20/2019
helpviewer_keywords:
- locating assemblies
- assemblies [.NET], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
ms.openlocfilehash: 1fa1c486c0cddce4ddcfae7f2df27e2e85c88e66
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687601"
---
# <a name="assembly-location"></a>Lokalizacja zestawu

Lokalizacja zestawu określa, czy środowisko uruchomieniowe języka wspólnego może je zlokalizować w przypadku odwołania, a także określić, czy zestaw może być współużytkowany z innymi zestawami. Zestaw można wdrożyć w następujących lokalizacjach:

- Katalog lub podkatalogi aplikacji.

     Jest to najczęściej używane miejsce wdrożenia zestawu. Podkatalogi katalogu głównego aplikacji mogą opierać się na języku lub kulturze. Jeśli zestaw zawiera informacje w atrybucie Culture, musi znajdować się w podkatalogu w katalogu aplikacji z nazwą tej kultury.

- Globalna pamięć podręczna zestawów.

     Jest to pamięć podręczna kodu całego komputera zainstalowana wszędzie tam, gdzie jest zainstalowany aparat plików wykonywalnych języka wspólnego. W większości przypadków, jeśli zamierzasz udostępnić zestaw z wieloma aplikacjami, należy wdrożyć go w globalnej pamięci podręcznej zestawów.

- Na serwerze HTTP.

     Zestaw wdrożony na serwerze HTTP musi mieć silną nazwę; Wskaż zestaw w sekcji codebase w pliku konfiguracyjnym aplikacji.

## <a name="see-also"></a>Zobacz także

- [Tworzenie zestawów](create.md)
- [Globalna pamięć podręczna zestawów](../../framework/app-domains/gac.md)
- [Jak środowisko uruchomieniowe lokalizuje zestawy](../../framework/deployment/how-the-runtime-locates-assemblies.md)
