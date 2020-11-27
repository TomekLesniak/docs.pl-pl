---
title: 'Instrukcje: tworzenie podstawowego kanału informacyjnego RSS'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 431879b8-a5f8-4947-ad1e-4768c726aca8
ms.openlocfilehash: d322dd40fd024685d6f3236caed41ae5eec1f375
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256810"
---
# <a name="how-to-create-a-basic-rss-feed"></a><span data-ttu-id="ba252-102">Instrukcje: tworzenie podstawowego kanału informacyjnego RSS</span><span class="sxs-lookup"><span data-stu-id="ba252-102">How to: Create a Basic RSS Feed</span></span>

<span data-ttu-id="ba252-103">Windows Communication Foundation (WCF) umożliwia utworzenie usługi, która uwidacznia zespolone źródło danych.</span><span class="sxs-lookup"><span data-stu-id="ba252-103">Windows Communication Foundation (WCF) allows you to create a service that exposes a syndication feed.</span></span> <span data-ttu-id="ba252-104">W tym temacie omówiono sposób tworzenia usługi zespolonej, która uwidacznia kanał informacyjny zespolonej RSS.</span><span class="sxs-lookup"><span data-stu-id="ba252-104">This topic discusses how to create a syndication service that exposes an RSS syndication feed.</span></span>  
  
### <a name="to-create-a-basic-syndication-service"></a><span data-ttu-id="ba252-105">Aby utworzyć podstawową usługę zespalania</span><span class="sxs-lookup"><span data-stu-id="ba252-105">To create a basic syndication service</span></span>  
  
1. <span data-ttu-id="ba252-106">Zdefiniuj kontrakt usługi przy użyciu interfejsu oznaczonego <xref:System.ServiceModel.Web.WebGetAttribute> atrybutem.</span><span class="sxs-lookup"><span data-stu-id="ba252-106">Define a service contract using an interface marked with the <xref:System.ServiceModel.Web.WebGetAttribute> attribute.</span></span> <span data-ttu-id="ba252-107">Każda operacja, która jest udostępniana jako zespolone źródło danych, powinna zwracać <xref:System.ServiceModel.Syndication.Rss20FeedFormatter> obiekt.</span><span class="sxs-lookup"><span data-stu-id="ba252-107">Each operation that is exposed as a syndication feed should return a <xref:System.ServiceModel.Syndication.Rss20FeedFormatter> object.</span></span>  
  
     [!code-csharp[htRssBasic#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#0)]
     [!code-vb[htRssBasic#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#0)]  
  
    > [!NOTE]
    > <span data-ttu-id="ba252-108">Wszystkie operacje usługi, które stosują ten <xref:System.ServiceModel.Web.WebGetAttribute> atrybut są mapowane na żądania HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="ba252-108">All service operations that apply the <xref:System.ServiceModel.Web.WebGetAttribute> attribute are mapped to HTTP GET requests.</span></span> <span data-ttu-id="ba252-109">Aby zmapować operację na inną metodę HTTP, użyj <xref:System.ServiceModel.Web.WebInvokeAttribute> zamiast niego.</span><span class="sxs-lookup"><span data-stu-id="ba252-109">To map your operation to a different HTTP method, use the <xref:System.ServiceModel.Web.WebInvokeAttribute> instead.</span></span> <span data-ttu-id="ba252-110">Aby uzyskać więcej informacji, zobacz [How to: Create a Basic Internet http Web Service](how-to-create-a-basic-wcf-web-http-service.md).</span><span class="sxs-lookup"><span data-stu-id="ba252-110">For more information, see [How to: Create a Basic WCF Web HTTP Service](how-to-create-a-basic-wcf-web-http-service.md).</span></span>  
  
2. <span data-ttu-id="ba252-111">Zaimplementuj kontrakt usługi.</span><span class="sxs-lookup"><span data-stu-id="ba252-111">Implement the service contract.</span></span>  
  
     [!code-csharp[htRssBasic#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#1)]
     [!code-vb[htRssBasic#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#1)]  
  
3. <span data-ttu-id="ba252-112">Utwórz <xref:System.ServiceModel.Syndication.SyndicationFeed> obiekt i Dodaj autora, kategorię i opis.</span><span class="sxs-lookup"><span data-stu-id="ba252-112">Create a <xref:System.ServiceModel.Syndication.SyndicationFeed> object and add an author, category, and description.</span></span>  
  
     [!code-csharp[htRssBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#2)]
     [!code-vb[htRssBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#2)]  
  
4. <span data-ttu-id="ba252-113">Utwórz kilka <xref:System.ServiceModel.Syndication.SyndicationItem> obiektów.</span><span class="sxs-lookup"><span data-stu-id="ba252-113">Create several <xref:System.ServiceModel.Syndication.SyndicationItem> objects.</span></span>  
  
     [!code-csharp[htRssBasic#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#3)]
     [!code-vb[htRssBasic#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#3)]  
  
5. <span data-ttu-id="ba252-114">Dodaj <xref:System.ServiceModel.Syndication.SyndicationItem> do źródła danych.</span><span class="sxs-lookup"><span data-stu-id="ba252-114">Add the <xref:System.ServiceModel.Syndication.SyndicationItem> to the feed.</span></span>  
  
     [!code-csharp[htRssBasic#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#4)]
     [!code-vb[htRssBasic#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#4)]  
  
6. <span data-ttu-id="ba252-115">Zwróć źródło danych.</span><span class="sxs-lookup"><span data-stu-id="ba252-115">Return the feed.</span></span>  
  
     [!code-csharp[htRssBasic#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#5)]
     [!code-vb[htRssBasic#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#5)]  
  
### <a name="to-host-a-service"></a><span data-ttu-id="ba252-116">Aby hostować usługę</span><span class="sxs-lookup"><span data-stu-id="ba252-116">To host a service</span></span>  
  
1. <span data-ttu-id="ba252-117">Utwórz <xref:System.ServiceModel.Web.WebServiceHost> obiekt.</span><span class="sxs-lookup"><span data-stu-id="ba252-117">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span>  
  
     [!code-csharp[htRssBasic#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#6)]
     [!code-vb[htRssBasic#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#6)]  
  
2. <span data-ttu-id="ba252-118">Otwórz hosta usługi i poczekaj, aż użytkownik naciśnie klawisz ENTER.</span><span class="sxs-lookup"><span data-stu-id="ba252-118">Open the service host and wait until the user presses ENTER.</span></span>  
  
     [!code-csharp[htRssBasic#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#8)]
     [!code-vb[htRssBasic#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#8)]  
  
### <a name="to-call-getblog-with-an-http-get"></a><span data-ttu-id="ba252-119">Aby wywołać metodę getblog () przy użyciu protokołu HTTP GET</span><span class="sxs-lookup"><span data-stu-id="ba252-119">To call GetBlog() with an HTTP GET</span></span>  
  
1. <span data-ttu-id="ba252-120">Otwórz program Internet Explorer, wpisz następujący adres URL, a następnie naciśnij klawisz ENTER: `http://localhost:8000/BlogService/GetBlog` .</span><span class="sxs-lookup"><span data-stu-id="ba252-120">Open Internet Explorer, type the following URL, and press ENTER: `http://localhost:8000/BlogService/GetBlog`.</span></span> <span data-ttu-id="ba252-121">Adres URL zawiera adres podstawowy usługi ( `http://localhost:8000/BlogService` ), adres względny punktu końcowego i operację usługi do wywołania.</span><span class="sxs-lookup"><span data-stu-id="ba252-121">The URL contains the base address of the service (`http://localhost:8000/BlogService`), the relative address of the endpoint, and the service operation to call.</span></span>  
  
### <a name="to-call-getblog-from-code"></a><span data-ttu-id="ba252-122">Aby wywołać metodę getblog () z kodu</span><span class="sxs-lookup"><span data-stu-id="ba252-122">To call GetBlog() from code</span></span>  
  
1. <span data-ttu-id="ba252-123">Utwórz <xref:System.Xml.XmlReader> z adresem podstawowym i metodą, którą wywołujesz.</span><span class="sxs-lookup"><span data-stu-id="ba252-123">Create an <xref:System.Xml.XmlReader> with the base address and the method you are calling.</span></span>  
  
     [!code-csharp[htRssBasic#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#9)]
     [!code-vb[htRssBasic#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#9)]  
  
2. <span data-ttu-id="ba252-124">Wywołaj metodę statyczną <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> , przekazując w <xref:System.Xml.XmlReader> właśnie utworzony sposób.</span><span class="sxs-lookup"><span data-stu-id="ba252-124">Call the static <xref:System.ServiceModel.Syndication.SyndicationFeed.Load%28System.Xml.XmlReader%29> method, passing in the <xref:System.Xml.XmlReader> you just created.</span></span>  
  
     [!code-csharp[htRssBasic#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#10)]
     [!code-vb[htRssBasic#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#10)]  
  
     <span data-ttu-id="ba252-125">Spowoduje to wywołanie operacji usługi i wypełnienie nowej <xref:System.ServiceModel.Syndication.SyndicationFeed> z programem formatującego zwróconym przez operację usługi.</span><span class="sxs-lookup"><span data-stu-id="ba252-125">This invokes the service operation and populates a new <xref:System.ServiceModel.Syndication.SyndicationFeed> with the formatter returned from the service operation.</span></span>  
  
3. <span data-ttu-id="ba252-126">Dostęp do obiektu źródła danych.</span><span class="sxs-lookup"><span data-stu-id="ba252-126">Access the feed object.</span></span>  
  
     [!code-csharp[htRssBasic#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/snippets.cs#11)]
     [!code-vb[htRssBasic#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/snippets.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="ba252-127">Przykład</span><span class="sxs-lookup"><span data-stu-id="ba252-127">Example</span></span>  

 <span data-ttu-id="ba252-128">Poniżej znajduje się pełna lista kodów dla tego przykładu.</span><span class="sxs-lookup"><span data-stu-id="ba252-128">The following is the full code listing for this example.</span></span>  
  
 [!code-csharp[htRssBasic#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/htrssbasic/cs/program.cs#12)]
 [!code-vb[htRssBasic#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htrssbasic/vb/program.vb#12)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ba252-129">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="ba252-129">Compiling the Code</span></span>  

 <span data-ttu-id="ba252-130">Podczas kompilowania powyższego kodu odwołuje się System.ServiceModel.dll i System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="ba252-130">When compiling the preceding code, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba252-131">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="ba252-131">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
