---
title: Narzędzie Contract-First
ms.date: 03/30/2017
ms.assetid: 0a880690-f460-4475-a5f4-9f91ce08fcc6
ms.openlocfilehash: 1896a76892c76fb7277c3e36978604a4d290018e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255133"
---
# <a name="contract-first-tool"></a>Narzędzie Contract-First

Kontrakty usług często muszą być tworzone na podstawie istniejących usług. W .NET Framework 4,5 i nowszych klasy kontraktów danych mogą być tworzone automatycznie z istniejących usług przy użyciu narzędzia kontrakt-pierwsze. Aby można było użyć narzędzia kontraktu, plik definicji schematu XML (XSD) musi zostać pobrany lokalnie; Narzędzie nie może importować kontraktów danych zdalnych za pośrednictwem protokołu HTTP.

 Narzędzie pierwszy kontrakt jest zintegrowane z Visual Studio 2012 jako zadanie kompilacji. Pliki kodu generowane przez zadanie kompilacji są tworzone za każdym razem, gdy projekt został skompilowany, dzięki czemu projekt może łatwo przyjąć zmiany w podstawowym kontrakcie usługi.

 Typy schematów, które może zaimportować narzędzie kontraktu, obejmują następujące elementy:

```xml
<xsd:complexType>
 <xsd:simpleType>
 </xsd:simpleType>
</xsd:complexType>
```

 Typy proste nie będą generowane, jeśli są to elementy pierwotne, takie jak `Int16` lub `String` ; typy złożone nie będą generowane, jeśli są typu `Collection` . Typy nie będą również generowane, jeśli są częścią innego `xsd:complexType` . We wszystkich tych przypadkach do typów zostaną przywoływane istniejące typy w projekcie.

## <a name="adding-a-data-contract-to-a-project"></a>Dodawanie kontraktu danych do projektu

 Aby można było użyć narzędzia pierwszego kontraktu, do projektu należy dodać kontrakt usługi (XSD). Na potrzeby tego omówienia do zilustrowania funkcji pierwszego kontraktu zostanie użyty następujący kontrakt. Ta definicja usługi jest małym podzbiorem kontraktu usługi używanego przez interfejs API wyszukiwania w usłudze Bing.

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="ServiceSchema"
    targetNamespace="http://tempuri.org/ServiceSchema.xsd"
    elementFormDefault="qualified"
    xmlns="http://tempuri.org/ServiceSchema.xsd"
    xmlns:mstns="http://tempuri.org/ServiceSchema.xsd"
    xmlns:xs="http://www.w3.org/2001/XMLSchema"
>
  <xs:complexType name="SearchRequest">
    <xs:sequence>
      <xs:element minOccurs="0" maxOccurs="1" name="Version" type="xs:string" default="2.2" />
      <xs:element minOccurs="0" maxOccurs="1" name="Market" type="xs:string" />
      <xs:element minOccurs="0" maxOccurs="1" name="UILanguage" type="xs:string" />
      <xs:element minOccurs="1" maxOccurs="1" name="Query" type="xs:string" />
      <xs:element minOccurs="1" maxOccurs="1" name="AppId" type="xs:string" />
      <xs:element minOccurs="0" maxOccurs="1" name="Latitude" type="xs:double" />
      <xs:element minOccurs="0" maxOccurs="1" name="Longitude" type="xs:double" />
      <xs:element minOccurs="0" maxOccurs="1" name="Radius" type="xs:double" />
    </xs:sequence>
  </xs:complexType>
  <xs:simpleType name="WebSearchOption">
    <xs:restriction base="xs:string">
      <xs:enumeration value="DisableHostCollapsing" />
      <xs:enumeration value="DisableQueryAlterations" />
    </xs:restriction>
  </xs:simpleType>
</xs:schema>
```

 Aby dodać powyższy kontrakt usługi do projektu, kliknij prawym przyciskiem myszy projekt i wybierz polecenie **Dodaj nowy..**.. Wybierz pozycję definicja schematu w okienku WCF okna dialogowego szablony i Nadaj nowemu plikowi nazwę SampleContract. xsd. Skopiuj i wklej powyższy kod do widoku Kod nowego pliku.

## <a name="configuring-contract-first-options"></a>Konfigurowanie kontraktu — opcje pierwszego

 Opcje kontraktu — pierwsze można skonfigurować w menu właściwości projektu WCF. Aby włączyć programowanie pierwszego kontraktu, zaznacz pole wyboru **Włącz XSD jako język definicji typu** na stronie WCF okna właściwości projektu.

 ![Zrzut ekranu przedstawiający opcje WCF z włączonym programowaniem w pierwszej kolejności.](./media/contract-first-tool/contract-first-options.png)

 Aby skonfigurować właściwości zaawansowane, kliknij przycisk Zaawansowane.

 ![Zaawansowane ustawienia generowania kodu kontraktu — okno dialogowe.](./media/contract-first-tool/advanced-contract-settings.png)

 Poniższe ustawienia zaawansowane można skonfigurować do generowania kodu z umów. Ustawienia można skonfigurować tylko dla wszystkich plików w projekcie; w tej chwili nie można skonfigurować ustawień dla poszczególnych plików.

- **Tryb serializatora**: to ustawienie określa, który serializator jest używany do odczytywania plików kontraktu usługi. Po wybraniu **serializatora XML** , **typy kolekcji** i opcje **ponownego użycia** są wyłączone. Te opcje mają zastosowanie tylko do **serializatora kontraktu danych**.

- **Użyj ponownie typów**: to ustawienie określa, które biblioteki są używane do ponownego użycia. To ustawienie ma zastosowanie tylko wtedy, gdy **tryb serializatora** jest ustawiony na **serializator kontraktu danych**.

- **Typ kolekcji**: to ustawienie określa w pełni kwalifikowana lub kwalifikowana dla zestawu typ, który ma być używany jako typ danych kolekcji. To ustawienie ma zastosowanie tylko wtedy, gdy **tryb serializatora** jest ustawiony na **serializator kontraktu danych**.

- **Typ słownika**: to ustawienie określa w pełni kwalifikowana lub kwalifikowana dla zestawu typ, który ma być używany jako typ danych słownika.

- **EnableDataBinding**: to ustawienie określa, czy zaimplementować <xref:System.ComponentModel.INotifyPropertyChanged> interfejs dla wszystkich typów danych w celu wdrożenia powiązania danych.

- **ExcludedTypes**: to ustawienie określa listę w pełni kwalifikowanych lub kwalifikowanych do zestawu typów, które mają być wykluczone z zestawów, do których się odwołuje. To ustawienie ma zastosowanie tylko wtedy, gdy **tryb serializatora** jest ustawiony na **serializator kontraktu danych**.

- **GenerateInternalTypes**: to ustawienie określa, czy mają zostać wygenerowane klasy, które są oznaczone jako wewnętrzne. To ustawienie ma zastosowanie tylko wtedy, gdy **tryb serializatora** jest ustawiony na **serializator kontraktu danych**.

- **GenerateSerializableTypes**: to ustawienie określa, czy generować klasy z <xref:System.SerializableAttribute> atrybutem. To ustawienie ma zastosowanie tylko wtedy, gdy **tryb serializatora** jest ustawiony na **serializator kontraktu danych**.

- **ImportXmlTypes**: to ustawienie określa, czy należy skonfigurować serializator kontraktu danych, aby zastosować <xref:System.SerializableAttribute> atrybut do klas bez <xref:System.Runtime.Serialization.DataContractAttribute> atrybutu.  To ustawienie ma zastosowanie tylko wtedy, gdy **tryb serializatora** jest ustawiony na **serializator kontraktu danych**.

- **SupportFx35TypedDataSets**: to ustawienie określa, czy należy udostępnić dodatkowe funkcje dla wpisanych zestawów danych utworzonych dla .NET Framework 3,5. Gdy  **tryb serializatora** jest ustawiony na **Serializator XML**, <xref:System.Data.Design.TypedDataSetSchemaImporterExtensionFx35> rozszerzenie zostanie dodane do importera schematu XML, gdy ta wartość jest ustawiona na true. Gdy  **tryb serializatora** jest ustawiony na **serializator kontraktu danych**, typ <xref:System.DateTimeOffset> zostanie wykluczony z odwołań, gdy ta wartość zostanie ustawiona na wartość false, tak aby <xref:System.DateTimeOffset> zawsze była generowana dla starszych wersji struktury.

- **InputXsdFiles**: to ustawienie określa listę plików wejściowych. Każdy plik musi zawierać prawidłowy schemat XML.

- **Język**: to ustawienie określa język wygenerowanego kodu kontraktu. Ustawienie musi być rozpoznawalne przez program <xref:System.CodeDom.Compiler.CodeDomProvider> .

- **NamespaceMappings**: to ustawienie określa mapowania z przestrzeni nazw obiektów docelowych XSD na przestrzenie nazw środowiska CLR. Każde mapowanie powinno mieć następujący format:

    ```xml
    "Schema Namespace, CLR Namespace"
    ```

     Serializator XML akceptuje tylko jedno mapowanie w następującym formacie:

    ```xml
    "*, CLR Namespace"
    ```

- **OutputDirectory**: to ustawienie określa katalog, w którym będą generowane pliki kodu.

 Ustawienia te zostaną użyte do wygenerowania typów kontraktu usługi z plików umów serwisowych podczas kompilowania projektu.

## <a name="using-contract-first-development"></a>Korzystanie z kontraktu — pierwsze programowanie

 Po dodaniu kontraktu usługi do projektu i potwierdzeniu ustawień kompilacji Skompiluj projekt, naciskając klawisz **F6**. Typy zdefiniowane w kontrakcie usługi będą następnie dostępne do użycia w projekcie.

 Aby użyć typów zdefiniowanych w kontrakcie usługi, Dodaj odwołanie do `ContractTypes` pod bieżącą przestrzenią nazw:

```csharp
using MyProjectNamespace.ContractTypes;
```

 Typy zdefiniowane w kontrakcie usługi zostaną następnie rozpoznawalne w projekcie, jak pokazano poniżej:

 ![Klasa SearchRequest wyświetlana w technologii IntelliSense po wpisaniu kilku pierwszych liter.](./media/contract-first-tool/service-contract-types.png)

 Typy generowane przez narzędzie są tworzone w pliku GeneratedXSDTypes.cs. Plik jest domyślnie tworzony w \<project directory> katalogu/obj/ \<build configuration> /XSDGeneratedCode/. Przykładowy schemat na początku tego artykułu został przekonwertowany w następujący sposób:

```csharp
//------------------------------------------------------------------------------
// <auto-generated>
//     This code was generated by a tool.
//     Runtime Version:4.0.30319.17330
//
//     Changes to this file may cause incorrect behavior and will be lost if
//     the code is regenerated.
// </auto-generated>
//------------------------------------------------------------------------------

namespace TestXSD3.ContractTypes
{
    using System.Xml.Serialization;

    /// <remarks/>
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]
    [System.SerializableAttribute()]
    [System.Diagnostics.DebuggerStepThroughAttribute()]
    [System.ComponentModel.DesignerCategoryAttribute("code")]
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=true)]
    public partial class SearchRequest
    {

        private string versionField;

        private string marketField;

        private string uILanguageField;

        private string queryField;

        private string appIdField;

        private double latitudeField;

        private bool latitudeFieldSpecified;

        private double longitudeField;

        private bool longitudeFieldSpecified;

        private double radiusField;

        private bool radiusFieldSpecified;

        public SearchRequest()
        {
            this.versionField = "2.2";
        }

        /// <remarks/>
        [System.ComponentModel.DefaultValueAttribute("2.2")]
        public string Version
        {
            get
            {
                return this.versionField;
            }
            set
            {
                this.versionField = value;
            }
        }

        /// <remarks/>
        public string Market
        {
            get
            {
                return this.marketField;
            }
            set
            {
                this.marketField = value;
            }
        }

        /// <remarks/>
        public string UILanguage
        {
            get
            {
                return this.uILanguageField;
            }
            set
            {
                this.uILanguageField = value;
            }
        }

        /// <remarks/>
        public string Query
        {
            get
            {
                return this.queryField;
            }
            set
            {
                this.queryField = value;
            }
        }

        /// <remarks/>
        public string AppId
        {
            get
            {
                return this.appIdField;
            }
            set
            {
                this.appIdField = value;
            }
        }

        /// <remarks/>
        public double Latitude
        {
            get
            {
                return this.latitudeField;
            }
            set
            {
                this.latitudeField = value;
            }
        }

        /// <remarks/>
        [System.Xml.Serialization.XmlIgnoreAttribute()]
        public bool LatitudeSpecified
        {
            get
            {
                return this.latitudeFieldSpecified;
            }
            set
            {
                this.latitudeFieldSpecified = value;
            }
        }

        /// <remarks/>
        public double Longitude
        {
            get
            {
                return this.longitudeField;
            }
            set
            {
                this.longitudeField = value;
            }
        }

        /// <remarks/>
        [System.Xml.Serialization.XmlIgnoreAttribute()]
        public bool LongitudeSpecified
        {
            get
            {
                return this.longitudeFieldSpecified;
            }
            set
            {
                this.longitudeFieldSpecified = value;
            }
        }

        /// <remarks/>
        public double Radius
        {
            get
            {
                return this.radiusField;
            }
            set
            {
                this.radiusField = value;
            }
        }

        /// <remarks/>
        [System.Xml.Serialization.XmlIgnoreAttribute()]
        public bool RadiusSpecified
        {
            get
            {
                return this.radiusFieldSpecified;
            }
            set
            {
                this.radiusFieldSpecified = value;
            }
        }
    }

    /// <remarks/>
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]
    [System.SerializableAttribute()]
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=false)]
    public enum WebSearchOption
    {

        /// <remarks/>
        DisableHostCollapsing,

        /// <remarks/>
        DisableQueryAlterations,
    }
}
```

## <a name="errors-and-warnings"></a>Błędy i ostrzeżenia

 Błędy i ostrzeżenia napotkane podczas analizowania schematu XSD będą wyświetlane jako błędy kompilacji i ostrzeżenia.

## <a name="interface-inheritance"></a>Dziedziczenie interfejsu

 Nie można używać dziedziczenia interfejsów w przypadku tworzenia kontraktu. jest to zgodne z sposobem zachowania interfejsów w innych operacjach. Aby można było użyć interfejsu, który dziedziczy interfejs podstawowy, należy użyć dwóch oddzielnych punktów końcowych. Pierwszy punkt końcowy używa dziedziczonego kontraktu, a drugi punkt końcowy implementuje interfejs podstawowy.
