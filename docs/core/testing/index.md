---
title: Testowanie w programie .NET
description: Ten artykuł zawiera krótkie omówienie pojęć związanych z testowaniem, terminologii i narzędzi do testowania w programie .NET.
author: IEvangelist
ms.author: dapine
ms.date: 10/19/2020
ms.openlocfilehash: 36e88cc059447a98931593e0535c70cbc92a2cf4
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223474"
---
# <a name="testing-in-net"></a>Testowanie w programie .NET

W tym artykule wprowadzono koncepcję testowania i przedstawiono sposób, w jaki różne rodzaje testów mogą służyć do walidacji kodu. Dostępne są różne narzędzia do testowania aplikacji .NET, takich jak [interfejs wiersza polecenia platformy .NET](#net-cli) lub [zintegrowane środowiska deweloperskie (środowisk IDE)](#ide).

## <a name="test-types"></a>Typy testów

Posiadanie zautomatyzowanych testów to doskonały sposób, aby upewnić się, że kod aplikacji wykonuje działania wykonywane przez jego autorów. W tym artykule omówiono testy jednostkowe, testy integracji i testy obciążenia.

### <a name="unit-tests"></a>Testy jednostkowe

*Test jednostkowy* jest testem, który wykonuje poszczególne składniki oprogramowania lub metody, znane także jako "jednostka pracy". Testy jednostkowe powinny tylko testować kod w formancie dewelopera. Nie testują problemów dotyczących infrastruktury. Zagadnienia dotyczące infrastruktury obejmują współpracę z bazami danych, systemami plików i zasobami sieciowymi.

Aby uzyskać więcej informacji na temat tworzenia testów jednostkowych, zobacz [Narzędzia do testowania](#testing-tools).

### <a name="integration-tests"></a>Testy integracji

*Test integracji* różni się od testów jednostkowych, co umożliwia współdziałanie dwóch lub większej liczby składników oprogramowania, znanych także jako "Integracja". Te testy działają na szerszym spektrum testowanego systemu, podczas gdy testy jednostkowe koncentrują się na poszczególnych składnikach. Często testy integracji obejmują zagadnienia związane z infrastrukturą.

### <a name="load-tests"></a>Testy obciążenia

*Test obciążenia* ma na celu określenie, czy system może obsłużyć określone obciążenie, na przykład liczbę równoczesnych użytkowników korzystających z aplikacji oraz możliwość obsługi interakcji przez aplikację. Aby uzyskać więcej informacji na temat testowania obciążeniowego aplikacji sieci Web, zobacz [ASP.NET Core testowanie obciążeniowe/obciążeniowe](/aspnet/core/test/load-tests).

## <a name="test-considerations"></a>Zagadnienia dotyczące testowania

Należy pamiętać o [najlepszych rozwiązaniach](unit-testing-best-practices.md) dotyczących pisania testów. Na przykład [programowanie sterowane testami (TDD)](https://deviq.com/test-driven-development) to gdy test jednostkowy jest zapisywana przed kodem, który ma być sprawdzany. TDD przypomina Tworzenie konspektu dla książki przed jej zapisaniem. Jest to pomocne, aby deweloperzy mogli pisać łatwiejszy, czytelny i wydajny kod.

## <a name="testing-tools"></a>Narzędzia do testowania

.NET jest platformą programistyczną dla wielu języków i można napisać różne typy testów dla [języków C#](../../csharp/index.yml), [F #](../../fsharp/index.yml)i [Visual Basic](../../visual-basic/index.yml). Dla każdego z tych języków można wybrać kilka platform testowych.

### <a name="xunit"></a>xUnit

[xUnit](https://xunit.net) to bezpłatne narzędzie do testowania jednostkowego dla platformy .NET przeznaczone dla społeczności typu open source. Zapisanie przez oryginalny spis NUnit v2, xUnit.net to najnowsza technologia do testowania jednostkowego aplikacji .NET. xUnit.net współpracuje z reostrer, CodeRush, TestDriven.NET i [Xamarin](/apps/xamarin). Jest to projekt [platformy .NET Foundation](https://dotnetfoundation.org) i działa w ramach ich Kodeksu postępowania.

Więcej informacji można znaleźć w następujących zasobach:

- [Testowanie jednostkowe przy użyciu języka C #](unit-testing-with-dotnet-test.md)
- [Testowanie jednostkowe przy użyciu języka F #](unit-testing-fsharp-with-dotnet-test.md)
- [Testowanie jednostkowe za pomocą Visual Basic](unit-testing-visual-basic-with-dotnet-test.md)

### <a name="nunit"></a>NUnit

[Nunit](https://nunit.org) to struktura testowania jednostkowego dla wszystkich języków .NET. Początkowo z JUnit, bieżąca wersja produkcyjna została zapisywana z wieloma nowymi funkcjami i obsługą dla szerokiego zakresu platform .NET. Jest to projekt [platformy .NET Foundation](https://dotnetfoundation.org).

Więcej informacji można znaleźć w następujących zasobach:

- [Testowanie jednostkowe przy użyciu języka C #](unit-testing-with-nunit.md)
- [Testowanie jednostkowe przy użyciu języka F #](unit-testing-fsharp-with-nunit.md)
- [Testowanie jednostkowe za pomocą Visual Basic](unit-testing-visual-basic-with-nunit.md)

### <a name="mstest"></a>MSTest

[MSTest](https://github.com/Microsoft/testfx-docs) to Microsoft Test Framework dla wszystkich języków .NET. Jest ona rozszerzalna i współpracuje z interfejsem wiersza polecenia platformy .NET i programem Visual Studio. Więcej informacji można znaleźć w następujących zasobach:

- [Testowanie jednostkowe przy użyciu języka C #](unit-testing-with-mstest.md)
- [Testowanie jednostkowe przy użyciu języka F #](unit-testing-fsharp-with-mstest.md)
- [Testowanie jednostkowe za pomocą Visual Basic](unit-testing-visual-basic-with-mstest.md)

### <a name="net-cli"></a>INTERFEJS WIERSZA POLECENIA PLATFORMY .NET

Testy jednostkowe rozwiązań można uruchomić z poziomu [interfejsu wiersza polecenia platformy .NET](../tools/index.md), z poleceniem [test dotnet](../tools/dotnet-test.md) . Interfejs wiersza polecenia platformy .NET udostępnia większość funkcji, które są dostępne w ramach interfejsów użytkownika [zintegrowane środowiska deweloperskie (środowisk IDE)](#ide) . Interfejs wiersza polecenia platformy .NET jest na wielu platformach i jest dostępny do użytku w ramach potoków ciągłej integracji i dostarczania. Interfejs wiersza polecenia platformy .NET jest używany w przypadku procesów inicjowanych przez skrypty do automatyzowania typowych zadań.

### <a name="ide"></a>IDE

Niezależnie od tego, czy używasz programu Visual Studio, Visual Studio dla komputerów Mac czy Visual Studio Code, istnieją graficzne interfejsy użytkownika do testowania funkcji. Dostępne są więcej funkcji środowisk IDE niż interfejs wiersza polecenia, na przykład [Live Unit Testing](/visualstudio/test/live-unit-testing). Aby uzyskać więcej informacji, zobacz [dołączanie i wykluczanie testów w programie Visual Studio](/visualstudio/test/live-unit-testing#include-and-exclude-test-projects-and-test-methods).

## <a name="see-also"></a>Zobacz też

Aby uzyskać więcej informacji, zobacz następujące artykuły:

- [Najlepsze rozwiązania dotyczące testów jednostkowych za pomocą platformy .NET](unit-testing-best-practices.md)
- [Testy integracji w ASP.NET Core](/aspnet/core/test/integration-tests#test-app-prerequisites)
- [Uruchamianie selektywnych testów jednostkowych](selective-unit-tests.md)
- [Użyj pokrycia kodu do testów jednostkowych](unit-testing-code-coverage.md)
