---
title: Zabezpieczanie aplikacji klienckich
ms.date: 03/30/2017
ms.assetid: 6239592e-fa7d-4dea-9f00-d296d0048b01
ms.openlocfilehash: 96b43d28d3e22df66cb7f7010916b5c7f7a86b77
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189009"
---
# <a name="secure-client-applications"></a>Zabezpieczanie aplikacji klienckich

Aplikacje zwykle składają się z wielu części, które muszą być chronione przed lukami w zabezpieczeniach, co może spowodować utratę danych lub w inny sposób złamać system. Tworzenie bezpiecznych interfejsów użytkownika może zapobiec wielu problemom, blokując osoby atakujące przed uzyskaniem dostępu do danych lub zasobów systemowych.  
  
## <a name="validate-user-input"></a>Sprawdzanie poprawności danych wejściowych użytkownika  

 Podczas konstruowania aplikacji, która uzyskuje dostęp do danych, należy zastanowić się, że wszystkie dane wejściowe użytkownika są złośliwe, dopóki nie zostaną udowodnione. Niewykonanie tej czynności może spowodować, że aplikacja będzie narażona na ataki. .NET Framework zawiera klasy, które ułatwiają wymuszanie domeny wartości dla kontrolek wejściowych, takich jak ograniczenie liczby znaków, które można wprowadzić. Punkty zaczepienia zdarzeń umożliwiają pisanie procedur w celu sprawdzenia poprawności wartości. Dane wejściowe użytkownika mogą być zweryfikowane i jednoznacznie wpisane, ograniczając narażenie aplikacji na luki w zabezpieczeniach skryptów i iniekcji SQL.  
  
> [!IMPORTANT]
> Należy również sprawdzić poprawność danych wejściowych użytkownika w źródle danych, a także w aplikacji klienckiej. Osoba atakująca może zdecydować się na obejście aplikacji i bezpośrednie ataki ze źródła danych.  
  
 [Zabezpieczenia i dane użytkownika](../../../standard/security/security-and-user-input.md)  
 Opisuje, jak obsługiwać delikatne i potencjalnie niebezpieczne usterki dotyczące danych wejściowych użytkownika.  
  
 [Sprawdzanie poprawności danych wejściowych użytkownika na stronach sieci Web ASP.NET](/previous-versions/aspnet/7kh55542(v=vs.100))  
 Przegląd sprawdzania poprawności danych wprowadzonych przez użytkownika przy użyciu kontrolek weryfikacji ASP.NET.  
  
 [Dane użytkownika w formularzach systemu Windows](/dotnet/desktop/winforms/user-input-in-windows-forms)  
 Zawiera linki i informacje dotyczące sprawdzania poprawności danych wejściowych myszy i klawiatury w aplikacji Windows Forms.  
  
 [.NET Framework — Wyrażenia regularne](../../../standard/base-types/regular-expressions.md)  
 Opisuje, w jaki sposób używać <xref:System.Text.RegularExpressions.Regex> klasy do sprawdzania poprawności danych wejściowych użytkownika.  
  
## <a name="windows-applications"></a>Aplikacje systemu Windows  

 W przeszłości aplikacje systemu Windows są zwykle wykonywane z pełnymi uprawnieniami. .NET Framework zapewnia infrastrukturę ograniczającą wykonywanie kodu w aplikacji systemu Windows przy użyciu zabezpieczeń dostępu kodu (CAS). Jednak tylko urzędy certyfikacji nie wystarczają do ochrony aplikacji.  
  
 [Zabezpieczenia formularzy systemu Windows](/dotnet/desktop/winforms/windows-forms-security)  
 Omawia sposób zabezpieczania Windows Forms aplikacji i zawiera linki do powiązanych tematów.  
  
 [Formularze systemu Windows i niezarządzane aplikacje](/dotnet/desktop/winforms/advanced/windows-forms-and-unmanaged-applications)  
 Opisuje sposób współpracy z niezarządzanymi aplikacjami w aplikacji Windows Forms.  
  
 [Wdrożenie ClickOnce w przypadku formularzy systemu Windows](/dotnet/desktop/winforms/clickonce-deployment-for-windows-forms)  
 Opisuje sposób używania `ClickOnce` wdrożenia w aplikacji Windows Forms i omawia implikacje związane z bezpieczeństwem.  
  
## <a name="aspnet-and-xml-web-services"></a>ASP.NET i XML Web Services  

 Aplikacje ASP.NET zazwyczaj muszą ograniczyć dostęp do niektórych części witryny sieci Web i zapewnić inne mechanizmy ochrony danych i zabezpieczeń lokacji. Te linki zapewniają przydatne informacje na potrzeby zabezpieczania aplikacji ASP.NET.  
  
 Usługa sieci Web XML udostępnia dane, które mogą być używane przez aplikację ASP.NET, aplikację Windows Forms lub inną usługę sieci Web. Należy zarządzać zabezpieczeniami samej usługi sieci Web, a także zabezpieczeniami dla aplikacji klienckiej.  
  
 Więcej informacji zawierają poniższe zasoby.  
  
|Zasób|Opis|  
|--------------|-----------------|  
|[Zabezpieczanie witryn sieci Web ASP.NET](/previous-versions/aspnet/91f66yxt(v=vs.100))|W tym artykule omówiono sposób zabezpieczania aplikacji ASP.NET.|  
|[Zabezpieczanie usług sieci Web XML utworzonych za pomocą ASP.NET](/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100))|W tym artykule omówiono sposób implementowania zabezpieczeń usługi sieci Web ASP.NET.|  
|[Omówienie luk w zabezpieczeniach](/previous-versions/aspnet/w1sw53ds(v=vs.100))|W tym artykule omówiono sposób ochrony przed atakami wykorzystującymi luki w zabezpieczeniach, które próbują wstawiać złośliwe znaki do strony sieci Web.|  
|[Podstawowe rozwiązania w zakresie zabezpieczeń dla aplikacji sieci Web](/previous-versions/aspnet/zdh19h94(v=vs.100))|Ogólne informacje o zabezpieczeniach i linki do dalszych dyskusji,|  
  
## <a name="remoting"></a>Komunikacji zdalnej  

 Komunikacja zdalna platformy .NET umożliwia łatwe tworzenie rozproszonych aplikacji, niezależnie od tego, czy składniki aplikacji znajdują się na jednym komputerze, czy rozkładają się na całym świecie. Można tworzyć aplikacje klienckie, które używają obiektów w innych procesach na tym samym komputerze lub na innym komputerze, który jest dostępny w sieci. Można również użyć komunikacji zdalnej .NET do komunikowania się z innymi domenami aplikacji w tym samym procesie.  
  
|Zasób|Opis|  
|--------------|-----------------|  
|[Konfiguracja aplikacji zdalnych](/previous-versions/dotnet/netframework-4.0/b8tysty8(v=vs.100))|W tym artykule omówiono sposób konfigurowania aplikacji zdalnych w celu uniknięcia typowych problemów.|  
|[Zabezpieczenia w komunikacji zdalnej](/previous-versions/dotnet/netframework-4.0/9hwst9th(v=vs.100))|Zawiera opis uwierzytelniania i szyfrowania, a także dodatkowe tematy dotyczące zabezpieczeń związane z usługami zdalnymi.|  
|[Zagadnienia dotyczące zabezpieczeń internetowych i zdalnego dostępu](../../misc/security-and-remoting-considerations.md)|Opisuje problemy z zabezpieczeniami dotyczące obiektów chronionych i przekroczenia domeny aplikacji.|  
  
## <a name="see-also"></a>Zobacz też

- [Zabezpieczanie aplikacji ADO.NET](securing-ado-net-applications.md)
- [Zalecenia dotyczące strategii dostępu do danych](/previous-versions/visualstudio/visual-studio-2008/8fxztkff(v=vs.90))
- [Zabezpieczanie aplikacji](/visualstudio/ide/securing-applications)
- [Ochrona informacji o połączeniu](protecting-connection-information.md)
- [Omówienie ADO.NET](ado-net-overview.md)
