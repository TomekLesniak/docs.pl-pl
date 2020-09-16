---
title: Wskazówki dotyczące zabezpieczeń zestawów danych i DataTable
ms.date: 07/14/2020
dev_langs:
- csharp
ms.openlocfilehash: e9973df02ff478eedc932099fb8be0526a97b899
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679458"
---
# <a name="dataset-and-datatable-security-guidance"></a><span data-ttu-id="2043f-102">Wskazówki dotyczące zabezpieczeń zestawów danych i DataTable</span><span class="sxs-lookup"><span data-stu-id="2043f-102">DataSet and DataTable security guidance</span></span>

<span data-ttu-id="2043f-103">Ten artykuł ma zastosowanie do:</span><span class="sxs-lookup"><span data-stu-id="2043f-103">This article applies to:</span></span>

* <span data-ttu-id="2043f-104">.NET Framework (wszystkie wersje)</span><span class="sxs-lookup"><span data-stu-id="2043f-104">.NET Framework (all versions)</span></span>
* <span data-ttu-id="2043f-105">.NET Core i nowsze</span><span class="sxs-lookup"><span data-stu-id="2043f-105">.NET Core and later</span></span>
* <span data-ttu-id="2043f-106">.NET 5,0 i nowsze</span><span class="sxs-lookup"><span data-stu-id="2043f-106">.NET 5.0 and later</span></span>

<span data-ttu-id="2043f-107">[Zestaw](/dotnet/api/system.data.dataset) danych i typy [DataTable](/dotnet/api/system.data.datatable) są starszymi składnikami platformy .NET, które umożliwiają reprezentowania zestawów danych jako obiektów zarządzanych.</span><span class="sxs-lookup"><span data-stu-id="2043f-107">The [DataSet](/dotnet/api/system.data.dataset) and [DataTable](/dotnet/api/system.data.datatable) types are legacy .NET components that allow representing data sets as managed objects.</span></span> <span data-ttu-id="2043f-108">Te składniki zostały wprowadzone w środowisku .NET 1,0 w ramach oryginalnej [infrastruktury ADO.NET](./index.md).</span><span class="sxs-lookup"><span data-stu-id="2043f-108">These components were introduced in .NET 1.0 as part of the original [ADO.NET infrastructure](./index.md).</span></span> <span data-ttu-id="2043f-109">Ich celem było zapewnienie widoku zarządzanego na potrzeby relacyjnego zestawu danych, który jest bardziej abstrakcyjny, niezależnie od tego, czy bazowe źródło danych było XML, SQL czy inną technologią.</span><span class="sxs-lookup"><span data-stu-id="2043f-109">Their goal was to provide a managed view over a relational data set, abstracting away whether the underlying source of the data was XML, SQL, or another technology.</span></span>

<span data-ttu-id="2043f-110">Aby uzyskać więcej informacji na temat ADO.NET, w tym bardziej nowoczesnych odmian widoku danych, zapoznaj [się z dokumentacją ADO.NET](../index.md).</span><span class="sxs-lookup"><span data-stu-id="2043f-110">For more information on ADO.NET, including more modern data view paradigms, see [the ADO.NET documentation](../index.md).</span></span>

## <a name="default-restrictions-when-deserializing-a-dataset-or-datatable-from-xml"></a><span data-ttu-id="2043f-111">Domyślne ograniczenia podczas deserializacji zestawu danych lub elementu DataTable z pliku XML</span><span class="sxs-lookup"><span data-stu-id="2043f-111">Default restrictions when deserializing a DataSet or DataTable from XML</span></span>

<span data-ttu-id="2043f-112">We wszystkich obsługiwanych wersjach .NET Framework, .NET Core i .NET `DataSet` i należy `DataTable` wprowadzić następujące ograniczenia dotyczące typów obiektów, które mogą być obecne w deserializowanych danych.</span><span class="sxs-lookup"><span data-stu-id="2043f-112">On all supported versions of .NET Framework, .NET Core, and .NET, `DataSet` and `DataTable` place the following restrictions on what types of objects may be present in the deserialized data.</span></span> <span data-ttu-id="2043f-113">Domyślnie ta lista jest ograniczona do:</span><span class="sxs-lookup"><span data-stu-id="2043f-113">By default, this list is restricted to:</span></span>

* <span data-ttu-id="2043f-114">Elementy podstawowe i równoważne podstawowe:,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,,, `bool` `char` `sbyte` `byte` `short` `ushort` `int` `uint` `long` `ulong` `float` `double` `decimal` `DateTime` `DateTimeOffset` `TimeSpan` `string` `Guid` `SqlBinary` `SqlBoolean` `SqlByte` `SqlBytes` `SqlChars` `SqlDateTime` `SqlDecimal` `SqlDouble` `SqlGuid` `SqlInt16` `SqlInt32` `SqlInt64` `SqlMoney` `SqlSingle` i `SqlString` .</span><span class="sxs-lookup"><span data-stu-id="2043f-114">Primitives and primitive equivalents: `bool`, `char`, `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, `decimal`, `DateTime`, `DateTimeOffset`, `TimeSpan`, `string`, `Guid`, `SqlBinary`, `SqlBoolean`, `SqlByte`, `SqlBytes`, `SqlChars`, `SqlDateTime`, `SqlDecimal`, `SqlDouble`, `SqlGuid`, `SqlInt16`, `SqlInt32`, `SqlInt64`, `SqlMoney`, `SqlSingle`, and `SqlString`.</span></span>
* <span data-ttu-id="2043f-115">Często używane elementy inne niż pierwotne: `Type` , `Uri` , i `BigInteger` .</span><span class="sxs-lookup"><span data-stu-id="2043f-115">Commonly used non-primitives: `Type`, `Uri`, and `BigInteger`.</span></span>
* <span data-ttu-id="2043f-116">Najczęściej używane typy _System. Drawing_ : `Color` ,,,,, `Point` `PointF` `Rectangle` `RectangleF` `Size` i `SizeF` .</span><span class="sxs-lookup"><span data-stu-id="2043f-116">Commonly used _System.Drawing_ types: `Color`, `Point`, `PointF`, `Rectangle`, `RectangleF`, `Size`, and `SizeF`.</span></span>
* <span data-ttu-id="2043f-117">`Enum` Typ.</span><span class="sxs-lookup"><span data-stu-id="2043f-117">`Enum` types.</span></span>
* <span data-ttu-id="2043f-118">Tablice i listy powyższych typów.</span><span class="sxs-lookup"><span data-stu-id="2043f-118">Arrays and lists of the above types.</span></span>

<span data-ttu-id="2043f-119">Jeśli dane przychodzące XML zawierają obiekt, którego typ nie znajduje się na tej liście:</span><span class="sxs-lookup"><span data-stu-id="2043f-119">If the incoming XML data contains an object whose type is not in this list:</span></span>

* <span data-ttu-id="2043f-120">Wyjątek jest zgłaszany przy użyciu następującego komunikatu i śladu stosu.</span><span class="sxs-lookup"><span data-stu-id="2043f-120">An exception is thrown with the following message and stack trace.</span></span>  
<span data-ttu-id="2043f-121">Komunikat o błędzie:</span><span class="sxs-lookup"><span data-stu-id="2043f-121">Error Message:</span></span>  
<span data-ttu-id="2043f-122">System. InvalidOperationException: typ " \<Type Name\> , Version = \<n.n.n.n\> , Culture = \<culture\> , PublicKeyToken = \<token value\> " nie jest dozwolony w tym miejscu.</span><span class="sxs-lookup"><span data-stu-id="2043f-122">System.InvalidOperationException : Type '\<Type Name\>, Version=\<n.n.n.n\>, Culture=\<culture\>, PublicKeyToken=\<token value\>' is not allowed here.</span></span> <span data-ttu-id="2043f-123">[https://go.microsoft.com/fwlink/?linkid=2132227](https://go.microsoft.com/fwlink/?linkid=2132227)Aby uzyskać więcej informacji, zobacz.</span><span class="sxs-lookup"><span data-stu-id="2043f-123">See [https://go.microsoft.com/fwlink/?linkid=2132227](https://go.microsoft.com/fwlink/?linkid=2132227) for more details.</span></span>  
<span data-ttu-id="2043f-124">Ślad stosu:</span><span class="sxs-lookup"><span data-stu-id="2043f-124">Stack Trace:</span></span>  
<span data-ttu-id="2043f-125">w System. Data. TypeLimiter. EnsureTypeIsAllowed (typ typu, TypeLimiter capturedLimiter)</span><span class="sxs-lookup"><span data-stu-id="2043f-125">at System.Data.TypeLimiter.EnsureTypeIsAllowed(Type type, TypeLimiter capturedLimiter)</span></span>  
<span data-ttu-id="2043f-126">w System. Data. DataColumn. UpdateColumnType (typ typu, StorageType, typeCode)</span><span class="sxs-lookup"><span data-stu-id="2043f-126">at System.Data.DataColumn.UpdateColumnType(Type type, StorageType typeCode)</span></span>  
<span data-ttu-id="2043f-127">w System. Data. DataColumn. set_DataType (typ wartości)</span><span class="sxs-lookup"><span data-stu-id="2043f-127">at System.Data.DataColumn.set_DataType(Type value)</span></span>  

* <span data-ttu-id="2043f-128">Operacja deserializacji kończy się niepowodzeniem.</span><span class="sxs-lookup"><span data-stu-id="2043f-128">The deserialization operation fails.</span></span>

<span data-ttu-id="2043f-129">Podczas ładowania kodu XML do istniejącego `DataSet` `DataTable` wystąpienia lub istniejące definicje kolumn są również brane pod uwagę.</span><span class="sxs-lookup"><span data-stu-id="2043f-129">When loading XML into an existing `DataSet` or `DataTable` instance, the existing column definitions are also taken into account.</span></span> <span data-ttu-id="2043f-130">Jeśli tabela zawiera już definicję kolumny typu niestandardowego, ten typ jest tymczasowo dodawany do listy dozwolonych w czasie trwania operacji deserializacji XML.</span><span class="sxs-lookup"><span data-stu-id="2043f-130">If the table already contains a column definition of a custom type, that type is temporarily added to the allow list for the duration of the XML deserialization operation.</span></span>

> [!NOTE]
> <span data-ttu-id="2043f-131">Po dodaniu kolumn do programu `DataTable` program `ReadXml` nie odczytuje schematu z kodu XML, a jeśli schemat nie jest zgodny, nie będzie również odczytywany w rekordach, dlatego należy dodać wszystkie kolumny samodzielnie, aby użyć tej metody.</span><span class="sxs-lookup"><span data-stu-id="2043f-131">Once you add columns to a `DataTable`, `ReadXml` will not read the schema from the XML, and if the schema does not match it will also not read in the records, so you will need to add all the columns yourself to use this method.</span></span>

```csharp
XmlReader xmlReader = GetXmlReader();

// Assume the XML blob contains data for type MyCustomClass.
// The following call to ReadXml fails because MyCustomClass isn't in the allowed types list.

DataTable table = new DataTable("MyDataTable");
table.ReadXml(xmlReader);

// However, the following call to ReadXml succeeds, since the DataTable instance
// already defines a column of type MyCustomClass.

DataTable table = new DataTable("MyDataTable");
table.Columns.Add("MyColumn", typeof(MyCustomClass));
table.ReadXml(xmlReader); // this call will succeed
```

<span data-ttu-id="2043f-132">Ograniczenia typu obiektu mają zastosowanie również w przypadku `XmlSerializer` deserializacji wystąpienia `DataSet` lub `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="2043f-132">The object type restrictions also apply when using `XmlSerializer` to deserialize an instance of `DataSet` or `DataTable`.</span></span> <span data-ttu-id="2043f-133">Jednak mogą nie stosować `BinaryFormatter` się do deserializacji wystąpienia `DataSet` lub `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="2043f-133">However, they may not apply when using `BinaryFormatter` to deserialize an instance of `DataSet` or `DataTable`.</span></span>

<span data-ttu-id="2043f-134">Ograniczenia dotyczące typu obiektu nie mają zastosowania, na przykład `DataAdapter.Fill` gdy `DataTable` wystąpienie jest wypełniane bezpośrednio z bazy danych bez użycia interfejsów API deserializacji XML.</span><span class="sxs-lookup"><span data-stu-id="2043f-134">The object type restrictions don't apply when using `DataAdapter.Fill`, such as when a `DataTable` instance is populated directly from a database without using the XML deserialization APIs.</span></span>

### <a name="extend-the-list-of-allowed-types"></a><span data-ttu-id="2043f-135">Rozwiń listę dozwolonych typów</span><span class="sxs-lookup"><span data-stu-id="2043f-135">Extend the list of allowed types</span></span>

<span data-ttu-id="2043f-136">Aplikacja może rozbudować listę dozwolonych typów, aby uwzględnić niestandardowe typy oprócz wbudowanych typów wymienionych powyżej.</span><span class="sxs-lookup"><span data-stu-id="2043f-136">An app can extend the allowed types list to include custom types in addition to the built-in types listed above.</span></span> <span data-ttu-id="2043f-137">Jeśli rozszerzasz listę dozwolonych typów, zmiana ma wpływ na _wszystkie_ `DataSet` `DataTable` wystąpienia w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2043f-137">If extending the allowed types list, the change affects _all_ `DataSet` and `DataTable` instances within the app.</span></span> <span data-ttu-id="2043f-138">Typów nie można usunąć z listy wbudowanych typów dozwolonych.</span><span class="sxs-lookup"><span data-stu-id="2043f-138">Types cannot be removed from the built-in allowed types list.</span></span>

#### <a name="extend-through-configuration-net-framework-40---48"></a><span data-ttu-id="2043f-139">Przechodzenie do konfiguracji (.NET Framework 4,0 – 4,8)</span><span class="sxs-lookup"><span data-stu-id="2043f-139">Extend through configuration (.NET Framework 4.0 - 4.8)</span></span>

<span data-ttu-id="2043f-140">_App.config_ można użyć do rozszerania listy dozwolonych typów.</span><span class="sxs-lookup"><span data-stu-id="2043f-140">_App.config_ can be used to extend the allowed types list.</span></span> <span data-ttu-id="2043f-141">Aby rozwinąć listę dozwolonych typów:</span><span class="sxs-lookup"><span data-stu-id="2043f-141">To extend the allowed types list:</span></span>

* <span data-ttu-id="2043f-142">Użyj `<configSections>` elementu, aby dodać odwołanie do sekcji Konfiguracja _System. Data_ .</span><span class="sxs-lookup"><span data-stu-id="2043f-142">Use the `<configSections>` element to add a reference to the _System.Data_ configuration section.</span></span>
* <span data-ttu-id="2043f-143">Użyj `<system.data.dataset.serialization>` / `<allowedTypes>` , aby określić dodatkowe typy.</span><span class="sxs-lookup"><span data-stu-id="2043f-143">Use `<system.data.dataset.serialization>`/`<allowedTypes>` to specify additional types.</span></span>

<span data-ttu-id="2043f-144">Każdy `<add>` element musi określać tylko jeden typ za pomocą nazwy typu kwalifikowanego zestawu.</span><span class="sxs-lookup"><span data-stu-id="2043f-144">Each `<add>` element must specify only one type by using its assembly qualified type name.</span></span> <span data-ttu-id="2043f-145">Aby dodać dodatkowe typy do listy dozwolonych typów, Użyj wielu `<add>` elementów.</span><span class="sxs-lookup"><span data-stu-id="2043f-145">To add additional types to the allowed types list, use multiple `<add>` elements.</span></span>

<span data-ttu-id="2043f-146">Poniższy przykład pokazuje Rozszerzanie listy dozwolonych typów przez dodanie typu niestandardowego `Fabrikam.CustomType` .</span><span class="sxs-lookup"><span data-stu-id="2043f-146">The following sample shows extending the allowed types list by adding the custom type `Fabrikam.CustomType`.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add type="assembly qualified type name" /> -->
      <add type="Fabrikam.CustomType, Fabrikam, Version=1.0.0.0, Culture=neutral, PublicKeyToken=2b3831f2f2b744f7" />
      <!-- additional <add /> elements as needed -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

<span data-ttu-id="2043f-147">Aby pobrać kwalifikowaną nazwę zestawu typu, użyj właściwości [Type. AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) , jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="2043f-147">To retrieve the assembly qualified name of a type, use the [Type.AssemblyQualifiedName](/dotnet/api/system.type.assemblyqualifiedname) property, as demonstrated in the following code.</span></span>

```csharp
string assemblyQualifiedName = typeof(Fabrikam.CustomType).AssemblyQualifiedName;
```

<a name="etc"></a>

#### <a name="extend-through-configuration-net-framework-20---35"></a><span data-ttu-id="2043f-148">Przechodzenie do konfiguracji (.NET Framework 2,0 – 3,5)</span><span class="sxs-lookup"><span data-stu-id="2043f-148">Extend through configuration (.NET Framework 2.0 - 3.5)</span></span>

<span data-ttu-id="2043f-149">Jeśli aplikacja jest przeznaczona dla .NET Framework 2,0 lub 3,5, nadal możesz użyć powyższego mechanizmu _App.config_ , aby rozwinąć listę dozwolonych typów.</span><span class="sxs-lookup"><span data-stu-id="2043f-149">If your app targets .NET Framework 2.0 or 3.5, you can still use the above _App.config_ mechanism to extend the allowed types list.</span></span> <span data-ttu-id="2043f-150">Jednak `<configSections>` element będzie wyglądał nieco inaczej, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="2043f-150">However, your `<configSections>` element will look slightly different, as shown in the following code:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- The below <sectionGroup> and <section> are specific to .NET Framework 2.0 and 3.5. -->
    <sectionGroup name="system.data.dataset.serialization" type="System.Data.SerializationSettingsSectionGroup, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">
      <section name="allowedTypes" type="System.Data.AllowedTypesSectionHandler, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>
    </sectionGroup>
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes>
      <!-- <add /> elements, as demonstrated in the .NET Framework 4.0 - 4.8 sample code above. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

#### <a name="extend-programmatically-net-framework-net-core-net-50"></a><span data-ttu-id="2043f-151">Zwiększ programowo (.NET Framework, .NET Core, .NET 5.0 +)</span><span class="sxs-lookup"><span data-stu-id="2043f-151">Extend programmatically (.NET Framework, .NET Core, .NET 5.0+)</span></span>

<span data-ttu-id="2043f-152">Listę dozwolonych typów można również rozszerzyć programowo przy użyciu [elementu AppDomain. SetData](/dotnet/api/system.appdomain.setdata) z dobrze znanym kluczem _System. Data. DataSetDefaultAllowedTypes_, jak pokazano w poniższym kodzie.</span><span class="sxs-lookup"><span data-stu-id="2043f-152">The list of allowed types can also be extended programmatically by using [AppDomain.SetData](/dotnet/api/system.appdomain.setdata) with the well-known key _System.Data.DataSetDefaultAllowedTypes_, as shown in the following code.</span></span>

```csharp
Type[] extraAllowedTypes = new Type[]
{
    typeof(Fabrikam.CustomType),
    typeof(Contoso.AdditionalCustomType)
};

AppDomain.CurrentDomain.SetData("System.Data.DataSetDefaultAllowedTypes", extraAllowedTypes);
```

<span data-ttu-id="2043f-153">W przypadku używania mechanizmu rozszerzenia wartość skojarzona z kluczem _System. Data. DataSetDefaultAllowedTypes_ musi być typu `Type[]` .</span><span class="sxs-lookup"><span data-stu-id="2043f-153">If using the extension mechanism, the value associated with the key _System.Data.DataSetDefaultAllowedTypes_ must be of type `Type[]`.</span></span>

<span data-ttu-id="2043f-154">Na .NET Framework lista dozwolonych typów może być rozszerzona zarówno z _App.config_ , jak i `AppDomain.SetData` .</span><span class="sxs-lookup"><span data-stu-id="2043f-154">On .NET Framework, the list of allowed types may be extended both with _App.config_ and `AppDomain.SetData`.</span></span> <span data-ttu-id="2043f-155">W tym przypadku `DataSet` i `DataTable` zezwoli na deserializacji obiektu w ramach danych, jeśli jego typ znajduje się na liście.</span><span class="sxs-lookup"><span data-stu-id="2043f-155">In this case, `DataSet` and `DataTable` will allow an object to be deserialized as part of the data if its type is present in either list.</span></span>

### <a name="run-an-app-in-audit-mode-net-framework"></a><span data-ttu-id="2043f-156">Uruchom aplikację w trybie inspekcji (.NET Framework)</span><span class="sxs-lookup"><span data-stu-id="2043f-156">Run an app in audit mode (.NET Framework)</span></span>

<span data-ttu-id="2043f-157">W .NET Framework `DataSet` i `DataTable` zapewniają możliwość trybu inspekcji.</span><span class="sxs-lookup"><span data-stu-id="2043f-157">In .NET Framework, `DataSet` and `DataTable` provide an audit mode capability.</span></span> <span data-ttu-id="2043f-158">Gdy tryb inspekcji jest włączony, `DataSet` należy `DataTable` porównać typy obiektów przychodzących z listą dozwolonych typów.</span><span class="sxs-lookup"><span data-stu-id="2043f-158">When audit mode is enabled, `DataSet` and `DataTable` compare the types of incoming objects against the allowed types list.</span></span> <span data-ttu-id="2043f-159">Jeśli jednak obiekt, którego typ jest niedozwolony, jest widoczny, wyjątek **nie** zostanie zgłoszony.</span><span class="sxs-lookup"><span data-stu-id="2043f-159">However, if an object whose type is not allowed is seen, an exception is **not** thrown.</span></span> <span data-ttu-id="2043f-160">Zamiast tego `DataSet` należy `DataTable` powiadomić wszystkie dołączone `TraceListener` wystąpienia o typie podejrzanym, co pozwala na `TraceListener` rejestrowanie tych informacji.</span><span class="sxs-lookup"><span data-stu-id="2043f-160">Instead, `DataSet` and `DataTable` notify any attached `TraceListener` instances that a suspicious type is present, allowing the `TraceListener` to log this information.</span></span> <span data-ttu-id="2043f-161">Nie jest zgłaszany żaden wyjątek, a operacja deserializacji będzie kontynuowana.</span><span class="sxs-lookup"><span data-stu-id="2043f-161">No exception is thrown and the deserialization operation continues.</span></span>

> [!WARNING]
> <span data-ttu-id="2043f-162">Uruchamianie aplikacji w trybie inspekcji powinna być tylko tymczasowym środkiem używanym do testowania.</span><span class="sxs-lookup"><span data-stu-id="2043f-162">Running an app in "audit mode" should only be a temporary measure used for testing.</span></span> <span data-ttu-id="2043f-163">Gdy tryb inspekcji jest włączony `DataSet` i `DataTable` nie Wymuszaj ograniczeń typu, co może spowodować powstanie sieci w aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2043f-163">When audit mode is enabled, `DataSet` and `DataTable` do not enforce type restrictions, which can introduce a security hole inside your app.</span></span> <span data-ttu-id="2043f-164">Aby uzyskać więcej informacji, zobacz sekcje zatytułowane [usuwanie wszystkich ograniczeń typu](#ratr) i [bezpieczeństwo w odniesieniu do niezaufanych danych wejściowych](#swr).</span><span class="sxs-lookup"><span data-stu-id="2043f-164">For more information, see the sections titled [Removing all type restrictions](#ratr) and [Safety with regard to untrusted input](#swr).</span></span>

<span data-ttu-id="2043f-165">Tryb inspekcji można włączyć za _App.config_:</span><span class="sxs-lookup"><span data-stu-id="2043f-165">Audit mode can be enabled through _App.config_:</span></span>

* <span data-ttu-id="2043f-166">Zapoznaj się z sekcją [rozszerzanie przez konfigurację](#etc) w tym dokumencie, aby uzyskać informacje na temat właściwej wartości do umieszczenia dla `<configSections>` elementu.</span><span class="sxs-lookup"><span data-stu-id="2043f-166">See the [Extending through configuration](#etc) section in this document for information on the proper value to put for the `<configSections>` element.</span></span>
* <span data-ttu-id="2043f-167">Użyj `<allowedTypes auditOnly="true">` , aby włączyć tryb inspekcji, jak pokazano w poniższej tabeli.</span><span class="sxs-lookup"><span data-stu-id="2043f-167">Use `<allowedTypes auditOnly="true">` to enable audit mode, as shown in the following markup.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <configSections>
    <!-- See the section of this document titled "Extending through configuration" for the appropriate
         <sectionGroup> and <section> elements to put here, depending on whether you're running .NET
         Framework 2.0 - 3.5 or 4.0 - 4.8. -->
  </configSections>
  <system.data.dataset.serialization>
    <allowedTypes auditOnly="true"> <!-- setting auditOnly="true" enables audit mode -->
      <!-- Optional <add /> elements as needed. -->
    </allowedTypes>
  </system.data.dataset.serialization>
</configuration>
```

<span data-ttu-id="2043f-168">Gdy tryb inspekcji jest włączony, można użyć _App.config_ , aby połączyć preferowaną z `TraceListener` `DataSet` wbudowaną nazwą wbudowanego `TraceSource.` źródła śledzenia jest _System. Data. DataSet_.</span><span class="sxs-lookup"><span data-stu-id="2043f-168">Once audit mode is enabled, you can use _App.config_ to connect your preferred `TraceListener` to the `DataSet` built-in `TraceSource.` The name of the built-in trace source is _System.Data.DataSet_.</span></span> <span data-ttu-id="2043f-169">Poniższy przykład ilustruje zapisywanie zdarzeń śledzenia w konsoli programu _i_ w pliku dziennika na dysku.</span><span class="sxs-lookup"><span data-stu-id="2043f-169">The following sample demonstrates writing trace events to the console _and_ to a log file on disk.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.diagnostics>
    <sources>
      <source name="System.Data.DataSet"
              switchType="System.Diagnostics.SourceSwitch"
              switchValue="Warning">
        <listeners>
          <!-- write to the console -->
          <add name="console"
               type="System.Diagnostics.ConsoleTraceListener" />
          <!-- *and* write to a log file on disk -->
          <add name="filelog"
               type="System.Diagnostics.TextWriterTraceListener"
               initializeData="c:\logs\mylog.txt" />
        </listeners>
      </source>
    </sources>
  </system.diagnostics>
</configuration>
```

<span data-ttu-id="2043f-170">Aby uzyskać więcej informacji na temat `TraceSource` i `TraceListener` , zobacz dokument [How to: use TraceSource and filters with Trace detektors](../../../debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md).</span><span class="sxs-lookup"><span data-stu-id="2043f-170">For more information on `TraceSource` and `TraceListener`, see the document [How to: Use TraceSource and Filters with Trace Listeners](../../../debug-trace-profile/how-to-use-tracesource-and-filters-with-trace-listeners.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2043f-171">Uruchamianie aplikacji w trybie inspekcji nie jest dostępne w programie .NET Core ani w programie .NET 5,0 i nowszych wersjach.</span><span class="sxs-lookup"><span data-stu-id="2043f-171">Running an app in audit mode is not available in .NET Core or in .NET 5.0 and later.</span></span>

<a name="ratr"></a>

### <a name="remove-all-type-restrictions"></a><span data-ttu-id="2043f-172">Usuń wszystkie ograniczenia typów</span><span class="sxs-lookup"><span data-stu-id="2043f-172">Remove all type restrictions</span></span>

<span data-ttu-id="2043f-173">Jeśli aplikacja musi usunąć wszystkie ograniczenia dotyczące ograniczania typów z `DataSet` i `DataTable` :</span><span class="sxs-lookup"><span data-stu-id="2043f-173">If an app must remove all type limiting restrictions from `DataSet` and `DataTable`:</span></span>

* <span data-ttu-id="2043f-174">Istnieje kilka opcji, aby pominąć ograniczenia ograniczające typy.</span><span class="sxs-lookup"><span data-stu-id="2043f-174">There are several options to suppress type limiting restrictions.</span></span>
* <span data-ttu-id="2043f-175">Dostępne opcje zależą od struktury docelowej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2043f-175">The options available depend on the framework the app targets.</span></span>

> [!WARNING]
> <span data-ttu-id="2043f-176">Usunięcie wszystkich ograniczeń dotyczących typów może spowodować powstanie otworu zabezpieczeń wewnątrz aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2043f-176">Removing all type restrictions can introduce a security hole inside the app.</span></span> <span data-ttu-id="2043f-177">W przypadku korzystania z tego mechanizmu upewnij się, że aplikacja nie używa lub **nie** `DataSet` `DataTable` odczytuje niezaufanych danych wejściowych.</span><span class="sxs-lookup"><span data-stu-id="2043f-177">When using this mechanism, ensure the app does **not** use `DataSet` or `DataTable` to read untrusted input.</span></span> <span data-ttu-id="2043f-178">Aby uzyskać więcej informacji, zobacz [CVE-2020-1147](https://portal.msrc.microsoft.com/en-us/security-guidance/advisory/CVE-2020-1147) i w poniższej sekcji zatytułowanej [bezpieczeństwo w odniesieniu do niezaufanych danych wejściowych](#swr).</span><span class="sxs-lookup"><span data-stu-id="2043f-178">For more information, see [CVE-2020-1147](https://portal.msrc.microsoft.com/en-us/security-guidance/advisory/CVE-2020-1147) and the following section titled [Safety with regard to untrusted input](#swr).</span></span>

#### <a name="through-appcontext-configuration-net-framework-46---48-net-core-21-and-later-net-50-and-later"></a><span data-ttu-id="2043f-179">Za poorednictwem konfiguracji AppContext (.NET Framework 4,6-4,8, .NET Core 2,1 i nowszych, .NET 5,0 i nowsze)</span><span class="sxs-lookup"><span data-stu-id="2043f-179">Through AppContext configuration (.NET Framework 4.6 - 4.8, .NET Core 2.1 and later, .NET 5.0 and later)</span></span>

<span data-ttu-id="2043f-180">`AppContext`Przełącznik, `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` , po ustawieniu, aby `true` usunąć wszystkie ograniczenia dotyczące ograniczania typów z `DataSet` i `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="2043f-180">The `AppContext` switch, `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation`, when set to `true` removes all type limiting restrictions from `DataSet` and `DataTable`.</span></span>

<span data-ttu-id="2043f-181">W .NET Framework tego przełącznika można włączyć za pośrednictwem _App.config_, jak pokazano w następującej konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="2043f-181">In .NET Framework, this switch can be enabled via _App.config_, as shown in the following configuration:</span></span>

```xml
<configuration>
   <runtime>
      <!-- Warning: setting the following switch can introduce a security problem. -->
      <AppContextSwitchOverrides value="Switch.System.Data.AllowArbitraryDataSetTypeInstantiation=true" />
   </runtime>
</configuration>
```

<span data-ttu-id="2043f-182">W ASP.NET `<AppContextSwitchOverrides>` element nie jest dostępny.</span><span class="sxs-lookup"><span data-stu-id="2043f-182">In ASP.NET, the `<AppContextSwitchOverrides>` element is not available.</span></span> <span data-ttu-id="2043f-183">Zamiast tego przełącznik można włączyć za pośrednictwem _Web.config_, jak pokazano w następującej konfiguracji:</span><span class="sxs-lookup"><span data-stu-id="2043f-183">Instead, the switch can be enabled via _Web.config_, as shown in the following configuration:</span></span>

```xml
<configuration>
    <appSettings>
        <!-- Warning: setting the following switch can introduce a security problem. -->
        <add key="AppContext.SetSwitch:Switch.System.Data.AllowArbitraryDataSetTypeInstantiation" value="true" />
    </appSettings>
</configuration>
```

<span data-ttu-id="2043f-184">Aby uzyskać więcej informacji, zobacz [\<AppContextSwitchOverrides>](../../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element.</span><span class="sxs-lookup"><span data-stu-id="2043f-184">For more information, see the [\<AppContextSwitchOverrides>](../../../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) element.</span></span>

<span data-ttu-id="2043f-185">W przypadku platformy .NET Core, .NET 5 i ASP.NET Core to ustawienie jest kontrolowane przez _runtimeconfig.jsna_, jak pokazano w poniższym kodzie JSON:</span><span class="sxs-lookup"><span data-stu-id="2043f-185">In .NET Core, .NET 5, and ASP.NET Core, this setting is controlled by _runtimeconfig.json_, as shown in the following JSON:</span></span>

```json
{
  "runtimeOptions": {
    "configProperties": {
      "Switch.System.Data.AllowArbitraryDataSetTypeInstantiation": true
    }
  }
}
```

<span data-ttu-id="2043f-186">Aby uzyskać więcej informacji, zobacz ["podstawowe ustawienia konfiguracji środowiska uruchomieniowego .NET"](../../../../core/run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="2043f-186">For more information, see [".NET Core run-time configuration settings"](../../../../core/run-time-config/index.md).</span></span>

<span data-ttu-id="2043f-187">`AllowArbitraryDataSetTypeInstantiation` można również ustawić programowo za pośrednictwem [AppContext. setswitch](/dotnet/api/system.appcontext.setswitch) zamiast przy użyciu pliku konfiguracji, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="2043f-187">`AllowArbitraryDataSetTypeInstantiation` can also be set programmatically via [AppContext.SetSwitch](/dotnet/api/system.appcontext.setswitch) instead of using a configuration file, as shown in the following code:</span></span>

```csharp
// Warning: setting the following switch can introduce a security problem.
AppContext.SetSwitch("Switch.System.Data.AllowArbitraryDataSetTypeInstantiation", true);
```

 <span data-ttu-id="2043f-188">W przypadku wybrania wcześniejszego podejścia programistycznego wywołanie `AppContext.SetSwitch` powinno odbywać się wczesne podczas uruchamiania aplikacji.</span><span class="sxs-lookup"><span data-stu-id="2043f-188">If you choose the preceding programmatic approach, the call to `AppContext.SetSwitch` should occur early in the apps startup.</span></span>

#### <a name="through-the-machine-wide-registry-net-framework-20---48"></a><span data-ttu-id="2043f-189">Za pomocą rejestru na całym komputerze (.NET Framework 2,0 – 4,8)</span><span class="sxs-lookup"><span data-stu-id="2043f-189">Through the machine-wide registry (.NET Framework 2.0 - 4.8)</span></span>

<span data-ttu-id="2043f-190">Jeśli `AppContext` program nie jest dostępny, sprawdzanie ograniczające typy można wyłączyć za pomocą rejestru systemu Windows:</span><span class="sxs-lookup"><span data-stu-id="2043f-190">If `AppContext` is not available, type limiting checks can be disabled with the Windows registry:</span></span>

* <span data-ttu-id="2043f-191">Administrator musi skonfigurować rejestr.</span><span class="sxs-lookup"><span data-stu-id="2043f-191">An administrator must configure the registry.</span></span>
* <span data-ttu-id="2043f-192">Korzystanie z rejestru jest zmianą dla całego komputera i wpłynie na _wszystkie_ aplikacje działające na tym komputerze.</span><span class="sxs-lookup"><span data-stu-id="2043f-192">Using the registry is a machine-wide change and will affect _all_ apps running on the machine.</span></span>

| <span data-ttu-id="2043f-193">Typ</span><span class="sxs-lookup"><span data-stu-id="2043f-193">Type</span></span>  |  <span data-ttu-id="2043f-194">Wartość</span><span class="sxs-lookup"><span data-stu-id="2043f-194">Value</span></span> |
|---|---|
| <span data-ttu-id="2043f-195">**Klucz rejestru**</span><span class="sxs-lookup"><span data-stu-id="2043f-195">**Registry key**</span></span> | `HKLM\SOFTWARE\Microsoft\.NETFramework\AppContext` |
| <span data-ttu-id="2043f-196">**Nazwa wartości**</span><span class="sxs-lookup"><span data-stu-id="2043f-196">**Value name**</span></span> | `Switch.System.Data.AllowArbitraryDataSetTypeInstantiation` |
| <span data-ttu-id="2043f-197">**Typ wartości**</span><span class="sxs-lookup"><span data-stu-id="2043f-197">**Value type**</span></span> | `REG_SZ` |
| <span data-ttu-id="2043f-198">**Dane wartości**</span><span class="sxs-lookup"><span data-stu-id="2043f-198">**Value data**</span></span> | `true` |

<span data-ttu-id="2043f-199">W 64-bitowym systemie operacyjnym, ta wartość musi być dodana zarówno dla klucza 64-bitowego (podanego powyżej), jak i klucza 32-bitowego.</span><span class="sxs-lookup"><span data-stu-id="2043f-199">On a 64-bit operating system, this value my need to be added for both the 64-bit key (shown above) and the 32-bit key.</span></span> <span data-ttu-id="2043f-200">Klucz 32-bitowy znajduje się w lokalizacji `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext` .</span><span class="sxs-lookup"><span data-stu-id="2043f-200">The 32-bit key is located at `HKLM\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\AppContext`.</span></span>

<span data-ttu-id="2043f-201">Aby uzyskać więcej informacji na temat korzystania z rejestru do konfigurowania `AppContext` , zobacz ["AppContext for Library](/dotnet/api/system.appcontext#appcontext-for-library-consumers)consumers".</span><span class="sxs-lookup"><span data-stu-id="2043f-201">For more information on using the registry to configure `AppContext`, see ["AppContext for library consumers"](/dotnet/api/system.appcontext#appcontext-for-library-consumers).</span></span>

<a name="swr"></a>

## <a name="safety-with-regard-to-untrusted-input"></a><span data-ttu-id="2043f-202">Bezpieczeństwo w odniesieniu do niezaufanych danych wejściowych</span><span class="sxs-lookup"><span data-stu-id="2043f-202">Safety with regard to untrusted input</span></span>

<span data-ttu-id="2043f-203">Chociaż `DataSet` i `DataTable` nakładają domyślne ograniczenia dotyczące typów, które mogą być obecne podczas deserializacji ładunków XML __ `DataSet` i `DataTable` są ogólnie niebezpieczne, gdy są wypełniane niezaufanymi danymi wejściowymi.__</span><span class="sxs-lookup"><span data-stu-id="2043f-203">While `DataSet` and `DataTable` do impose default limitations on the types that are allowed to be present while deserializing XML payloads, __`DataSet` and `DataTable` are in general not safe when populated with untrusted input.__</span></span> <span data-ttu-id="2043f-204">Poniżej znajduje się niepełna lista sposobów `DataSet` `DataTable` odczytywania niezaufanych danych wejściowych lub wystąpienia.</span><span class="sxs-lookup"><span data-stu-id="2043f-204">The following is a non-exhaustive list of ways that a `DataSet` or `DataTable` instance might read untrusted input.</span></span>

* <span data-ttu-id="2043f-205">Odwołuje się do `DataAdapter` bazy danych, a `DataAdapter.Fill` Metoda jest używana do wypełniania `DataSet` zawartością zapytania bazy danych.</span><span class="sxs-lookup"><span data-stu-id="2043f-205">A `DataAdapter` references a database, and the `DataAdapter.Fill` method is used to populate a `DataSet` with the contents of a database query.</span></span>
* <span data-ttu-id="2043f-206">`DataSet.ReadXml`Metoda or `DataTable.ReadXml` służy do odczytywania pliku XML zawierającego informacje o kolumnie i wierszu.</span><span class="sxs-lookup"><span data-stu-id="2043f-206">The `DataSet.ReadXml` or `DataTable.ReadXml` method is used to read an XML file containing column and row information.</span></span>
* <span data-ttu-id="2043f-207">`DataSet`Wystąpienie lub `DataTable` jest serializowane jako część usług sieci Web ASP.NET (SOAP) lub punktu końcowego WCF.</span><span class="sxs-lookup"><span data-stu-id="2043f-207">A `DataSet` or `DataTable` instance is serialized as part of a ASP.NET (SOAP) web services or WCF endpoint.</span></span>
* <span data-ttu-id="2043f-208">Serializator, taki jak `XmlSerializer` jest używany do deserializacji `DataSet` `DataTable` wystąpienia lub ze strumienia XML.</span><span class="sxs-lookup"><span data-stu-id="2043f-208">A serializer such as `XmlSerializer` is used to deserialize a `DataSet` or `DataTable` instance from an XML stream.</span></span>
* <span data-ttu-id="2043f-209">Serializator, taki jak `JsonConvert` jest używany do deserializacji `DataSet` `DataTable` wystąpienia lub ze strumienia JSON.</span><span class="sxs-lookup"><span data-stu-id="2043f-209">A serializer such as `JsonConvert` is used to deserialize a `DataSet` or `DataTable` instance from a JSON stream.</span></span> <span data-ttu-id="2043f-210">`JsonConvert` to metoda w popularnejNewtonsoft.Jsinnej firmy [ w](https://www.newtonsoft.com/json) bibliotece.</span><span class="sxs-lookup"><span data-stu-id="2043f-210">`JsonConvert` is a method in the popular third-party [Newtonsoft.Json](https://www.newtonsoft.com/json) library.</span></span>
* <span data-ttu-id="2043f-211">Serializator, taki jak `BinaryFormatter` jest używany do deserializacji `DataSet` `DataTable` wystąpienia lub z strumienia nieprzetworzonych bajtów.</span><span class="sxs-lookup"><span data-stu-id="2043f-211">A serializer such as `BinaryFormatter` is used to deserialize a `DataSet` or `DataTable` instance from a raw byte stream.</span></span>

<span data-ttu-id="2043f-212">W tym dokumencie omówiono zagadnienia dotyczące bezpieczeństwa w przypadku wcześniejszych scenariuszy.</span><span class="sxs-lookup"><span data-stu-id="2043f-212">This document discusses safety considerations for the preceding scenarios.</span></span>

## <a name="use-dataadapterfill-to-populate-a-dataset-from-an-untrusted-data-source"></a><span data-ttu-id="2043f-213">Użyj `DataAdapter.Fill` , aby wypełnić `DataSet` z niezaufanego źródła danych</span><span class="sxs-lookup"><span data-stu-id="2043f-213">Use `DataAdapter.Fill` to populate a `DataSet` from an untrusted data source</span></span>

<span data-ttu-id="2043f-214">`DataSet`Wystąpienie może być wypełniane za `DataAdapter` pomocą [ `DataAdapter.Fill` metody](/dotnet/api/system.data.common.dataadapter.fill), jak pokazano w poniższym przykładzie.</span><span class="sxs-lookup"><span data-stu-id="2043f-214">A `DataSet` instance can be populated from a `DataAdapter` by using [the `DataAdapter.Fill` method](/dotnet/api/system.data.common.dataadapter.fill), as shown in the following example.</span></span>

```csharp
// Assumes that connection is a valid SqlConnection object.
string queryString =
  "SELECT CustomerID, CompanyName FROM dbo.Customers";
SqlDataAdapter adapter = new SqlDataAdapter(queryString, connection);

DataSet customers = new DataSet();
adapter.Fill(customers, "Customers");
```

<span data-ttu-id="2043f-215">(Przykładowy kod jest częścią większego przykładu znalezionego podczas [wypełniania zestawu danych z elementu DataAdapter](../populating-a-dataset-from-a-dataadapter.md)).</span><span class="sxs-lookup"><span data-stu-id="2043f-215">(The code sample above is part of a larger sample found at [Populating a DataSet from a DataAdapter](../populating-a-dataset-from-a-dataadapter.md).)</span></span>

> <span data-ttu-id="2043f-216">Większość aplikacji może uprościć i założyć, że ich warstwa bazy danych jest zaufana.</span><span class="sxs-lookup"><span data-stu-id="2043f-216">Most apps can simplify and assume that their database layer is trusted.</span></span> <span data-ttu-id="2043f-217">Niemniej jednak w wykonywaćniu aplikacji do [modelowania zagrożeń](https://www.microsoft.com/securityengineering/sdl/threatmodeling) model zagrożeń może być uważany za granicę zaufania między aplikacją a warstwą bazy danych (serwera).</span><span class="sxs-lookup"><span data-stu-id="2043f-217">However, if you are in the habit of [threat modeling](https://www.microsoft.com/securityengineering/sdl/threatmodeling) your apps, your threat model may consider there to be a trust boundary between the application (client) and database layer (server).</span></span> <span data-ttu-id="2043f-218">Korzystanie z uwierzytelniania [wzajemnego](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) i uwierzytelniania usługi [AAD](/azure/azure-sql/database/authentication-aad-overview) między klientem a serwerem jest jednym ze sposobów, aby pomóc w rozwiązywaniu ryzyka związanego z tym.</span><span class="sxs-lookup"><span data-stu-id="2043f-218">Using [mutual authentication](/sql/relational-databases/native-client/features/service-principal-name-spn-support-in-client-connections) or [AAD authentication](/azure/azure-sql/database/authentication-aad-overview) between client and server is one way to help address the risks associated with this.</span></span> <span data-ttu-id="2043f-219">W pozostałej części tej sekcji omówiono możliwy wynik połączenia klienta z niezaufanym serwerem.</span><span class="sxs-lookup"><span data-stu-id="2043f-219">The remainder of this section discusses the possible result of a client connecting to an untrusted server.</span></span>

<span data-ttu-id="2043f-220">Konsekwencje wskazywania `DataAdapter` niezaufanego źródła danych zależą od implementacji `DataAdapter` samego siebie.</span><span class="sxs-lookup"><span data-stu-id="2043f-220">The consequences of pointing a `DataAdapter` at an untrusted data source depend on the implementation of the `DataAdapter` itself.</span></span>

### <a name="sqldataadapter"></a><span data-ttu-id="2043f-221">Element SqlDataAdapter</span><span class="sxs-lookup"><span data-stu-id="2043f-221">SqlDataAdapter</span></span>

<span data-ttu-id="2043f-222">W przypadku typu wbudowanego [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter)odwołującego się do niezaufanego źródła danych może spowodować atak typu "odmowa usługi" (DOS).</span><span class="sxs-lookup"><span data-stu-id="2043f-222">For the built-in type [SqlDataAdapter](/dotnet/api/microsoft.data.sqlclient.sqldataadapter), referencing an untrusted data source could result in a denial of service (DoS) attack.</span></span> <span data-ttu-id="2043f-223">Atak na system DoS może spowodować, że aplikacja przestanie odpowiadać lub ulegnie awarii.</span><span class="sxs-lookup"><span data-stu-id="2043f-223">The DoS attack could result in the app becoming unresponsive or crashing.</span></span> <span data-ttu-id="2043f-224">Jeśli osoba atakująca może zakładać bibliotekę DLL wraz z aplikacją, mogą oni również uzyskać dostęp do lokalnego wykonywania kodu.</span><span class="sxs-lookup"><span data-stu-id="2043f-224">If an attacker can plant a DLL alongside the app, they may also be able to achieve local code execution.</span></span>

### <a name="other-dataadapter-types"></a><span data-ttu-id="2043f-225">Inne typy DataAdapter</span><span class="sxs-lookup"><span data-stu-id="2043f-225">Other DataAdapter types</span></span>

<span data-ttu-id="2043f-226">`DataAdapter`Implementacje innych firm muszą dokonać własnych ocen, które zapewniają gwarancje bezpieczeństwa, które są przez nie związane z niezaufanymi danymi wejściowymi.</span><span class="sxs-lookup"><span data-stu-id="2043f-226">Third-party `DataAdapter` implementations must make their own assessments about what security guarantees they provide in the face of untrusted inputs.</span></span> <span data-ttu-id="2043f-227">Platforma .NET nie może podejmować żadnych gwarancji bezpieczeństwa dotyczących tych implementacji.</span><span class="sxs-lookup"><span data-stu-id="2043f-227">.NET cannot make any safety guarantees regarding these implementations.</span></span>

<a name="dsrdtr"></a>

## <a name="datasetreadxml-and-datatablereadxml"></a><span data-ttu-id="2043f-228">DataSet. ReadXml i DataTable. ReadXml</span><span class="sxs-lookup"><span data-stu-id="2043f-228">DataSet.ReadXml and DataTable.ReadXml</span></span>

<span data-ttu-id="2043f-229">`DataSet.ReadXml`Metody i `DataTable.ReadXml` nie są bezpieczne, gdy są używane z niezaufanymi danymi wejściowymi.</span><span class="sxs-lookup"><span data-stu-id="2043f-229">The `DataSet.ReadXml` and `DataTable.ReadXml` methods are not safe when used with untrusted input.</span></span> <span data-ttu-id="2043f-230">Zdecydowanie zalecamy, aby zamiast tego rozważyć użycie jednego z alternatyw opisanych w dalszej części tego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="2043f-230">We strongly recommend that consumers instead consider using one of the alternatives outlined later in this document.</span></span>

<span data-ttu-id="2043f-231">Implementacje `DataSet.ReadXml` i `DataTable.ReadXml` zostały pierwotnie utworzone przed lukami w serializacji jako dobrze zrozumieć kategorię zagrożeń.</span><span class="sxs-lookup"><span data-stu-id="2043f-231">The implementations of `DataSet.ReadXml` and `DataTable.ReadXml` were originally created before serialization vulnerabilities were a well-understood threat category.</span></span> <span data-ttu-id="2043f-232">W związku z tym kod nie przestrzega bieżących najlepszych rozwiązań w zakresie zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="2043f-232">As a result, the code does not follow current security best practices.</span></span> <span data-ttu-id="2043f-233">Te interfejsy API mogą służyć jako wektory dla osób atakujących do wykonywania ataków w systemie DoS względem aplikacji sieci Web.</span><span class="sxs-lookup"><span data-stu-id="2043f-233">These APIs can be used as vectors for attackers to perform DoS attacks against web apps.</span></span> <span data-ttu-id="2043f-234">Ataki te mogą spowodować, że usługa sieci Web nie odpowiada, lub spowodować zakończenie nieoczekiwanego procesu.</span><span class="sxs-lookup"><span data-stu-id="2043f-234">These attacks might render the web service unresponsive or result in unexpected process termination.</span></span> <span data-ttu-id="2043f-235">Struktura nie zapewnia środków zaradczych dla tych kategorii ataków i .NET traktuje to zachowanie "według projektu".</span><span class="sxs-lookup"><span data-stu-id="2043f-235">The framework does not provide mitigations for these attack categories and .NET considers this behavior "by design".</span></span>

<span data-ttu-id="2043f-236">Program .NET wydał aktualizacje zabezpieczeń, aby wyeliminować niektóre problemy, takie jak ujawnienie informacji lub zdalne wykonywanie kodu w programie `DataSet.ReadXml` i `DataTable.ReadXml` .</span><span class="sxs-lookup"><span data-stu-id="2043f-236">.NET has released security updates to mitigate some issues such as information disclosure or remote code execution in `DataSet.ReadXml` and `DataTable.ReadXml`.</span></span> <span data-ttu-id="2043f-237">Aktualizacje zabezpieczeń platformy .NET mogą nie zapewniać pełnej ochrony przed tymi kategoriami zagrożeń.</span><span class="sxs-lookup"><span data-stu-id="2043f-237">The .NET security updates may not provide complete protection against these threat categories.</span></span> <span data-ttu-id="2043f-238">Konsumenci powinni ocenić swoje poszczególne scenariusze i rozważyć ich potencjalną ekspozycję na te zagrożenia.</span><span class="sxs-lookup"><span data-stu-id="2043f-238">Consumers should assess their individual scenarios and consider their potential exposure to these risks.</span></span>

<span data-ttu-id="2043f-239">Klienci powinni mieć świadomość, że aktualizacje zabezpieczeń tych interfejsów API mogą mieć wpływ na zgodność aplikacji w niektórych sytuacjach.</span><span class="sxs-lookup"><span data-stu-id="2043f-239">Consumers should be aware that security updates to these APIs may impact application compatibility in some situations.</span></span> <span data-ttu-id="2043f-240">Ponadto istnieje możliwość, że nowa Luka w zabezpieczeniach tych interfejsów API zostanie odnaleziona, dla której platforma .NET nie może praktycznie opublikować aktualizacji zabezpieczeń.</span><span class="sxs-lookup"><span data-stu-id="2043f-240">Furthermore, the possibility exists that a novel vulnerability in these APIs will be discovered for which .NET can't practically publish a security update.</span></span>

<span data-ttu-id="2043f-241">Zalecamy, aby konsumenci tych interfejsów API:</span><span class="sxs-lookup"><span data-stu-id="2043f-241">We recommend that consumers of these APIs either:</span></span>

* <span data-ttu-id="2043f-242">Rozważ użycie jednego z alternatyw opisanych w dalszej części tego dokumentu.</span><span class="sxs-lookup"><span data-stu-id="2043f-242">Consider using one of the alternatives outlined later in this document.</span></span>
* <span data-ttu-id="2043f-243">Wykonaj indywidualne oceny ryzyka w swoich aplikacjach.</span><span class="sxs-lookup"><span data-stu-id="2043f-243">Perform individual risk assessments on their apps.</span></span>

<span data-ttu-id="2043f-244">Jedyną odpowiedzialnością dla użytkownika jest określenie, czy mają być używane te interfejsy API.</span><span class="sxs-lookup"><span data-stu-id="2043f-244">It is the consumer's sole responsibility to determine whether to utilize these APIs.</span></span> <span data-ttu-id="2043f-245">Konsumenci powinni ocenić wszelkie zagrożenia bezpieczeństwa, techniczne i prawne, w tym wymagania prawne, które mogą towarzyszyć za pomocą tych interfejsów API.</span><span class="sxs-lookup"><span data-stu-id="2043f-245">Consumers should assess any security, technical, and legal risks, including regulatory requirements, that may accompany using these APIs.</span></span>

## <a name="dataset-and-datatable-via-aspnet-web-services-or-wcf"></a><span data-ttu-id="2043f-246">DataSet i DataTable za pośrednictwem usług sieci Web ASP.NET lub WCF</span><span class="sxs-lookup"><span data-stu-id="2043f-246">DataSet and DataTable via ASP.NET web services or WCF</span></span>

<span data-ttu-id="2043f-247">Możliwe jest zaakceptowanie `DataSet` lub `DataTable` wystąpienie w usłudze sieci Web ASP.NET (SOAP), jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="2043f-247">It is possible to accept a `DataSet` or a `DataTable` instance in an ASP.NET (SOAP) web service, as demonstrated in the following code:</span></span>

```csharp
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(DataTable dataTable)
    {
        /* Web method implementation. */
    }
}
```

<span data-ttu-id="2043f-248">Odmiana tego nie jest akceptowana `DataSet` ani `DataTable` bezpośrednio jako parametr, ale zamiast tego akceptuje ją w ramach ogólnego grafu serializowanego obiektu SOAP, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="2043f-248">A variation on this is not to accept `DataSet` or `DataTable` directly as a parameter, but instead to accept it as part of the overall SOAP serialized object graph, as shown in the following code:</span></span>

```csharp
using System.Data;
using System.Web.Services;

[WebService(Namespace = "http://contoso.com/")]
public class MyService : WebService
{
    [WebMethod]
    public string MyWebMethod(MyClass data)
    {
        /* Web method implementation. */
    }
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="2043f-249">Lub przy użyciu programu WCF zamiast usług sieci Web ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="2043f-249">Or, using WCF instead of ASP.NET web services:</span></span>

```csharp
using System.Data;
using System.ServiceModel;

[ServiceContract(Namespace = "http://contoso.com/")]
public interface IMyContract
{
    [OperationContract]
    string MyMethod(DataTable dataTable);
    [OperationContract]
    string MyOtherMethod(MyClass data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="2043f-250">We wszystkich tych przypadkach model zagrożeń i gwarancje bezpieczeństwa są takie same, jak w [sekcji DataSet. ReadXml i DataTable. ReadXml](#dsrdtr).</span><span class="sxs-lookup"><span data-stu-id="2043f-250">In all of these cases, the threat model and security guarantees are the same as the [DataSet.ReadXml and DataTable.ReadXml section](#dsrdtr).</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-xmlserializer"></a><span data-ttu-id="2043f-251">Deserializacja zestawu danych lub DataTable za pomocą elementu XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="2043f-251">Deserialize a DataSet or DataTable via XmlSerializer</span></span>

<span data-ttu-id="2043f-252">Deweloperzy mogą używać `XmlSerializer` do deserializacji `DataSet` i `DataTable` wystąpień, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="2043f-252">Developers can use `XmlSerializer` to deserialize `DataSet` and `DataTable` instances, as shown in the following code:</span></span>

```csharp
using System.Data;
using System.IO;
using System.Xml.Serialization;

public DataSet PerformDeserialization1(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(DataSet));
    return (DataSet)serializer.Deserialize(stream);
}

public MyClass PerformDeserialization2(Stream stream) {
    XmlSerializer serializer = new XmlSerializer(typeof(MyClass));
    return (MyClass)serializer.Deserialize(stream);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="2043f-253">W takich przypadkach model zagrożeń i gwarancje bezpieczeństwa są takie same, jak w [sekcji DataSet. ReadXml i DataTable. ReadXml](#dsrdtr)</span><span class="sxs-lookup"><span data-stu-id="2043f-253">In these cases, the threat model and security guarantees are the same as the [DataSet.ReadXml and DataTable.ReadXml section](#dsrdtr)</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-jsonconvert"></a><span data-ttu-id="2043f-254">Deserializacja zestawu danych lub DataTable za pośrednictwem JsonConvert</span><span class="sxs-lookup"><span data-stu-id="2043f-254">Deserialize a DataSet or DataTable via JsonConvert</span></span>

<span data-ttu-id="2043f-255">Popularnej biblioteki Newtonsoft innej firmy [JSON.NET](https://www.newtonsoft.com/json) może służyć do deserializacji `DataSet` i `DataTable` wystąpień, jak pokazano w poniższym kodzie:</span><span class="sxs-lookup"><span data-stu-id="2043f-255">The popular third-party Newtonsoft library [JSON.NET](https://www.newtonsoft.com/json) can be used to deserialize `DataSet` and `DataTable` instances, as shown in the following code:</span></span>

```csharp
using System.Data;
using Newtonsoft.Json;

public DataSet PerformDeserialization1(string json) {
    return JsonConvert.DeserializeObject<DataSet>(data);
}

public MyClass PerformDeserialization2(string json) {
    return JsonConvert.DeserializeObject<MyClass>(data);
}

public class MyClass
{
    // Property of type DataTable, automatically serialized and
    // deserialized as part of the overall MyClass payload.
    public DataTable MyDataTable { get; set; }
}
```

<span data-ttu-id="2043f-256">Deserializacja a `DataSet` lub `DataTable` w ten sposób z niezaufanego obiektu BLOB JSON nie jest bezpieczna.</span><span class="sxs-lookup"><span data-stu-id="2043f-256">Deserializing a `DataSet` or `DataTable` in this manner from an untrusted JSON blob is not safe.</span></span> <span data-ttu-id="2043f-257">Ten wzorzec jest narażony na atak typu "odmowa usługi".</span><span class="sxs-lookup"><span data-stu-id="2043f-257">This pattern is vulnerable to a denial of service attack.</span></span> <span data-ttu-id="2043f-258">Atak może ulec awarii lub nie reagować.</span><span class="sxs-lookup"><span data-stu-id="2043f-258">Such an attack could crash the app or render it unresponsive.</span></span>

> [!NOTE]
> <span data-ttu-id="2043f-259">Firma Microsoft nie gwarantuje ani nie obsługuje implementacji bibliotek innych firm, takich jak _Newtonsoft.Json_.</span><span class="sxs-lookup"><span data-stu-id="2043f-259">Microsoft does not warrant or support the implementation of third-party libraries like _Newtonsoft.Json_.</span></span> <span data-ttu-id="2043f-260">Te informacje są dostarczane w celu zapewnienia kompletności i są dokładne od momentu tego zapisu.</span><span class="sxs-lookup"><span data-stu-id="2043f-260">This information is provided for completeness and is accurate as of the time of this writing.</span></span>

## <a name="deserialize-a-dataset-or-datatable-via-binaryformatter"></a><span data-ttu-id="2043f-261">Deserializacja zestawu danych lub DataTable za pośrednictwem BinaryFormatter</span><span class="sxs-lookup"><span data-stu-id="2043f-261">Deserialize a DataSet or DataTable via BinaryFormatter</span></span>

<span data-ttu-id="2043f-262">Deweloperzy nie muszą używać `BinaryFormatter` , `NetDataContractSerializer` , `SoapFormatter` ani pokrewnych ***niebezpiecznych*** elementów formatujących do deserializacji `DataSet` `DataTable` wystąpienia lub z niezaufanego ładunku:</span><span class="sxs-lookup"><span data-stu-id="2043f-262">Developers must never use `BinaryFormatter`, `NetDataContractSerializer`, `SoapFormatter`, or related ***unsafe*** formatters to deserialize a `DataSet` or `DataTable` instance from an untrusted payload:</span></span>

* <span data-ttu-id="2043f-263">Jest to podatne na pełny atak wykonywania kodu zdalnego.</span><span class="sxs-lookup"><span data-stu-id="2043f-263">This is susceptible to a full remote code execution attack.</span></span>
* <span data-ttu-id="2043f-264">Użycie niestandardowych `SerializationBinder` nie jest wystarczające, aby zapobiec takim atakom.</span><span class="sxs-lookup"><span data-stu-id="2043f-264">Using a custom `SerializationBinder` is not sufficient to prevent such an attack.</span></span>

## <a name="safe-replacements"></a><span data-ttu-id="2043f-265">Bezpieczne zamienniki</span><span class="sxs-lookup"><span data-stu-id="2043f-265">Safe replacements</span></span>

<span data-ttu-id="2043f-266">W przypadku aplikacji, które:</span><span class="sxs-lookup"><span data-stu-id="2043f-266">For apps that either:</span></span>

* <span data-ttu-id="2043f-267">Akceptuj `DataSet` lub `DataTable` za pomocą punktu końcowego protokołu SOAP lub punktu końcowego WCF.</span><span class="sxs-lookup"><span data-stu-id="2043f-267">Accept `DataSet` or `DataTable` through an .asmx SOAP endpoint or a WCF endpoint.</span></span>
* <span data-ttu-id="2043f-268">Deserializacja niezaufanych danych do wystąpienia `DataSet` lub `DataTable` .</span><span class="sxs-lookup"><span data-stu-id="2043f-268">Deserialize untrusted data into an instance of `DataSet` or `DataTable`.</span></span>

<span data-ttu-id="2043f-269">Rozważ zastępowanie modelu obiektów, aby użyć [Entity Framework](/ef).</span><span class="sxs-lookup"><span data-stu-id="2043f-269">Consider replacing the object model to use [Entity Framework](/ef).</span></span> <span data-ttu-id="2043f-270">Entity Framework:</span><span class="sxs-lookup"><span data-stu-id="2043f-270">Entity Framework:</span></span>

* <span data-ttu-id="2043f-271">To rozbudowana, nowoczesne, zorientowane obiektowo środowisko, które może reprezentować dane relacyjne.</span><span class="sxs-lookup"><span data-stu-id="2043f-271">Is a rich, modern, object-oriented framework that can represent relational data.</span></span>
* <span data-ttu-id="2043f-272">Program udostępnia [zróżnicowany ekosystem](/ef/core/providers/) dostawców baz danych, co ułatwia tworzenie zapytań w bazie danych przy użyciu modeli obiektów Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="2043f-272">Brings [a diverse ecosystem](/ef/core/providers/) of database providers to make it easy to project database queries via your Entity Framework object models.</span></span>
* <span data-ttu-id="2043f-273">Oferuje wbudowane zabezpieczenia podczas deserializacji danych z niezaufanych źródeł.</span><span class="sxs-lookup"><span data-stu-id="2043f-273">Offers built-in protections when deserializing data from untrusted sources.</span></span>

<span data-ttu-id="2043f-274">W przypadku aplikacji korzystających z `.aspx` punktów końcowych protokołu SOAP Rozważ zmianę tych punktów końcowych na potrzeby korzystania z [platformy WCF](../../../wcf/index.md).</span><span class="sxs-lookup"><span data-stu-id="2043f-274">For apps that use `.aspx` SOAP endpoints, consider changing those endpoints to use [WCF](../../../wcf/index.md).</span></span> <span data-ttu-id="2043f-275">WCF to bardziej zaproponowana wymiana `.asmx` usług sieci Web.</span><span class="sxs-lookup"><span data-stu-id="2043f-275">WCF is a more fully featured replacement for `.asmx` web services.</span></span> <span data-ttu-id="2043f-276">Punkty końcowe WCF [mogą być udostępniane za pośrednictwem protokołu SOAP](../../../wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md) w celu zapewnienia zgodności z istniejącymi wywołaniami.</span><span class="sxs-lookup"><span data-stu-id="2043f-276">WCF endpoints [can be exposed via SOAP](../../../wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md) for compatibility with existing callers.</span></span>

## <a name="code-analyzers"></a><span data-ttu-id="2043f-277">Analizatory kodu</span><span class="sxs-lookup"><span data-stu-id="2043f-277">Code analyzers</span></span>

<span data-ttu-id="2043f-278">Reguły zabezpieczeń analizatora kodu, które są uruchamiane podczas kompilowania kodu źródłowego, mogą pomóc w znalezieniu luk w zabezpieczeniach związanych z tym problemem z zabezpieczeniami w języku C# i Visual Basic kodzie.</span><span class="sxs-lookup"><span data-stu-id="2043f-278">Code analyzer security rules, which run when your source code is compiled, can help to find vulnerabilities related to this security issue in C# and Visual Basic code.</span></span> <span data-ttu-id="2043f-279">Microsoft. CodeAnalysis. FxCopAnalyzers to pakiet NuGet analizatorów kodu dystrybuowany na [NuGet.org](https://www.nuget.org/).</span><span class="sxs-lookup"><span data-stu-id="2043f-279">Microsoft.CodeAnalysis.FxCopAnalyzers is a NuGet package of code analyzers that's distributed on [nuget.org](https://www.nuget.org/).</span></span>

<span data-ttu-id="2043f-280">Aby zapoznać się z omówieniem analizatorów kodu, zobacz [Omówienie analizatorów kodu źródłowego](/visualstudio/code-quality/roslyn-analyzers-overview).</span><span class="sxs-lookup"><span data-stu-id="2043f-280">For an overview of code analyzers, see [Overview of source code analyzers](/visualstudio/code-quality/roslyn-analyzers-overview).</span></span>

<span data-ttu-id="2043f-281">Włącz następujące reguły Microsoft. CodeAnalysis. FxCopAnalyzers:</span><span class="sxs-lookup"><span data-stu-id="2043f-281">Enable the following Microsoft.CodeAnalysis.FxCopAnalyzers rules:</span></span>

- <span data-ttu-id="2043f-282">[CA2350](/visualstudio/code-quality/ca2350): nie należy używać elementu DataTable. ReadXml () z niezaufanymi danymi</span><span class="sxs-lookup"><span data-stu-id="2043f-282">[CA2350](/visualstudio/code-quality/ca2350): Do not use DataTable.ReadXml() with untrusted data</span></span>
- <span data-ttu-id="2043f-283">[CA2351](/visualstudio/code-quality/ca2351): nie należy używać zestawu danych. ReadXml () z niezaufanymi danymi</span><span class="sxs-lookup"><span data-stu-id="2043f-283">[CA2351](/visualstudio/code-quality/ca2351): Do not use DataSet.ReadXml() with untrusted data</span></span>
- <span data-ttu-id="2043f-284">[CA2352](/visualstudio/code-quality/ca2352): niebezpieczny zestaw danych lub DataTable w typie możliwym do serializacji może być narażony na ataki zdalnego wykonywania kodu</span><span class="sxs-lookup"><span data-stu-id="2043f-284">[CA2352](/visualstudio/code-quality/ca2352): Unsafe DataSet or DataTable in serializable type can be vulnerable to remote code execution attacks</span></span>
- <span data-ttu-id="2043f-285">[CA2353](/visualstudio/code-quality/ca2353): niebezpieczny zestaw danych lub DataTable w typie możliwym do serializacji</span><span class="sxs-lookup"><span data-stu-id="2043f-285">[CA2353](/visualstudio/code-quality/ca2353): Unsafe DataSet or DataTable in serializable type</span></span>
- <span data-ttu-id="2043f-286">[CA2354](/visualstudio/code-quality/ca2354): niebezpieczny zestaw danych lub DataTable w odszeregowanym grafie obiektów może być narażony na ataki zdalnego wykonywania kodu</span><span class="sxs-lookup"><span data-stu-id="2043f-286">[CA2354](/visualstudio/code-quality/ca2354): Unsafe DataSet or DataTable in deserialized object graph can be vulnerable to remote code execution attacks</span></span>
- <span data-ttu-id="2043f-287">[CA2355](/visualstudio/code-quality/ca2355): znaleziono niebezpieczny typ elementu dataset lub typu DataTable w grafie obiektu, który można zdeserializować</span><span class="sxs-lookup"><span data-stu-id="2043f-287">[CA2355](/visualstudio/code-quality/ca2355): Unsafe DataSet or DataTable type found in deserializable object graph</span></span>
- <span data-ttu-id="2043f-288">[CA2356](/visualstudio/code-quality/ca2356): niebezpieczny typ zestawu danych lub typu DataTable w grafie obiektów do serializacji sieci Web</span><span class="sxs-lookup"><span data-stu-id="2043f-288">[CA2356](/visualstudio/code-quality/ca2356): Unsafe DataSet or DataTable type in web deserializable object graph</span></span>
- <span data-ttu-id="2043f-289">[CA2361](/visualstudio/code-quality/ca2361): Upewnij się, że automatycznie wygenerowana Klasa zawierająca zestaw danych. ReadXml () nie jest używana z niezaufanymi danymi</span><span class="sxs-lookup"><span data-stu-id="2043f-289">[CA2361](/visualstudio/code-quality/ca2361): Ensure autogenerated class containing DataSet.ReadXml() is not used with untrusted data</span></span>
- <span data-ttu-id="2043f-290">[CA2362](/visualstudio/code-quality/ca2362): niebezpieczny zestaw danych lub DataTable w automatycznie generowanym typie możliwym do serializacji może być narażony na ataki zdalnego wykonywania kodu</span><span class="sxs-lookup"><span data-stu-id="2043f-290">[CA2362](/visualstudio/code-quality/ca2362): Unsafe DataSet or DataTable in autogenerated serializable type can be vulnerable to remote code execution attacks</span></span>

<span data-ttu-id="2043f-291">Aby uzyskać więcej informacji na temat konfigurowania reguł, zobacz [Korzystanie z analizatorów kodu](/visualstudio/code-quality/use-roslyn-analyzers).</span><span class="sxs-lookup"><span data-stu-id="2043f-291">For more information about configuring rules, see [Use code analyzers](/visualstudio/code-quality/use-roslyn-analyzers).</span></span>

<span data-ttu-id="2043f-292">Nowe reguły zabezpieczeń są dostępne w następujących pakietach NuGet:</span><span class="sxs-lookup"><span data-stu-id="2043f-292">The new security rules are available in the following NuGet packages:</span></span>

- <span data-ttu-id="2043f-293">Microsoft. CodeAnalysis. FxCopAnalyzers 3.3.0: for Visual Studio 2019 w wersji 16,3 lub nowszej</span><span class="sxs-lookup"><span data-stu-id="2043f-293">Microsoft.CodeAnalysis.FxCopAnalyzers 3.3.0: for Visual Studio 2019 version 16.3 or later</span></span>
- <span data-ttu-id="2043f-294">Microsoft. CodeAnalysis. FxCopAnalyzers 2.9.11: for Visual Studio 2017 w wersji 15,9 lub nowszej</span><span class="sxs-lookup"><span data-stu-id="2043f-294">Microsoft.CodeAnalysis.FxCopAnalyzers 2.9.11: for Visual Studio 2017 version 15.9 or later</span></span>
