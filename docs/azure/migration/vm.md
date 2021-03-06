---
title: Migrowanie aplikacji sieci Web ASP.NET na maszynę wirtualną platformy Azure
description: Dowiedz się, jak migrować aplikację sieci Web ASP.NET z lokalnego na maszynę wirtualną platformy Azure.
ms.topic: how-to
ms.date: 06/20/2020
ms.openlocfilehash: 940243310c5e6ed13d2a42c8d9d87244200479f5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171562"
---
# <a name="migrate-an-aspnet-web-application-to-an-azure-virtual-machine"></a>Migrowanie aplikacji sieci Web ASP.NET na maszynę wirtualną platformy Azure

Ten dokument zawiera omówienie sposobu migrowania aplikacji sieci Web ASP.NET z lokalizacji lokalnej na maszynę wirtualną platformy Azure.

## <a name="quickstart"></a>Szybki start

Dowiedz się, jak utworzyć maszynę wirtualną i opublikować w niej aplikację: [Publikowanie na maszynie wirtualnej platformy Azure](https://tutorials.visualstudio.com/aspnet-vm/intro)

## <a name="get-started"></a>Rozpoczęcie pracy

Te samouczki demonstrują procedurę tworzenia (lub migrowania) maszyny wirtualnej, publikowania w niej aplikacji sieci Web oraz innych zadań, które mogą być wymagane do obsługi aplikacji na platformie Azure.

- Utwórz maszynę wirtualną dla swojej aplikacji ASP.NET na platformie Azure przy użyciu jednej z następujących opcji:
  - [Utwórz nową maszynę wirtualną dla aplikacji ASP.NET](https://go.microsoft.com/fwlink/?linkid=863237)
  - [Migrowanie istniejącej lokalnej maszyny wirtualnej VMWare](/azure/migrate/tutorial-migrate-vmware)
  - [Migrowanie istniejącej lokalnej maszyny wirtualnej funkcji Hyper-V](/azure/migrate/tutorial-migrate-hyper-v)
- [Publikowanie aplikacji przy użyciu programu Visual Studio](https://go.microsoft.com/fwlink/?linkid=863240)
- [Tworzenie bezpiecznej sieci wirtualnej dla maszyn wirtualnych](/azure/virtual-network/virtual-network-get-started-vnet-subnet)
- [Tworzenie potoku ciągłej integracji/ciągłego wdrażania dla aplikacji](/vsts/build-release/apps/cd/deploy-webdeploy-iis-deploygroups)
- [Przejdź do zestawu skalowania maszyn wirtualnych w celu zapewnienia wysokiej dostępności i skalowalności](/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-deploy-app)

## <a name="considerations"></a>Zagadnienia do rozważenia

### <a name="benefits"></a>Korzyści

Usługa Virtual Machines oferuje najprostszą ścieżkę do migracji aplikacji z lokalizacji lokalnej do chmury. Umożliwiają one replikację tego samego środowiska, w którym aplikacja jest stosowana lokalnie, a jednocześnie eliminuje konieczność utrzymania własnych centrów danych. Virtual Machine Scale Sets zapewnić wysoką dostępność i skalowalność dla aplikacji działających w Virtual Machines.

### <a name="virtual-machine-size"></a>Rozmiar maszyny wirtualnej

Wybierz rozmiar i typ maszyny wirtualnej, która jest optymalnie zoptymalizowana dla obciążenia. Aby uzyskać więcej informacji, zobacz [rozmiary maszyn wirtualnych z systemem Windows na platformie Azure](/azure/virtual-machines/windows/sizes).

### <a name="maintenance"></a>Konserwacja

Podobnie jak w przypadku maszyn lokalnych, użytkownik jest odpowiedzialny za konserwację i aktualizowanie maszyny wirtualnej<sup>&#42;</sup>. Jeśli aplikacja może działać w środowisku PaaS (Platform as a Service), takim jak [Azure App Service](/azure/app-service/) lub w [kontenerze](/azure/app-service/containers/), spowoduje to usunięcie tej potrzeby.

*<sup>&#42;</sup> [automatyczne uaktualnienia systemu operacyjnego dla zestawów skalowania maszyn wirtualnych](/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-automatic-upgrade) jest obecnie dostępne jako usługa w wersji zapoznawczej.*

### <a name="virtual-networks"></a>Sieci wirtualne

Usługa Azure Virtual Networks umożliwia:

- Tworzenie infrastruktury hybrydowej kontrolowanej przez użytkownika
- Przenoszenie własnych adresów IP i serwerów DNS
- Tworzenie izolowanego i wysoce bezpiecznego środowiska dla aplikacji
- Połącz maszynę wirtualną z siecią lokalną przy użyciu jednej z kilku [opcji łączności](/azure/vpn-gateway/vpn-gateway-about-vpngateways#s2smulti)
- Integruj maszynę wirtualną z siecią lokalną za pomocą [ExpressRoute](https://azure.microsoft.com/services/expressroute/)

Aby rozpocząć, zobacz [dokumentację dotyczącą Virtual Network](/azure/virtual-network/)

### <a name="active-directory"></a>Usługa Active Directory

Wiele aplikacji używa Active Directory do uwierzytelniania i zarządzania tożsamościami.

- Azure AD Connect umożliwia integrację katalogów lokalnych z Azure Active Directory. Aby rozpocząć, zobacz [integrowanie katalogów lokalnych z Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).
- Alternatywnie [ExpressRoute](https://azure.microsoft.com/services/expressroute/) umożliwia aplikacji dostęp do Active Directory lokalnych.

### <a name="sql-databases"></a>Bazy danych SQL

Jeśli aplikacja korzysta z lokalnej bazy danych, aplikacja nie będzie mogła komunikować się z nią domyślnie. Można:

- Skonfiguruj sieć hybrydową, która umożliwia aplikacji dostęp do bazy danych działającej lokalnie.
- Przeprowadź migrację bazy danych do platformy Azure. Aby uzyskać więcej informacji, zobacz [Migrowanie bazy danych SQL Server na platformę Azure](sql.md).

### <a name="high-availability-and-scalability"></a>Wysoka dostępność i skalowalność

#### <a name="virtual-machine-scale-sets"></a>Zestawy skali maszyn wirtualnych

Upewnij się, że aplikacja jest wysoce dostępna i można ją skalować, migrować do zestawu skalowania maszyn wirtualnych platformy Azure, aby zwiększyć dostępność i skalowalność aplikacji. VM Scale Sets zapewnić możliwość korzystania z istniejącej maszyny wirtualnej, która została już skonfigurowana, lub skonfigurowania potoku kompilacji w celu utworzenia obrazu w aplikacji.

Aby rozpocząć, zobacz [wdrażanie aplikacji w zestawach skalowania maszyn wirtualnych](/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-deploy-app).

#### <a name="centralized-logging"></a>Scentralizowane rejestrowanie

W przypadku uruchamiania aplikacji w wielu wystąpieniach warto rozważyć przechowywanie dzienników w scentralizowanej lokalizacji, takiej jak [usługa Azure Storage](/azure/storage/).

## <a name="next-steps"></a>Następne kroki

> [!div class="nextstepaction"]
> [Migrowanie bazy danych programu SQL Server na platformę Azure](sql.md)
