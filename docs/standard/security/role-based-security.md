---
title: Zabezpieczenia oparte na rolach
ms.date: 07/15/2020
ms.technology: dotnet-standard
helpviewer_keywords:
- role-based security, about role-based security
- user authentication, principals
- principals [.NET]
- security [.NET], role-based
- permissions [.NET], principals
- authentication [.NET], principals
- role-based security, principals
ms.assetid: 578cc32b-5654-4d8b-9d8c-ebcbc5c75390
ms.openlocfilehash: ed6c33be5a5da066e238c160da8bff8d25cb68fc
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555681"
---
# <a name="role-based-security"></a>Zabezpieczenia oparte na rolach

Role są często używane w aplikacjach finansowych lub firmowych w celu wymuszenia zasad. Na przykład aplikacja może nakładać limity rozmiaru przetwarzanej transakcji w zależności od tego, czy użytkownik wysyłający żądanie jest członkiem określonej roli. Urzędy mogą mieć autoryzację, aby przetwarzać transakcje, które są mniejsze od określonego progu, kierownicy mogą mieć wyższy limit, a wiceprezesowie mogą mieć jeszcze wyższy limit (lub bez ograniczeń). Zabezpieczeń opartych na rolach można także użyć, gdy aplikacja wymaga wielu zatwierdzeń do ukończenia akcji. Taki przypadek może być systemem zakupów, w którym każdy pracownik może wygenerować żądanie zakupu, ale tylko agent zakupów może przekonwertować to żądanie na zamówienie zakupu, które może zostać wysłane do dostawcy.  
  
 Zabezpieczenia oparte na rolach platformy .NET obsługują autoryzację, tworząc informacje o podmiotu zabezpieczeń, który jest zbudowany ze skojarzonej tożsamości, dostępnej dla bieżącego wątku. Tożsamość (oraz podmiot zabezpieczeń, które ułatwiają zdefiniowanie) mogą być oparte na koncie systemu Windows lub być niestandardową tożsamością niepowiązaną z kontem systemu Windows. Aplikacje platformy .NET mogą podejmować decyzje dotyczące autoryzacji w oparciu o tożsamość lub role podmiotu zabezpieczeń. Rola to nazwany zestaw podmiotów zabezpieczeń, który ma takie same uprawnienia, w odniesieniu do zabezpieczeń (takich jak Kasjer lub kierownik). Podmiot zabezpieczeń może być członkiem jednej lub większej liczby ról. W związku z tym aplikacje mogą używać przynależności do roli, aby określić, czy podmiot zabezpieczeń jest autoryzowany do wykonywania żądanych akcji.  
  
 Aby zapewnić łatwość użycia i spójność z zabezpieczeniami dostępu kodu, zabezpieczenia oparte na rolach programu .NET udostępniają <xref:System.Security.Permissions.PrincipalPermission?displayProperty=nameWithType> obiekty, które umożliwiają środowisko uruchomieniowe języka wspólnego wykonywanie autoryzacji w sposób podobny do sprawdzania zabezpieczeń dostępu kodu. <xref:System.Security.Permissions.PrincipalPermission>Klasa reprezentuje tożsamość lub rolę, która musi być zgodna z podmiotem zabezpieczeń i jest zgodna z kontrolami bezpieczeństwa deklaracyjnego i bezwzględnego. Dostęp do informacji o tożsamości podmiotu zabezpieczeń można także uzyskać bezpośrednio, a w razie konieczności sprawdzać rolę i tożsamość w kodzie.  
  
 Platforma .NET zapewnia obsługę zabezpieczeń opartą na rolach, która jest elastyczna i rozszerzalna, aby zaspokoić potrzeby szerokiego spektrum aplikacji. Możesz zdecydować się na współdziałanie z istniejącymi infrastrukturami uwierzytelniania, takimi jak usługi COM+ 1,0, lub utworzyć niestandardowy system uwierzytelniania. Zabezpieczenia oparte na rolach są szczególnie odpowiednie do użycia w aplikacjach sieci Web ASP.NET, które są przetwarzane głównie na serwerze programu. Jednak zabezpieczeń opartych na rolach platformy .NET można używać zarówno na kliencie, jak i na serwerze.  
  
 Przed przeczytaniem tej sekcji należy zapoznać się z materiałami przedstawionymi w [najważniejszych pojęciach dotyczących zabezpieczeń](key-security-concepts.md).  
  
## <a name="see-also"></a>Zobacz też
  
- [Obiekty główne i obiekty tożsamości](principal-and-identity-objects.md)
- [Główne pojęcia dotyczące zabezpieczeń](key-security-concepts.md)
- <xref:System.Security.Permissions.PrincipalPermission?displayProperty=nameWithType>
- [Zabezpieczenia ASP.NET Core](/aspnet/core/security/)
