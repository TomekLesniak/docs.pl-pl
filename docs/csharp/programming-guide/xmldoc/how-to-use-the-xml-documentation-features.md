---
title: Jak korzystać z funkcji dokumentacji XML — Przewodnik programowania w języku C#
description: Dowiedz się, jak korzystać z funkcji dokumentacji XML. Zobacz przykłady kodu i Wyświetl dodatkowe dostępne zasoby.
ms.date: 06/01/2018
helpviewer_keywords:
- XML documentation [C#]
- C# language, XML documentation features
ms.assetid: 8f33917b-9577-4c9a-818a-640dbbb0b399
ms.openlocfilehash: 9ad2cfe62c70174eec9020ad4c8ce11608aca36d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380673"
---
# <a name="how-to-use-the-xml-documentation-features"></a><span data-ttu-id="e3e77-104">Używanie funkcji dokumentacji XML</span><span class="sxs-lookup"><span data-stu-id="e3e77-104">How to use the XML documentation features</span></span>

<span data-ttu-id="e3e77-105">Poniższy przykład zawiera podstawowe Omówienie typu, który został udokumentowany.</span><span class="sxs-lookup"><span data-stu-id="e3e77-105">The following sample provides a basic overview of a type that has been documented.</span></span>

## <a name="example"></a><span data-ttu-id="e3e77-106">Przykład</span><span class="sxs-lookup"><span data-stu-id="e3e77-106">Example</span></span>

[!code-csharp[csProgGuideDocComments#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#15)]

<span data-ttu-id="e3e77-107">Przykład generuje plik *. XML* o następującej zawartości.</span><span class="sxs-lookup"><span data-stu-id="e3e77-107">The example generates an *.xml* file with the following contents.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>xmlsample</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            <summary>
            Class level summary documentation goes here.
            </summary>
            <remarks>
            Longer comments can be associated with a type or member through
            the remarks tag.
            </remarks>
        </member>
        <member name="F:TestClass._name">
            <summary>
            Store for the Name property.
            </summary>
        </member>
        <member name="M:TestClass.#ctor">
            <summary>
            The class constructor.
            </summary>
        </member>
        <member name="P:TestClass.Name">
            <summary>
            Name property.
            </summary>
            <value>
            A value tag is used to describe the property value.
            </value>
        </member>
        <member name="M:TestClass.SomeMethod(System.String)">
            <summary>
            Description for SomeMethod.
            </summary>
            <param name="s"> Parameter description for s goes here.</param>
            <seealso cref="T:System.String">
            You can use the cref attribute on any tag to reference a type or member
            and the compiler will check that the reference exists.
            </seealso>
        </member>
        <member name="M:TestClass.SomeOtherMethod">
            <summary>
            Some other method.
            </summary>
            <returns>
            Return values are described through the returns tag.
            </returns>
            <seealso cref="M:TestClass.SomeMethod(System.String)">
            Notice the use of the cref attribute to reference a specific method.
            </seealso>
        </member>
        <member name="M:TestClass.Main(System.String[])">
            <summary>
            The entry point for the application.
            </summary>
            <param name="args"> A list of command line arguments.</param>
        </member>
        <member name="T:TestInterface">
            <summary>
            Documentation that describes the interface goes here.
            </summary>
            <remarks>
            Details about the interface go here.
            </remarks>
        </member>
        <member name="M:TestInterface.InterfaceMethod(System.Int32)">
            <summary>
            Documentation that describes the method goes here.
            </summary>
            <param name="n">
            Parameter n requires an integer argument.
            </param>
            <returns>
            The method returns an integer.
            </returns>
        </member>
    </members>
</doc>
```

## <a name="compiling-the-code"></a><span data-ttu-id="e3e77-108">Kompilowanie kodu</span><span class="sxs-lookup"><span data-stu-id="e3e77-108">Compiling the code</span></span>

<span data-ttu-id="e3e77-109">Aby skompilować przykład, wprowadź następujące polecenie:</span><span class="sxs-lookup"><span data-stu-id="e3e77-109">To compile the example, enter the following command:</span></span>

`csc XMLsample.cs /doc:XMLsample.xml`

<span data-ttu-id="e3e77-110">To polecenie tworzy plik XML *XMLsample.xml*, który można wyświetlić w przeglądarce lub przy użyciu `TYPE` polecenia.</span><span class="sxs-lookup"><span data-stu-id="e3e77-110">This command creates the XML file *XMLsample.xml*, which you can view in your browser or by using the `TYPE` command.</span></span>

## <a name="robust-programming"></a><span data-ttu-id="e3e77-111">Niezawodne programowanie</span><span class="sxs-lookup"><span data-stu-id="e3e77-111">Robust programming</span></span>

<span data-ttu-id="e3e77-112">Dokumentacja XML zaczyna się od `///` .</span><span class="sxs-lookup"><span data-stu-id="e3e77-112">XML documentation starts with `///`.</span></span> <span data-ttu-id="e3e77-113">Podczas tworzenia nowego projektu kreatory umieszczają w nich kilka początkowych `///` wierszy.</span><span class="sxs-lookup"><span data-stu-id="e3e77-113">When you create a new project, the wizards put some starter `///` lines in for you.</span></span> <span data-ttu-id="e3e77-114">Przetwarzanie tych komentarzy ma pewne ograniczenia:</span><span class="sxs-lookup"><span data-stu-id="e3e77-114">The processing of these comments has some restrictions:</span></span>

- <span data-ttu-id="e3e77-115">Dokumentacja musi być poprawnie sformułowanym plikiem XML.</span><span class="sxs-lookup"><span data-stu-id="e3e77-115">The documentation must be well-formed XML.</span></span> <span data-ttu-id="e3e77-116">Jeśli kod XML nie jest poprawnie sformułowany, generowane jest ostrzeżenie, a plik dokumentacji będzie zawierać komentarz informujący o wystąpieniu błędu.</span><span class="sxs-lookup"><span data-stu-id="e3e77-116">If the XML is not well-formed, a warning is generated and the documentation file will contain a comment that says that an error was encountered.</span></span>

- <span data-ttu-id="e3e77-117">Deweloperzy mogą bezpłatnie tworzyć własne zestawy tagów.</span><span class="sxs-lookup"><span data-stu-id="e3e77-117">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="e3e77-118">Istnieje [zalecany zestaw tagów](recommended-tags-for-documentation-comments.md).</span><span class="sxs-lookup"><span data-stu-id="e3e77-118">There is a [recommended set of tags](recommended-tags-for-documentation-comments.md).</span></span> <span data-ttu-id="e3e77-119">Niektóre z zalecanych tagów mają specjalne znaczenie:</span><span class="sxs-lookup"><span data-stu-id="e3e77-119">Some of the recommended tags have special meanings:</span></span>

  - <span data-ttu-id="e3e77-120">`<param>`Tag jest używany do opisywania parametrów.</span><span class="sxs-lookup"><span data-stu-id="e3e77-120">The `<param>` tag is used to describe parameters.</span></span> <span data-ttu-id="e3e77-121">Jeśli jest używany, kompilator sprawdza, czy parametr istnieje i że wszystkie parametry zostały opisane w dokumentacji.</span><span class="sxs-lookup"><span data-stu-id="e3e77-121">If used, the compiler verifies that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="e3e77-122">Jeśli weryfikacja zakończy się niepowodzeniem, kompilator generuje ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="e3e77-122">If the verification fails, the compiler issues a warning.</span></span>

  - <span data-ttu-id="e3e77-123">Ten `cref` atrybut może być dołączany do dowolnego tagu w celu odwoływania się do elementu kodu.</span><span class="sxs-lookup"><span data-stu-id="e3e77-123">The `cref` attribute can be attached to any tag to reference a code element.</span></span> <span data-ttu-id="e3e77-124">Kompilator sprawdza, czy ten element kodu istnieje.</span><span class="sxs-lookup"><span data-stu-id="e3e77-124">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="e3e77-125">Jeśli weryfikacja zakończy się niepowodzeniem, kompilator generuje ostrzeżenie.</span><span class="sxs-lookup"><span data-stu-id="e3e77-125">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="e3e77-126">Kompilator przestrzega wszelkich instrukcji, `using` gdy szuka typu opisanego w `cref` atrybucie.</span><span class="sxs-lookup"><span data-stu-id="e3e77-126">The compiler respects any `using` statements when it looks for a type described in the `cref` attribute.</span></span>

  - <span data-ttu-id="e3e77-127">`<summary>`Tag jest używany przez funkcję IntelliSense w programie Visual Studio do wyświetlania dodatkowych informacji na temat typu lub elementu członkowskiego.</span><span class="sxs-lookup"><span data-stu-id="e3e77-127">The `<summary>` tag is used by IntelliSense inside Visual Studio to display additional information about a type or member.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e3e77-128">Plik XML nie zawiera pełnych informacji o typie i elementach członkowskich (na przykład nie zawierają żadnych informacji o typie).</span><span class="sxs-lookup"><span data-stu-id="e3e77-128">The XML file does not provide full information about the type and members (for example, it does not contain any type information).</span></span> <span data-ttu-id="e3e77-129">Aby uzyskać pełne informacje na temat typu lub elementu członkowskiego, należy użyć pliku dokumentacji wraz z odbiciem w rzeczywistym typie lub elemencie członkowskim.</span><span class="sxs-lookup"><span data-stu-id="e3e77-129">To get full information about a type or member, use the documentation file together with reflection on the actual type or member.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3e77-130">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="e3e77-130">See also</span></span>

- [<span data-ttu-id="e3e77-131">Przewodnik programowania w języku C#</span><span class="sxs-lookup"><span data-stu-id="e3e77-131">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="e3e77-132">-doc (opcje kompilatora C#)</span><span class="sxs-lookup"><span data-stu-id="e3e77-132">-doc (C# compiler options)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)
- [<span data-ttu-id="e3e77-133">Komentarze dokumentacji XML</span><span class="sxs-lookup"><span data-stu-id="e3e77-133">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="e3e77-134">Procesor dokumentacji DocFX</span><span class="sxs-lookup"><span data-stu-id="e3e77-134">DocFX documentation processor</span></span>](https://dotnet.github.io/docfx/)
- [<span data-ttu-id="e3e77-135">Procesor dokumentacji Sandcastle</span><span class="sxs-lookup"><span data-stu-id="e3e77-135">Sandcastle documentation processor</span></span>](https://github.com/EWSoftware/SHFB)
