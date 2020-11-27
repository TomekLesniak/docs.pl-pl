---
title: Używanie edytora wyrażeń niestandardowych
ms.date: 03/30/2017
ms.assetid: 0901b58b-e037-44a8-8281-f6f54361cfca
ms.openlocfilehash: e33e804d73239794a7f9cf9f3c28c3808f8b963e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293315"
---
# <a name="using-a-custom-expression-editor"></a><span data-ttu-id="c588b-102">Używanie edytora wyrażeń niestandardowych</span><span class="sxs-lookup"><span data-stu-id="c588b-102">Using a Custom Expression Editor</span></span>

<span data-ttu-id="c588b-103">Edytor wyrażeń niestandardowych można zaimplementować, aby zapewnić bogatsze lub prostsze środowisko edytowania wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="c588b-103">A custom expression editor can be implemented to provide a richer or simpler expression editing experience.</span></span> <span data-ttu-id="c588b-104">Istnieje kilka scenariuszy, w których warto użyć niestandardowego edytora wyrażeń:</span><span class="sxs-lookup"><span data-stu-id="c588b-104">There are several scenarios in which you might want to use a custom expression editor:</span></span>  
  
- <span data-ttu-id="c588b-105">Aby zapewnić obsługę technologii IntelliSense i innych zaawansowanych funkcji edycji w zaobsługiwanym Projektancie przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="c588b-105">To provide support for IntelliSense and other rich editing features in a rehosted workflow designer.</span></span> <span data-ttu-id="c588b-106">Należy podać tę funkcję, ponieważ domyślny Edytor wyrażeń programu Visual Studio nie może być używany w aplikacjach przewidzianych do przehostowania.</span><span class="sxs-lookup"><span data-stu-id="c588b-106">This functionality must be provided because the default Visual Studio expression editor cannot be used in rehosted applications.</span></span>  
  
- <span data-ttu-id="c588b-107">Aby uprościć środowisko edytowania wyrażeń dla użytkowników analityków firmy, tak aby nie były na przykład wymagane do uczenia się Visual Basic lub postępowania z wyrażeniami Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c588b-107">To simplify the expression editing experience for the business analyst users, so that they are not, for example, required to learn Visual Basic or deal with Visual Basic expressions.</span></span>  
  
 <span data-ttu-id="c588b-108">Do zaimplementowania niestandardowego edytora wyrażeń są wymagane trzy podstawowe kroki:</span><span class="sxs-lookup"><span data-stu-id="c588b-108">Three basic steps are needed to implement a custom expression editor:</span></span>  
  
1. <span data-ttu-id="c588b-109">Zaimplementuj interfejs <xref:System.Activities.Presentation.View.IExpressionEditorService>.</span><span class="sxs-lookup"><span data-stu-id="c588b-109">Implement the <xref:System.Activities.Presentation.View.IExpressionEditorService> interface.</span></span> <span data-ttu-id="c588b-110">Ten interfejs zarządza tworzeniem i zniszczeniem edytorów wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="c588b-110">This interface manages the creation and destruction of expression editors.</span></span>  
  
2. <span data-ttu-id="c588b-111">Zaimplementuj interfejs <xref:System.Activities.Presentation.View.IExpressionEditorInstance>.</span><span class="sxs-lookup"><span data-stu-id="c588b-111">Implement the <xref:System.Activities.Presentation.View.IExpressionEditorInstance> interface.</span></span> <span data-ttu-id="c588b-112">Ten interfejs implementuje interfejs użytkownika dla interfejsu użytkownika do edycji wyrażeń.</span><span class="sxs-lookup"><span data-stu-id="c588b-112">This interface implements the UI for expression editing UI.</span></span>  
  
3. <span data-ttu-id="c588b-113">Opublikuj <xref:System.Activities.Presentation.View.IExpressionEditorService> w aplikacji przehostowanej przepływ pracy.</span><span class="sxs-lookup"><span data-stu-id="c588b-113">Publish the <xref:System.Activities.Presentation.View.IExpressionEditorService> in your rehosted workflow application.</span></span>  
  
## <a name="implementing-a-custom-expression-editor-in-a-class-library"></a><span data-ttu-id="c588b-114">Implementowanie niestandardowego edytora wyrażeń w bibliotece klas</span><span class="sxs-lookup"><span data-stu-id="c588b-114">Implementing a Custom Expression Editor in a Class Library</span></span>  

 <span data-ttu-id="c588b-115">Oto przykład kodu dla klasy (dowód koncepcji) `MyEditorService` implementującej <xref:System.Activities.Presentation.View.IExpressionEditorService> interfejs jest zawarty w projekcie biblioteki MyExpressionEditorService.</span><span class="sxs-lookup"><span data-stu-id="c588b-115">Here is a sample of code for a (proof of concept) `MyEditorService` class that implements the <xref:System.Activities.Presentation.View.IExpressionEditorService> interface is contained in a MyExpressionEditorService library project.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Activities.Presentation.View;  
using System.Activities.Presentation.Hosting;  
using System.Activities.Presentation.Model;  
  
namespace MyExpressionEditorService  
{  
    public class MyEditorService : IExpressionEditorService  
    {  
        public void CloseExpressionEditors()  
        {  
  
        }  
        public IExpressionEditorInstance CreateExpressionEditor(AssemblyContextControlItem assemblies, ImportedNamespaceContextItem importedNamespaces, List<ModelItem> variables, string text)  
        {  
            MyExpressionEditorInstance instance = new MyExpressionEditorInstance();  
            return instance;  
        }  
        public IExpressionEditorInstance CreateExpressionEditor(AssemblyContextControlItem assemblies, ImportedNamespaceContextItem importedNamespaces, List<ModelItem> variables, string text, System.Windows.Size initialSize)  
                {  
            MyExpressionEditorInstance instance = new MyExpressionEditorInstance();  
            return instance;  
        }  
        public IExpressionEditorInstance CreateExpressionEditor(AssemblyContextControlItem assemblies, ImportedNamespaceContextItem importedNamespaces, List<ModelItem> variables, string text, Type expressionType)  
            {  
            MyExpressionEditorInstance instance = new MyExpressionEditorInstance();  
            return instance;  
        }  
        public IExpressionEditorInstance CreateExpressionEditor(AssemblyContextControlItem assemblies, ImportedNamespaceContextItem importedNamespaces, List<ModelItem> variables, string text, Type expressionType, System.Windows.Size initialSize)  
        {  
            MyExpressionEditorInstance instance = new MyExpressionEditorInstance();  
            return instance;  
        }  
        public void UpdateContext(AssemblyContextControlItem assemblies, ImportedNamespaceContextItem importedNamespaces)  
        {  
  
        }  
  
    }  
}  
```  
  
 <span data-ttu-id="c588b-116">Oto kod `MyExpressionEditorInstance` klasy implementującej <xref:System.Activities.Presentation.View.IExpressionEditorInstance> interfejs w projekcie biblioteki MyExpressionEditorService.</span><span class="sxs-lookup"><span data-stu-id="c588b-116">Here is the code for a `MyExpressionEditorInstance` class that implements the <xref:System.Activities.Presentation.View.IExpressionEditorInstance> interface in a MyExpressionEditorService library project.</span></span>  
  
```csharp  
using System;  
using System.Activities.Presentation.View;  
using System.Windows;  
using System.Reflection;  
using System.Windows.Controls;  
  
namespace MyExpressionEditorService  
{  
    public class MyExpressionEditorInstance : IExpressionEditorInstance  
    {  
        private TextBox textBox = new TextBox();  
  
        public bool AcceptsReturn { get; set; }  
        public bool AcceptsTab { get; set; }  
        public bool HasAggregateFocus {  
            get  
            {  
                return true;  
            }  
        }  
  
        public System.Windows.Controls.ScrollBarVisibility HorizontalScrollBarVisibility { get; set; }  
        public System.Windows.Controls.Control HostControl {  
            get  
            {  
                return textBox;  
            }  
        }  
        public int MaxLines { get; set; }  
        public int MinLines { get; set; }  
        public string Text { get; set; }  
        public System.Windows.Controls.ScrollBarVisibility VerticalScrollBarVisibility { get; set; }  
  
        public event EventHandler Closing;  
        public event EventHandler GotAggregateFocus;  
        public event EventHandler LostAggregateFocus;  
        public event EventHandler TextChanged;  
  
        public bool CanCompleteWord()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanCopy()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanCut()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanDecreaseFilterLevel()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanGlobalIntellisense()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanIncreaseFilterLevel()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanParameterInfo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanPaste()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanQuickInfo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanRedo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool CanUndo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
  
        public void ClearSelection()  
        {  
            MessageBox.Show(MethodBase.GetCurrentMethod().Name);  
        }  
        public void Close()  
        {  
            MessageBox.Show(MethodBase.GetCurrentMethod().Name);  
        }  
        public bool CompleteWord()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool Copy()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool Cut()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool DecreaseFilterLevel()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public void Focus()  
        {  
            MessageBox.Show(MethodBase.GetCurrentMethod().Name);  
        }  
        public string GetCommittedText()  
        {  
            return "CommittedText";  
        }  
        public bool GlobalIntellisense()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool IncreaseFilterLevel()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool ParameterInfo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool Paste()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool QuickInfo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool Redo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
        public bool Undo()  
        {  
            return (MessageBox.Show(MethodBase.GetCurrentMethod().Name, "TestEditorInstance", MessageBoxButton.YesNo) == MessageBoxResult.Yes);  
        }  
    }  
}  
```  
  
### <a name="publishing-a-custom-expression-editor-in-a-wpf-project"></a><span data-ttu-id="c588b-117">Publikowanie edytora wyrażeń niestandardowych w projekcie WPF</span><span class="sxs-lookup"><span data-stu-id="c588b-117">Publishing a Custom Expression Editor in a WPF Project</span></span>  

 <span data-ttu-id="c588b-118">Oto kod, który pokazuje, jak ponownie hostować projektanta w aplikacji WPF i jak utworzyć i opublikować `MyEditorService` usługę.</span><span class="sxs-lookup"><span data-stu-id="c588b-118">Here is the code that shows how to rehost the designer in a WPF application and how to create and publish the `MyEditorService` service.</span></span> <span data-ttu-id="c588b-119">Przed użyciem tego kodu, Dodaj odwołanie do projektu biblioteki MyExpressionEditorService z projektu, który zawiera aplikację avalon2.</span><span class="sxs-lookup"><span data-stu-id="c588b-119">Before using this code, add a reference to the MyExpressionEditorService library project from the project that contains the avalon2 application.</span></span>  
  
```csharp  
using System.Windows;  
using System.Windows.Controls;  
using System.Activities.Presentation;  
using System.Activities.Statements;  
using System.Activities.Core.Presentation;  
using System.Activities.Presentation.View;  
using MyExpressionEditorService;  
  
namespace WpfApplication1  
{  
    /// <summary>  
    /// Interaction logic for MainWindow.xaml  
    /// </summary>  
    public partial class MainWindow : Window  
    {  
  
        private MyEditorService expressionEditorService;  
        public MainWindow()  
        {  
            InitializeComponent();  
            new DesignerMetadata().Register();  
            createDesigner();  
        }  
  
        public void createDesigner()  
        {  
            WorkflowDesigner designer = new WorkflowDesigner();  
            Sequence root = new Sequence()  
            {  
                Activities = {  
                new Assign(),  
                new WriteLine()}  
            };  
  
            designer.Load(root);  
  
            Grid.SetColumn(designer.View, 0);  
  
            // Create ExpressionEditorService
            this.expressionEditorService = new MyEditorService();  
  
            // Publish the instance of MyEditorService.  
            designer.Context.Services.Publish<IExpressionEditorService>(this.expressionEditorService);  
  
            MyGrid.Children.Add(designer.View);  
        }  
    }  
}  
```  
  
### <a name="notes"></a><span data-ttu-id="c588b-120">Uwagi</span><span class="sxs-lookup"><span data-stu-id="c588b-120">Notes</span></span>  

 <span data-ttu-id="c588b-121">Jeśli używasz formantu **ExpressionTextBox** w projektancie działań niestandardowych, nie trzeba tworzyć i niszczyć edytorów wyrażeń przy użyciu <xref:System.Activities.Presentation.View.IExpressionEditorService.CreateExpressionEditor%2A> <xref:System.Activities.Presentation.View.IExpressionEditorService.CloseExpressionEditors%2A> metod i <xref:System.Activities.Presentation.View.IExpressionEditorService> interfejsu.</span><span class="sxs-lookup"><span data-stu-id="c588b-121">If you are using an **ExpressionTextBox** control in a custom activity designer, it is not necessary to create and destroy expression editors using the <xref:System.Activities.Presentation.View.IExpressionEditorService.CreateExpressionEditor%2A> and <xref:System.Activities.Presentation.View.IExpressionEditorService.CloseExpressionEditors%2A> methods of the <xref:System.Activities.Presentation.View.IExpressionEditorService> interface.</span></span> <span data-ttu-id="c588b-122">Klasa jest w <xref:System.Activities.Presentation.View.ExpressionTextBox> tej usłudze zarządzana.</span><span class="sxs-lookup"><span data-stu-id="c588b-122">The <xref:System.Activities.Presentation.View.ExpressionTextBox> class manages this for you.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c588b-123">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="c588b-123">See also</span></span>

- <xref:System.Activities.Presentation.View.IExpressionEditorService>
- <xref:System.Activities.Presentation.View.IExpressionEditorInstance>
- [<span data-ttu-id="c588b-124">Używanie elementu ExpressionTextBox w projektancie działań niestandardowych</span><span class="sxs-lookup"><span data-stu-id="c588b-124">Using the ExpressionTextBox in a Custom Activity Designer</span></span>](./samples/using-the-expressiontextbox-in-a-custom-activity-designer.md)
