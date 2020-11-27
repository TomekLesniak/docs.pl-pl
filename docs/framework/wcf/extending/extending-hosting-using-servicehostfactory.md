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
# <a name="extending-hosting-using-servicehostfactory"></a><span data-ttu-id="59320-102">Rozszerzanie hostingu za pomocą elementu ServiceHostFactory</span><span class="sxs-lookup"><span data-stu-id="59320-102">Extending Hosting Using ServiceHostFactory</span></span>

<span data-ttu-id="59320-103">Standardowy <xref:System.ServiceModel.ServiceHost> interfejs API dla usług hostingu w programie Windows Communication Foundation (WCF) to punkt rozszerzalności architektury WCF.</span><span class="sxs-lookup"><span data-stu-id="59320-103">The standard <xref:System.ServiceModel.ServiceHost> API for hosting services in Windows Communication Foundation (WCF) is an extensibility point in the WCF architecture.</span></span> <span data-ttu-id="59320-104">Użytkownicy mogą utworzyć własne klasy hosta z <xref:System.ServiceModel.ServiceHost> , zwykle przesłonić, aby <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> <xref:System.ServiceModel.Description.ServiceDescription> dodać domyślne punkty końcowe lub zmodyfikować zachowania przed otwarciem usługi.</span><span class="sxs-lookup"><span data-stu-id="59320-104">Users can derive their own host classes from <xref:System.ServiceModel.ServiceHost>, usually to override <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> to use <xref:System.ServiceModel.Description.ServiceDescription> to add default endpoints imperatively or modify behaviors, prior to opening the service.</span></span>  
  
 <span data-ttu-id="59320-105">W środowisku samoobsługowym nie trzeba tworzyć niestandardowych, <xref:System.ServiceModel.ServiceHost> ponieważ piszesz kod tworzący wystąpienie hosta, a następnie Wywołaj <xref:System.ServiceModel.ICommunicationObject.Open> go po utworzeniu jego wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="59320-105">In the self-host environment, you do not have to create a custom <xref:System.ServiceModel.ServiceHost> because you write the code that instantiates the host and then call <xref:System.ServiceModel.ICommunicationObject.Open> on it after you instantiate it.</span></span> <span data-ttu-id="59320-106">Między tymi dwoma krokami możesz wykonać dowolną czynność.</span><span class="sxs-lookup"><span data-stu-id="59320-106">Between those two steps you can do whatever you want.</span></span> <span data-ttu-id="59320-107">Możesz na przykład dodać nowy <xref:System.ServiceModel.Description.IServiceBehavior> :</span><span class="sxs-lookup"><span data-stu-id="59320-107">You could, for example, add a new <xref:System.ServiceModel.Description.IServiceBehavior>:</span></span>  
  
```csharp
public static void Main()  
{  
   ServiceHost host = new ServiceHost( typeof( MyService ) );  
   host.Description.Add( new MyServiceBehavior() );  
   host.Open();  
  
   ...  
}  
```  
  
 <span data-ttu-id="59320-108">Ta metoda nie jest wielokrotnego użytku.</span><span class="sxs-lookup"><span data-stu-id="59320-108">This approach is not reusable.</span></span> <span data-ttu-id="59320-109">Kod, który operuje na opisie, jest kodowany w programie hosta (w tym przypadku funkcji Main ()), więc trudno jest ponownie użyć tej logiki w innych kontekstach.</span><span class="sxs-lookup"><span data-stu-id="59320-109">The code that manipulates the description is coded into the host program (in this case, the Main() function), so it is difficult to reuse that logic in other contexts.</span></span> <span data-ttu-id="59320-110">Istnieją także inne sposoby dodawania <xref:System.ServiceModel.Description.IServiceBehavior> , które nie wymagają bezwzględnego kodu.</span><span class="sxs-lookup"><span data-stu-id="59320-110">There are also other ways of adding an <xref:System.ServiceModel.Description.IServiceBehavior> that do not require imperative code.</span></span> <span data-ttu-id="59320-111">Można utworzyć atrybut z <xref:System.ServiceModel.ServiceBehaviorAttribute> i umieścić go w typie implementacji usługi lub można skonfigurować zachowanie niestandardowe i utworzyć je dynamicznie za pomocą konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="59320-111">You can derive an attribute from <xref:System.ServiceModel.ServiceBehaviorAttribute> and put that on your service implementation type or you can make a custom behavior configurable and compose it dynamically using configuration.</span></span>  
  
 <span data-ttu-id="59320-112">Jednak w celu rozwiązania tego problemu można także użyć niewielkiej zmiany przykładu.</span><span class="sxs-lookup"><span data-stu-id="59320-112">However, a slight variation of the example can also be used to solve this problem.</span></span> <span data-ttu-id="59320-113">Jednym z metod jest przeniesienie kodu, który dodaje ServiceBehavior z `Main()` i do <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> metody niestandardowej pochodnej <xref:System.ServiceModel.ServiceHost> :</span><span class="sxs-lookup"><span data-stu-id="59320-113">One approach is to move the code that adds the ServiceBehavior out of `Main()` and into the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> method of a custom derivative of <xref:System.ServiceModel.ServiceHost>:</span></span>  
  
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
  
 <span data-ttu-id="59320-114">Następnie w programie można `Main()` użyć:</span><span class="sxs-lookup"><span data-stu-id="59320-114">Then, inside of `Main()` you can use:</span></span>  
  
```csharp
public static void Main()  
{  
   ServiceHost host = new DerivedHost( typeof( MyService ) );  
   host.Open();  
  
   ...  
}  
```  
  
 <span data-ttu-id="59320-115">Teraz hermetyzowamy logikę niestandardową do czystego abstrakcji, którą można łatwo ponownie wykorzystać w wielu różnych plikach wykonywalnych hosta.</span><span class="sxs-lookup"><span data-stu-id="59320-115">Now you have encapsulated the custom logic into a clean abstraction that can be easily reused across many different host executables.</span></span>  
  
 <span data-ttu-id="59320-116">Nie jest od razu oczywisty sposób użycia tego <xref:System.ServiceModel.ServiceHost> elementu niestandardowego z wewnątrz Internet Information Services (IIS) lub usługi aktywacji procesów systemu Windows (was).</span><span class="sxs-lookup"><span data-stu-id="59320-116">It is not immediately obvious how to use this custom <xref:System.ServiceModel.ServiceHost> from inside of Internet Information Services (IIS) or Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="59320-117">Te środowiska są inne niż środowisko samoobsługowe, ponieważ środowisko hostingu jest jednym wystąpieniem <xref:System.ServiceModel.ServiceHost> w imieniu aplikacji.</span><span class="sxs-lookup"><span data-stu-id="59320-117">Those environments are different than the self-host environment, because the hosting environment is the one instantiating the <xref:System.ServiceModel.ServiceHost> on behalf of the application.</span></span> <span data-ttu-id="59320-118">Infrastruktury usług IIS i WAS nie wiedzą o Twoich niestandardowych <xref:System.ServiceModel.ServiceHost> instrumentach pochodnych.</span><span class="sxs-lookup"><span data-stu-id="59320-118">The IIS and WAS hosting infrastructure does not know anything about your custom <xref:System.ServiceModel.ServiceHost> derivative.</span></span>  
  
 <span data-ttu-id="59320-119"><xref:System.ServiceModel.Activation.ServiceHostFactory>Została zaprojektowana w celu rozwiązania tego problemu z uzyskaniem dostępu do niestandardowego <xref:System.ServiceModel.ServiceHost> z poziomu usług IIS lub was.</span><span class="sxs-lookup"><span data-stu-id="59320-119">The <xref:System.ServiceModel.Activation.ServiceHostFactory> was designed to solve this problem of accessing your custom <xref:System.ServiceModel.ServiceHost> from within IIS or WAS.</span></span> <span data-ttu-id="59320-120">Ponieważ Host niestandardowy pochodzący z programu <xref:System.ServiceModel.ServiceHost> jest dynamicznie konfigurowany i potencjalnie różne typy, środowisko hostingu nigdy nie tworzy jego bezpośrednio.</span><span class="sxs-lookup"><span data-stu-id="59320-120">Because a custom host that is derived from <xref:System.ServiceModel.ServiceHost> is dynamically configured and potentially of various types, the hosting environment never instantiates it directly.</span></span> <span data-ttu-id="59320-121">Zamiast tego, WCF używa wzorca fabryki, aby zapewnić warstwę pośrednią między środowiskiem hostingu a konkretnym typem usługi.</span><span class="sxs-lookup"><span data-stu-id="59320-121">Instead, WCF uses a factory pattern to provide a layer of indirection between the hosting environment and the concrete type of the service.</span></span> <span data-ttu-id="59320-122">Jeśli użytkownik nie poinformuje inaczej, używa domyślnej implementacji <xref:System.ServiceModel.Activation.ServiceHostFactory> , która zwraca wystąpienie <xref:System.ServiceModel.ServiceHost> .</span><span class="sxs-lookup"><span data-stu-id="59320-122">Unless you tell it otherwise, it uses a default implementation of <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="59320-123">Ale można również udostępnić własną fabrykę, która zwraca hosta pochodnego, określając nazwę typu CLR implementacji fabryki w @ServiceHost dyrektywie.</span><span class="sxs-lookup"><span data-stu-id="59320-123">But you can also provide your own factory that returns your derived host by specifying the CLR type name of your factory implementation in the @ServiceHost directive.</span></span>  
  
 <span data-ttu-id="59320-124">Zamiarem jest to, że w przypadku podstawowych przypadków implementacja własnej fabryki powinna być prostym ćwiczeniem do przekazywania dalej.</span><span class="sxs-lookup"><span data-stu-id="59320-124">The intent is that for basic cases, implementing your own factory should be a straight forward exercise.</span></span> <span data-ttu-id="59320-125">Na przykład Oto niestandardowe, <xref:System.ServiceModel.Activation.ServiceHostFactory> które zwracają pochodną <xref:System.ServiceModel.ServiceHost> :</span><span class="sxs-lookup"><span data-stu-id="59320-125">For example, here is a custom <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns a derived <xref:System.ServiceModel.ServiceHost>:</span></span>  
  
```csharp
public class DerivedFactory : ServiceHostFactory  
{  
   public override ServiceHost CreateServiceHost( Type t, Uri[] baseAddresses )  
   {  
      return new DerivedHost( t, baseAddresses )  
   }  
}  
```  
  
 <span data-ttu-id="59320-126">Aby użyć tej fabryki zamiast domyślnej fabryki, podaj nazwę typu w @ServiceHost dyrektywie w następujący sposób:</span><span class="sxs-lookup"><span data-stu-id="59320-126">To use this factory instead of the default factory, provide the type name in the @ServiceHost directive as follows:</span></span>  
  
`<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>`  
  
 <span data-ttu-id="59320-127">Chociaż nie ma żadnego limitu technicznego dotyczącego działania, z którego chcesz <xref:System.ServiceModel.ServiceHost> <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A> korzystać, zalecamy, aby Twoje implementacje fabryki były proste, jak to możliwe.</span><span class="sxs-lookup"><span data-stu-id="59320-127">While there is no technical limit on doing what you want to the <xref:System.ServiceModel.ServiceHost> you return from <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A>, we suggest that you keep your factory implementations as simple as possible.</span></span> <span data-ttu-id="59320-128">Jeśli masz wiele logiki niestandardowej, lepiej jest umieścić tę logikę wewnątrz hosta, a nie wewnątrz fabryki, aby umożliwić jej wielokrotne używanie.</span><span class="sxs-lookup"><span data-stu-id="59320-128">If you have lots of custom logic, it is better to put that logic inside of your host instead of inside the factory so that it can be reusable.</span></span>  
  
 <span data-ttu-id="59320-129">Istnieje jeszcze jedna warstwa interfejsu API hostingu, która powinna zostać wymieniona w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="59320-129">There is one more layer to the hosting API that should be mentioned here.</span></span> <span data-ttu-id="59320-130">Funkcja WCF ma także <xref:System.ServiceModel.ServiceHostBase> i <xref:System.ServiceModel.Activation.ServiceHostFactoryBase> , z której są <xref:System.ServiceModel.ServiceHost> i <xref:System.ServiceModel.Activation.ServiceHostFactory> odpowiednio pochodne.</span><span class="sxs-lookup"><span data-stu-id="59320-130">WCF also has <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>, from which <xref:System.ServiceModel.ServiceHost> and <xref:System.ServiceModel.Activation.ServiceHostFactory> respectively derive.</span></span> <span data-ttu-id="59320-131">Istnieją one w przypadku bardziej zaawansowanych scenariuszy, w których należy wymienić duże części systemu metadanych przy użyciu własnych dostosowanych operacji tworzenia.</span><span class="sxs-lookup"><span data-stu-id="59320-131">Those exist for more advanced scenarios where you must swap out large parts of the metadata system with your own customized creations.</span></span>
