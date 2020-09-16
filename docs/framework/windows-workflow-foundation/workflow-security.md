---
title: Zabezpieczenia przepływu pracy
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], workflow security
ms.assetid: d712a566-f435-44c0-b8c0-49298e84b114
ms.openlocfilehash: d2d8556b1ed2ac0a2b030a88d6bfc0ad48ed6f5c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557518"
---
# <a name="workflow-security"></a>Zabezpieczenia przepływu pracy
Funkcja Windows Workflow Foundation (WF) jest zintegrowana z kilkoma różnymi technologiami, takimi jak Microsoft SQL Server i Windows Communication Foundation (WCF). Korzystanie z tych technologii może spowodować problemy z zabezpieczeniami w przepływie pracy, jeśli zostało wykonane nieprawidłowo.

## <a name="persistence-security-concerns"></a>Problemy z bezpieczeństwem trwałości

1. Przepływy pracy korzystające z <xref:System.Activities.Statements.Delay> działań i trwałości muszą zostać ponownie aktywowane przez usługę. Windows AppFabric używa usługi zarządzania przepływami pracy, aby ponownie aktywować przepływy pracy z wygasłymi czasomierzami. Usługa WMS tworzy <xref:System.ServiceModel.WorkflowServiceHost> do hostowania ponownie uaktywnionego przepływu pracy. Jeśli usługa WMS zostanie zatrzymana, utrwalone przepływy pracy nie zostaną ponownie aktywowane po wygaśnięciu czasomierza.

2. Dostęp do trwałych wystąpień należy chronić przed złośliwymi jednostkami spoza domeny aplikacji. Ponadto deweloperzy powinni upewnić się, że złośliwy kod nie może być wykonywany w tej samej domenie aplikacji co kod wystąpienia trwałego.

3. Tworzenie trwałych wystąpień nie powinno być uruchamiane z podniesionymi uprawnieniami (administratora).

4. Dane przetwarzane poza domeną aplikacji powinny być chronione.

5. Aplikacje wymagające izolacji zabezpieczeń nie powinny współużytkować tego samego wystąpienia abstrakcji schematu. Takie aplikacje powinny korzystać z różnych dostawców sklepu lub dostawców magazynu skonfigurowanych do korzystania z różnych wystąpień magazynu.

## <a name="sql-server-security-concerns"></a>Zagadnienia dotyczące zabezpieczeń SQL Server

- Gdy używane są duże liczby działań podrzędnych, lokalizacji, zakładek, rozszerzeń hosta lub zakresów, lub gdy są używane zakładki z bardzo dużymi ładunkiem, pamięć może być wyczerpana lub nadmierna ilość miejsca na bazę danych może zostać przypisana podczas trwałości. Można to ograniczyć przy użyciu zabezpieczeń na poziomie obiektów i na poziomie bazy danych.

- W przypadku korzystania <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> z programu Magazyn wystąpień musi być zabezpieczony.

- Poufne dane w magazynie wystąpień powinny być szyfrowane. Aby uzyskać więcej informacji, zobacz [SQL Server Encryption](/sql/relational-databases/security/encryption/sql-server-encryption).

- Ponieważ parametry połączenia z bazą danych często znajdują się w pliku konfiguracji, należy użyć zabezpieczeń na poziomie systemu Windows, aby upewnić się, że plik konfiguracji (Web.Config zazwyczaj) jest zabezpieczony, a informacje o logowaniu i haśle nie są zawarte w parametrach połączenia. Zamiast tego należy użyć uwierzytelniania systemu Windows między bazą danych a serwerem sieci Web.

## <a name="considerations-for-workflowservicehost"></a>Zagadnienia dotyczące obiektu WorkflowServiceHost

- Windows Communication Foundation (WCF) punkty końcowe używane w przepływach pracy powinny być zabezpieczone. Aby uzyskać więcej informacji, zobacz [Omówienie zabezpieczeń programu WCF](../wcf/feature-details/security-overview.md).

- Autoryzację na poziomie hosta można zaimplementować za pomocą polecenia <xref:System.ServiceModel.ServiceAuthorizationManager> . Aby uzyskać szczegółowe informacje [, zobacz jak to zrobić: Tworzenie niestandardowego Menedżera autoryzacji dla usługi](../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md) .

- ServiceSecurityContext dla wiadomości przychodzącej jest również dostępny w ramach przepływu pracy przez dostęp do elementu OperationContext.

## <a name="wf-security-pack-ctp"></a>WF Security Pack CTP
 Microsoft WF Security Pack (CTP) 1 to zestaw działań i ich wdrożenia na podstawie [Windows Workflow Foundation](index.md) w [.NET Framework 4](/previous-versions/dotnet/netframework-4.0/w0x726c2(v=vs.100)) (WF 4) i [Windows Identity Foundation (WIF)](/previous-versions/dotnet/framework/security/index). Pakiet Microsoft WF Security Pack CTP 1 zawiera zarówno działania, jak i ich projektantów, które ilustrują, jak łatwo włączyć różne scenariusze związane z zabezpieczeniami korzystające z przepływu pracy, w tym:

1. Personifikowanie tożsamości klienta w przepływie pracy

2. Autoryzacja w przepływie pracy, taka jak PrincipalPermission i weryfikacja oświadczeń

3. Komunikaty uwierzytelnione przy użyciu funkcji ClientCredentials określonych w przepływie pracy, takie jak nazwa użytkownika/hasło lub token pobrany z usługi tokenu zabezpieczającego (STS)

4. Przepływanie tokenu zabezpieczeń klienta do usługi zaplecza (delegowanie oparte na oświadczeniach) przy użyciu usługi WS-Trust ActAs

Aby uzyskać więcej informacji i pobrać pakiet zabezpieczeń programu WF CTP, zobacz: [WF Security Pack CTP](https://archive.codeplex.com/?p=wf)
