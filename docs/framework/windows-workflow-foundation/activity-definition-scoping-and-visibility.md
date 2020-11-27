---
title: Wyznaczanie zakresu i widoczność definicji działania
ms.date: 03/30/2017
ms.assetid: ccdffa07-9503-4eea-a61b-17f1564368b7
ms.openlocfilehash: c7f656fee4960a8c43ac58abafba400ed9b35bc1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289168"
---
# <a name="activity-definition-scoping-and-visibility"></a>Wyznaczanie zakresu i widoczność definicji działania

Zakres i widoczność definicji działań, podobnie jak określanie zakresu i widoczność obiektu, to zdolność innych obiektów lub działań do uzyskiwania dostępu do elementów członkowskich działania. Definicja działania jest wykonywana przez następujące implementacje:  
  
1. Określanie elementów członkowskich ( <xref:System.Activities.Argument> , <xref:System.Activities.Variable> , <xref:System.Activities.ActivityDelegate> obiektów i działań podrzędnych) dla działania ujawnia użytkownikom.  
  
2. Implementowanie logiki wykonywania działania  
  
 Implementacja może dotyczyć członków, którzy nie są narażeni na odbiorców działania, ale są raczej szczegółowymi informacjami o implementacji.  Podobnie jak w przypadku definicji typu, model działania umożliwia autorowi kwalifikowanie widoczności elementu członkowskiego działania w odniesieniu do definicji definiowanego działania.  Ta widoczność kontroluje aspekty użycia elementu członkowskiego, takie jak określanie zakresu danych.  
  
## <a name="scope"></a>Zakres  

 Oprócz określania zakresu danych widoczność modelu działania może ograniczyć dostęp do innych aspektów działania, takich jak Walidacja, debugowanie, śledzenie lub śledzenie. Właściwości wykonywania wykorzystują widoczność i zakres dla charakterystyki wykonywania ograniczające do określonego zakresu definicji. Pomocnicze katalogi główne używają widoczności i określania zakresu, aby ograniczyć stan przechwycony przez a <xref:System.Activities.Statements.CompensableActivity> do zakresu definicji, w której używane są działania kompensacyjne.  
  
## <a name="definition-and-usage"></a>Definicja i użycie  

 Przepływ pracy jest tworzony przez tworzenie nowych działań przez dziedziczenie z klas działania podstawowego i używanie działań z [wbudowanej biblioteki działań](net-framework-4-5-built-in-activity-library.md). Aby można było użyć działania, autor działania musi skonfigurować widoczność każdego składnika jego definicji.  
  
### <a name="activity-members"></a>Elementy członkowskie działania  

 Model działania definiuje argumenty, zmienne, Delegaty i działania podrzędne, które działanie staje się dostępne dla klientów. Każdy z tych elementów członkowskich może być zadeklarowany jako `public` lub `private` . Publiczne składowe są konfigurowane przez konsumenta działania, natomiast `private` członkowie korzystają z implementacji ustalonej przez autora działania. Reguły widoczności dla określania zakresu danych są następujące:  
  
1. Publiczne elementy członkowskie i publiczne elementy członkowskie publicznych działań podrzędnych mogą odwoływać się do zmiennych publicznych.  
  
2. Prywatne elementy członkowskie i publiczne elementy członkowskie publicznych działań podrzędnych mogą odwoływać się do argumentów i zmiennych prywatnych.  
  
 Członek, który może być ustawiony przez konsumenta działania, nigdy nie powinien być prywatny.  
  
### <a name="authoring-models"></a>Tworzenie modeli  

 Niestandardowe działania są definiowane przy użyciu <xref:System.Activities.NativeActivity> , <xref:System.Activities.Activity> , <xref:System.Activities.CodeActivity> , lub <xref:System.Activities.AsyncCodeActivity> . Działania, które pochodzą od tych klas mogą uwidaczniać różne typy elementów członkowskich z różnymi widoczności.  
  
#### <a name="nativeactivity"></a>NativeActivity  

 Działania, które pochodzą z <xref:System.Activities.NativeActivity> mają zachowanie, które są zapisywane w kodzie bezwzględnym i opcjonalnie można zdefiniować przy użyciu istniejących działań. Wygenerowanie działań od <xref:System.Activities.NativeActivity> przyznania dostępu do wszystkich funkcji udostępnianych przez środowisko uruchomieniowe. Każdy element członkowski takiego działania można zdefiniować przy użyciu publicznej lub prywatnej widoczności, z wyjątkiem argumentów, które mogą być deklarowane tylko jako `public` .  
  
 Elementy członkowskie klas pochodnych z <xref:System.Activities.NativeActivity> są zadeklarowane w środowisku uruchomieniowym przy użyciu <xref:System.Activities.NativeActivityMetadata> struktury przekazaną do <xref:System.Activities.NativeActivity.CacheMetadata%2A> metody.  
  
#### <a name="activity"></a>Działanie  

 Działania utworzone przy użyciu <xref:System.Activities.Activity> mają zachowanie, które jest przeznaczone wyłącznie do tworzenia innych działań. <xref:System.Activities.Activity>Klasa ma jedno działanie podrzędne implementacji, uzyskane przez środowisko uruchomieniowe przy użyciu <xref:System.Activities.Activity.Implementation%2A> . Działanie wynikające z programu <xref:System.Activities.Activity> może definiować argumenty publiczne, zmienne publiczne, zaimportowane ActivityDelegate i zaimportowane działania.  
  
 Zaimportowane ActivityDelegate i działania są deklarowane jako publiczne elementy podrzędne działania, ale nie mogą być bezpośrednio zaplanowane przez działanie. Te informacje są używane podczas weryfikacji, aby uniknąć uruchamiania walidacji mających dostęp do elementów nadrzędnych w lokalizacjach, w których działanie nigdy nie zostanie wykonane. Ponadto zaimportowane elementy podrzędne, podobnie jak publiczne elementy podrzędne, mogą być przywoływane i zaplanowane przez implementację działania. Oznacza to, że działanie, które importuje działanie o nazwie zakończeniu, może zawierać element <xref:System.Activities.Statements.Sequence> w implementacji, który planuje zakończeniu.  
  
#### <a name="codeactivity-asynccodeactivity"></a>Elementu CodeActivity/Metoda AsyncCodeActivity  

 Ta klasa bazowa służy do tworzenia zachowań w kodzie bezwzględnym. Działania, które pochodzą z tej klasy, mają dostęp tylko do tych, które ujawniają. Oznacza to, że jedynymi elementami członkowskimi, które mogą uwidaczniać te działania, są argumenty publiczne. Żadne inne elementy członkowskie lub widoczności nie mają zastosowania do tych działań.  
  
#### <a name="summary-of-visibilities"></a>Podsumowanie widoczności  

 Poniższa tabela zawiera podsumowanie informacji znajdujących się wcześniej w tej sekcji.  
  
|Typ elementu członkowskiego|NativeActivity|Działanie|Elementu CodeActivity/Metoda AsyncCodeActivity|  
|-----------------|--------------------|--------------|--------------------------------------|  
|Argumenty|Publiczny/prywatny|Publiczne|nie dotyczy|  
|Zmienne|Publiczny/prywatny|Publiczne|nie dotyczy|  
|Działania podrzędne|Publiczny/prywatny|Publiczne, jeden stały prywatny element podrzędny zdefiniowany w implementacji.|nie dotyczy|  
|ActivityDelegate|Publiczny/prywatny|Publiczne|nie dotyczy|  
  
 Ogólnie rzecz biorąc, element członkowski, który nie może zostać ustawiony przez konsumenta działania, nie powinien być publiczny.  
  
### <a name="execution-properties"></a>Właściwości wykonania  

 W niektórych scenariuszach warto ograniczyć określoną właściwość wykonania do publicznych elementów podrzędnych działania. <xref:System.Activities.ExecutionProperties>Kolekcja zawiera tę możliwość przy użyciu <xref:System.Activities.ExecutionProperties.Add%2A> metody. Ta metoda ma parametr logiczny wskazujący, czy określona właściwość jest objęta zakresem do wszystkich elementów podrzędnych, czy tylko te, które są publiczne. Jeśli ten parametr jest ustawiony na `true` , właściwość będzie widoczna tylko dla członków publicznych i publicznych elementów podrzędnych.  
  
### <a name="secondary-roots"></a>Pomocnicze elementy główne  

 Pomocniczy katalog główny to wewnętrzny mechanizm środowiska uruchomieniowego służący do zarządzania stanem działań związanych z kompensacją. Po <xref:System.Activities.Statements.CompensableActivity> zakończeniu działania jego stan nie jest czyszczony od razu. Zamiast tego stan jest obsługiwany przez środowisko uruchomieniowe w pomocniczym katalogu głównym do momentu zakończenia odcinka kompensacji. Środowiska lokalizacji przechwycone z pomocniczym katalogiem głównym odpowiadają zakresowi definicji, w której używane jest działanie kompensacyjne.
