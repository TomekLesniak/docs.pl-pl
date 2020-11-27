---
title: Dokumentacja interfejsu API odbicia dla platformy .NET Native
ms.date: 03/30/2017
ms.assetid: 0429c049-22a3-4ba1-9cc8-f6ee91e31d9c
ms.openlocfilehash: 4cded310397ffa4dea057899b6f008146d35a03b
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96250882"
---
# <a name="net-native-reflection-api-reference"></a>Dokumentacja interfejsu API odbicia dla platformy .NET Native

.NET Native obejmuje trzy nowe typy wyjątków: [System. Runtime. CompilerServices. MissingInteropDataException](missinginteropdataexception-class-net-native.md), [System. odbicie. MissingMetadataException](missingmetadataexception-class-net-native.md)oraz [System. odbicie. MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md). Zwróć uwagę na następujące informacje o wszystkich trzech typach wyjątków:  
  
 Te typy są przeznaczone tylko do użytku wewnętrznego.  
 Te trzy typy wyjątków służą tylko do używania łańcucha narzędzi .NET Native. Wyjątki są generowane, gdy łańcuch narzędzi .NET Native wykrywa brakujące dane, które nie zezwalają na kontynuowanie wykonywania programu.  
  
 Nie należy obsługiwać tych wyjątków w kodzie.  
 Te wyjątki wskazują, że brak metadanych wymaganych przez aplikację (wyjątki [MissingInteropDataException](missinginteropdataexception-class-net-native.md) i [MissingMetadataException](missingmetadataexception-class-net-native.md) ) lub kod implementacji wymagany przez aplikację (wyjątek [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) ). Te warunki wyjątków można poprawić, modyfikując plik dyrektywy środowiska uruchomieniowego (.rd.xml), aby udostępnić wymagane metadane lub kod implementacji w czasie wykonywania. Aby uzyskać więcej informacji, zobacz [Dokumentacja pliku konfiguracji dyrektyw środowiska uruchomieniowego (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md). Dostępne są dwa narzędzia do rozwiązywania problemów, które dostarczają odpowiednich wpisów dla plików dyrektywy środowiska uruchomieniowego, które spowodują eliminację wyjątków [MissingMetadataException](missingmetadataexception-class-net-native.md) i [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) :  
  
- [Narzędzie do rozwiązywania problemów z MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) dla typów.  
  
- [Narzędzie do rozwiązywania problemów z MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) .  
  
> [!NOTE]
> Ta dokumentacja dokumentuje trzy typy wyjątków, które są unikatowe dla .NET Native. Aby uzyskać dokumentację referencyjną dla podstawowego interfejsu API odbicia .NET Framework, zobacz <xref:System.Reflection> <xref:System.Reflection.Context> <xref:System.Reflection.Emit> przestrzenie nazw i. Aby uzyskać dokumentację referencyjną .NET Framework podstawowego interfejsu API międzyoperacyjności, zobacz <xref:System.Runtime.InteropServices> .  
  
## <a name="systemreflection-namespace"></a>Przestrzeń nazw System. odbicie  

 <xref:System.Reflection>Przestrzeń nazw zawiera podstawowe typy używane do odbicia w .NET Framework. W przypadku .NET Native zawiera również dwa nowe typy wyjątków:  
  
|Klasa|Opis|  
|-----------|-----------------|  
|[MissingMetadataException](missingmetadataexception-class-net-native.md)|Wyjątek, który jest generowany, gdy odbicie jest używane do pobierania nieobecnych metadanych.|  
|[MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)|Wyjątek, który jest generowany, gdy jest dostępny metadanych typu lub elementu członkowskiego typu, ale jego implementacja została usunięta.|  
  
 Aby uzyskać dokumentację dotyczącą innych typów w tej przestrzeni nazw, zobacz <xref:System.Reflection> strony referencyjne w zestawie dokumentacji .NET Framework.  
  
## <a name="systemruntimecompilerservices-namespace"></a>Przestrzeń nazw System. Runtime. CompilerServices  

 <xref:System.Runtime.CompilerServices>Przestrzeń nazw zawiera typy zaprojektowane dla użytkownika przez kompilatory języka. W przypadku .NET Native zawiera również nowy typ wyjątku:  
  
|Klasa|Opis|  
|-----------|-----------------|  
|[MissingInteropDataException](missinginteropdataexception-class-net-native.md)|Wyjątek, który jest generowany, gdy wywoływana jest metoda ręcznego kierowania, ale nie można odnaleźć metadanych dla typu przez analizę statyczną lub plik dyrektywy środowiska uruchomieniowego.|  
  
 Aby uzyskać dokumentację dotyczącą innych typów w tej przestrzeni nazw, zobacz <xref:System.Runtime.CompilerServices> strony referencyjne w zestawie dokumentacji .NET Framework.  
  
## <a name="see-also"></a>Zobacz też

- [Klasa MissingInteropDataException](missinginteropdataexception-class-net-native.md)
- [Klasa MissingMetadataException](missingmetadataexception-class-net-native.md)
- [Klasa MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)
- [Wprowadzenie](getting-started-with-net-native.md)
