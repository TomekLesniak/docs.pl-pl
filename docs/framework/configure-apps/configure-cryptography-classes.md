---
title: Konfigurowanie klasy kryptografii
description: Informacje o tym, jak Administratorzy komputera mogą konfigurować domyślne algorytmy kryptograficzne i implementacje algorytmów używane przez platformę .NET i aplikacje.
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: 5262dfca914fd5306297ea9535bcef3d2088d107
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165211"
---
# <a name="configuring-cryptography-classes"></a>Konfigurowanie klasy kryptografii

Windows SDK pozwala administratorom komputerów skonfigurować domyślne algorytmy kryptograficzne i implementacje algorytmów, które są używane przez .NET Framework i odpowiednio pisanych aplikacje.  Na przykład przedsiębiorstwo, które ma własną implementację algorytmu kryptograficznego, może wprowadzić implementację domyślną zamiast implementacji w Windows SDK. Chociaż zarządzane aplikacje, które używają kryptografii, zawsze mogą jawnie powiązać z konkretną implementacją, zaleca się utworzenie obiektów kryptograficznych przy użyciu systemu konfiguracji kryptograficznej.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [Mapowanie nazw algorytmów na klasy kryptografii](map-algorithm-names-to-cryptography-classes.md)  
 Opisuje sposób mapowania nazwy algorytmu na klasę kryptograficzną.  
  
 [Mapowanie identyfikatorów obiektów na algorytmy kryptografii](map-object-identifiers-to-cryptography-algorithms.md)  
 Opisuje sposób mapowania identyfikatora obiektu na algorytm kryptografii.  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Usługi kryptograficzne](../../standard/security/cryptographic-services.md)  
 Zawiera omówienie usług kryptograficznych zapewnianych przez Windows SDK.  
  
 [Schemat ustawień kryptografii](./file-schema/cryptography/index.md)  
 Opisuje elementy, które mapują przyjazne nazwy algorytmów na klasy implementujące algorytmy kryptografii.
