---
title: Śledzenie SQL
ms.date: 03/30/2017
ms.assetid: bcaebeb1-b9e5-49e8-881b-e49af66fd341
ms.openlocfilehash: 916c04b03dee296b7e6f5c792f0c4e50fb4203c0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90559353"
---
# <a name="sql-tracking"></a>Śledzenie SQL

Ten przykład pokazuje, jak napisać niestandardowego uczestnika śledzenia SQL, który zapisuje rekordy śledzenia do bazy danych SQL. Windows Workflow Foundation (WF) oferuje śledzenie przepływów pracy, aby uzyskać wgląd w wykonywanie wystąpienia przepływu pracy. Środowisko uruchomieniowe śledzenia emituje rekordy śledzenia przepływu pracy podczas wykonywania przepływu pracy. Aby uzyskać więcej informacji na temat śledzenia przepływu pracy, zobacz [śledzenie i śledzenie przepływu pracy](../workflow-tracking-and-tracing.md).

## <a name="use-the-sample"></a>Użyj przykładu

1. Sprawdź, czy masz SQL Server 2008, SQL Server 2008 Express lub nowszy. Skrypty spakowane z przykładem zakładają użycie wystąpienia programu SQL Express na komputerze lokalnym. Jeśli istnieje inne wystąpienie, przed uruchomieniem przykładu należy zmodyfikować skrypty powiązane z bazą danych.

2. Utwórz bazę danych śledzenia SQL Server, uruchamiając Trackingsetup. cmd w katalogu scripts (\WF\Basic\Tracking\SqlTracking\CS\Scripts). Spowoduje to utworzenie bazy danych o nazwie TrackingSample.

   > [!NOTE]
   > Skrypt tworzy bazę danych w domyślnym wystąpieniu programu SQL Express. Jeśli chcesz zainstalować ją w innym wystąpieniu bazy danych, Edytuj skrypt Trackingsetup. cmd.

3. Otwórz SqlTrackingSample. sln w programie Visual Studio 2010.

4. Naciśnij **klawisze CTRL** + **SHIFT** + **B** , aby skompilować rozwiązanie.

5. Naciśnij klawisz **F5** , aby uruchomić aplikację.

   Zostanie otwarte okno przeglądarki i zostanie wyświetlona lista katalogów dla aplikacji.

6. W przeglądarce kliknij pozycję StockPriceService. xamlx.

7. W przeglądarce zostanie wyświetlona strona StockPriceService, która zawiera adres WSDL usługi lokalnej. Kopiuj ten adres.

   Przykładem adresu WSDL usługi lokalnej jest `http://localhost:65193/StockPriceService.xamlx?wsdl` .

8. Korzystając z Eksploratora plików, uruchom klienta testowego WCF (WcfTestClient.exe). Znajduje się w *katalogu Microsoft Visual Studio 10.0 \ Common7\IDE*.

9. W kliencie testowym WCF kliknij menu **plik** i wybierz polecenie **Dodaj usługę**. Wklej adres usługi lokalnej do pola tekstowego. Kliknij przycisk **OK** , aby zamknąć okno dialogowe.

10. W kliencie testowym WCF kliknij dwukrotnie pozycję **GetStockPrice**. Spowoduje to otwarcie `GetStockPrice` operacji, która przyjmuje jeden parametr, wpisz wartość `Contoso` i kliknij przycisk **Wywołaj**.

11. Wysyłane rekordy śledzenia są zapisywane w bazie danych SQL. Aby wyświetlić rekordy śledzenia, Otwórz bazę danych TrackingSample w programie SQL Management Studio i przejdź do tabel. Uruchomienie zapytania SELECT w tabelach wyświetla dane w rekordach śledzenia przechowywanych w odpowiednich tabelach.

   Aby uzyskać więcej informacji na temat SQL Server Management Studio, zobacz [wprowadzenie SQL Server Management Studio](/sql/ssms/sql-server-management-studio-ssms). Pobierz SQL Server Management Studio [tym miejscu](https://aka.ms/ssmsfullsetup).

## <a name="uninstall-the-sample"></a>Odinstalowywanie przykładu

1. Uruchom skrypt theTrackingcleanup. cmd w katalogu przykładowym (*\WF\Basic\Tracking\SqlTracking*).

    > [!NOTE]
    > Trackingcleanup. cmd próbuje usunąć bazę danych w lokalnym komputerze SQL Express. Jeśli używasz innego wystąpienia programu SQL Server, Edytuj Trackingcleanup. cmd.

> [!IMPORTANT]
> Przykłady mogą być już zainstalowane na komputerze. Przed kontynuowaniem Wyszukaj następujący katalog (domyślny).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Jeśli ten katalog nie istnieje, przejdź do [przykładów Windows Communication Foundation (WCF) i Windows Workflow Foundation (WF) dla .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , aby pobrać wszystkie Windows Communication Foundation (WCF) i [!INCLUDE[wf1](../../../../includes/wf1-md.md)] przykłady. Ten przykład znajduje się w następującym katalogu.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\SqlTracking`

## <a name="see-also"></a>Zobacz także

- [Przykłady monitorowania oprogramowania AppFabric](/previous-versions/appfabric/ff383407(v=azure.10))
