---
title: Rozszerzanie hostingu za pomocą elementu ServiceHostFactory
ms.date: 03/30/2017
ms.assetid: bcc5ae1b-21ce-4e0e-a184-17fad74a441e
ms.openlocfilehash: d2224ea683326679efdad368cf2ff7b2b95f4dba
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273129"
---
# <a name="extending-hosting-using-servicehostfactory"></a>Rozszerzanie hostingu za pomocą elementu ServiceHostFactory

Standardowy <xref:System.ServiceModel.ServiceHost> interfejs API dla usług hostingu w programie Windows Communication Foundation (WCF) to punkt rozszerzalności architektury WCF. Użytkownicy mogą utworzyć własne klasy hosta z <xref:System.ServiceModel.ServiceHost> , zwykle przesłonić, aby <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> <xref:System.ServiceModel.Description.ServiceDescription> dodać domyślne punkty końcowe lub zmodyfikować zachowania przed otwarciem usługi.  
  
 W środowisku samoobsługowym nie trzeba tworzyć niestandardowych, <xref:System.ServiceModel.ServiceHost> ponieważ piszesz kod tworzący wystąpienie hosta, a następnie Wywołaj <xref:System.ServiceModel.ICommunicationObject.Open> go po utworzeniu jego wystąpienia. Między tymi dwoma krokami możesz wykonać dowolną czynność. Możesz na przykład dodać nowy <xref:System.ServiceModel.Description.IServiceBehavior> :  
  
```csharp
public static void Main()  
{  
   ServiceHost host = new ServiceHost( typeof( MyService ) );  
   host.Description.Add( new MyServiceBehavior() );  
   host.Open();  
  
   ...  
}  
```  
  
 Ta metoda nie jest wielokrotnego użytku. Kod, który operuje na opisie, jest kodowany w programie hosta (w tym przypadku funkcji Main ()), więc trudno jest ponownie użyć tej logiki w innych kontekstach. Istnieją także inne sposoby dodawania <xref:System.ServiceModel.Description.IServiceBehavior> , które nie wymagają bezwzględnego kodu. Można utworzyć atrybut z <xref:System.ServiceModel.ServiceBehaviorAttribute> i umieścić go w typie implementacji usługi lub można skonfigurować zachowanie niestandardowe i utworzyć je dynamicznie za pomocą konfiguracji.  
  
 Jednak w celu rozwiązania tego problemu można także użyć niewielkiej zmiany przykładu. Jednym z metod jest przeniesienie kodu, który dodaje ServiceBehavior z `Main()` i do <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> metody niestandardowej pochodnej <xref:System.ServiceModel.ServiceHost> :  
  
```csharp
public class DerivedHost : ServiceHost  
{  
   public DerivedHost( Type t, params Uri baseAddresses ) :  
      base( t, baseAddresses ) {}  
  
   public override void OnOpening()  
   {  
  this.Description.Add( new MyServiceBehavior() );  
   }  
}  
```  
  
 Następnie w programie można `Main()` użyć:  
  
```csharp
public static void Main()  
{  
   ServiceHost host = new DerivedHost( typeof( MyService ) );  
   host.Open();  
  
   ...  
}  
```  
  
 Teraz hermetyzowamy logikę niestandardową do czystego abstrakcji, którą można łatwo ponownie wykorzystać w wielu różnych plikach wykonywalnych hosta.  
  
 Nie jest od razu oczywisty sposób użycia tego <xref:System.ServiceModel.ServiceHost> elementu niestandardowego z wewnątrz Internet Information Services (IIS) lub usługi aktywacji procesów systemu Windows (was). Te środowiska są inne niż środowisko samoobsługowe, ponieważ środowisko hostingu jest jednym wystąpieniem <xref:System.ServiceModel.ServiceHost> w imieniu aplikacji. Infrastruktury usług IIS i WAS nie wiedzą o Twoich niestandardowych <xref:System.ServiceModel.ServiceHost> instrumentach pochodnych.  
  
 <xref:System.ServiceModel.Activation.ServiceHostFactory>Została zaprojektowana w celu rozwiązania tego problemu z uzyskaniem dostępu do niestandardowego <xref:System.ServiceModel.ServiceHost> z poziomu usług IIS lub was. Ponieważ Host niestandardowy pochodzący z programu <xref:System.ServiceModel.ServiceHost> jest dynamicznie konfigurowany i potencjalnie różne typy, środowisko hostingu nigdy nie tworzy jego bezpośrednio. Zamiast tego, WCF używa wzorca fabryki, aby zapewnić warstwę pośrednią między środowiskiem hostingu a konkretnym typem usługi. Jeśli użytkownik nie poinformuje inaczej, używa domyślnej implementacji <xref:System.ServiceModel.Activation.ServiceHostFactory> , która zwraca wystąpienie <xref:System.ServiceModel.ServiceHost> . Ale można również udostępnić własną fabrykę, która zwraca hosta pochodnego, określając nazwę typu CLR implementacji fabryki w @ServiceHost dyrektywie.  
  
 Zamiarem jest to, że w przypadku podstawowych przypadków implementacja własnej fabryki powinna być prostym ćwiczeniem do przekazywania dalej. Na przykład Oto niestandardowe, <xref:System.ServiceModel.Activation.ServiceHostFactory> które zwracają pochodną <xref:System.ServiceModel.ServiceHost> :  
  
```csharp
public class DerivedFactory : ServiceHostFactory  
{  
   public override ServiceHost CreateServiceHost( Type t, Uri[] baseAddresses )  
   {  
      return new DerivedHost( t, baseAddresses )  
   }  
}  
```  
  
 Aby użyć tej fabryki zamiast domyślnej fabryki, podaj nazwę typu w @ServiceHost dyrektywie w następujący sposób:  
  
`<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>`  
  
 Chociaż nie ma żadnego limitu technicznego dotyczącego działania, z którego chcesz <xref:System.ServiceModel.ServiceHost> <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A> korzystać, zalecamy, aby Twoje implementacje fabryki były proste, jak to możliwe. Jeśli masz wiele logiki niestandardowej, lepiej jest umieścić tę logikę wewnątrz hosta, a nie wewnątrz fabryki, aby umożliwić jej wielokrotne używanie.  
  
 Istnieje jeszcze jedna warstwa interfejsu API hostingu, która powinna zostać wymieniona w tym miejscu. Funkcja WCF ma także <xref:System.ServiceModel.ServiceHostBase> i <xref:System.ServiceModel.Activation.ServiceHostFactoryBase> , z której są <xref:System.ServiceModel.ServiceHost> i <xref:System.ServiceModel.Activation.ServiceHostFactory> odpowiednio pochodne. Istnieją one w przypadku bardziej zaawansowanych scenariuszy, w których należy wymienić duże części systemu metadanych przy użyciu własnych dostosowanych operacji tworzenia.
