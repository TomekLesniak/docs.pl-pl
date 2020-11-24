---
title: Interfejsy metadanych
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], metadata
- metadata interfaces [.NET Framework]
- interfaces (.NET Framework metadata]
ms.assetid: f5cdac93-a28c-48ef-8a19-5773376e9e7c
ms.openlocfilehash: 5d9b48df740668797a7c901219401e9ea304a8f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672884"
---
# <a name="metadata-interfaces"></a>Interfejsy metadanych

W tej sekcji opisano niezarządzane interfejsy, które zapewniają dostęp do metadanych uwidocznionych przez typy .NET Framework, metody, pola itd.  
  
## <a name="in-this-section"></a>W tej sekcji  

 [ICeeGen — Interfejs](iceegen-interface.md)  
 Zapewnia metody dynamicznego kompilowania kodu.  
  
 [IHostFilter — Interfejs](ihostfilter-interface.md)  
 Zapewnia metodę dla hosta czasu wykonywania, aby oznaczyć tokeny metadanych do przetwarzania.  
  
 [IMapToken — Interfejs](imaptoken-interface.md)  
 Oferuje możliwości mapowania między zaimportowanymi i emitowanymi sygnaturami metadanych.  
  
 [IMetaDataAssemblyEmit — Interfejs](imetadataassemblyemit-interface.md)  
 Dostarcza metody, które obsługują model z własnymi opisami używany przez środowisko uruchomieniowe języka wspólnego (CLR) do rozwiązywania i korzystania z zasobów.  
  
 [IMetaDataAssemblyImport — Interfejs](imetadataassemblyimport-interface.md)  
 Zapewnia metody umożliwiające dostęp i sprawdzanie zawartości manifestu zestawu.  
  
 [IMetaDataConverter — Interfejs](imetadataconverter-interface.md)  
 Zapewnia metody mapowania bibliotek typów na ich sygnatury metadanych oraz do konwersji między nimi.  
  
 [IMetaDataDispenser — Interfejs](imetadatadispenser-interface.md)  
 `IMetaDataDispenser` jest przestarzały. Zamiast tego użyj polecenia cmdlet `IMetaDataDispenserEx`.  
  
 [IMetaDataDispenserEx — Interfejs](imetadatadispenserex-interface.md)  
 Dostarcza metody, które mapują obszary pamięci do tworzenia lub modyfikowania metadanych.  
  
 [IMetaDataEmit — Interfejs](imetadataemit-interface.md)  
 Zapewnia metody tworzenia, modyfikowania i przechowywania metadanych dotyczących zestawu w aktualnie zdefiniowanym zakresie.  
  
 [IMetaDataEmit2 — Interfejs](imetadataemit2-interface.md)  
 Zapewnia metody definiowania i modyfikowania sygnatur metadanych metod i konstruktorów z parametrami typu <xref:System.Type?displayProperty=nameWithType> .  
  
 [IMetaDataError — Interfejs](imetadataerror-interface.md)  
 Zapewnia mechanizm wywołania zwrotnego do raportowania błędów podczas rozpoznawania podpisu metadanych dla zestawu.  
  
 [IMetaDataFilter — Interfejs](imetadatafilter-interface.md)  
 Zapewnia metody oznaczania i filtrowania tokenów metadanych, aby uniknąć powtarzających się akcji, które zostały już wykonane.  
  
 [IMetaDataImport — Interfejs](imetadataimport-interface.md)  
 Zapewnia metody importowania typów z innych zestawów i manipulowania nimi.  
  
 [IMetaDataImport2 — Interfejs](imetadataimport2-interface.md)  
 Rozszerza, `IMetaDataImport` Aby zapewnić możliwość pracy z typami ogólnymi.  
  
 [IMetaDataInfo — Interfejs](imetadatainfo-interface.md)  
 Zapewnia metodę, która pobiera informacje o mapowaniu metadanych z pliku na dysku do pamięci.  
  
 [IMetaDataTables — Interfejs](imetadatatables-interface.md)  
 Zapewnia metody przechowywania i pobierania informacji o metadanych w tabelach.  
  
 [IMetaDataTables2 — Interfejs](imetadatatables2-interface.md)  
 Rozszerza `IMetaDataTables` , aby uwzględnić metody pracy z strumieniami metadanych.  
  
 [IMetaDataValidate — Interfejs](imetadatavalidate-interface.md)  
 Zapewnia metody do użycia w celu walidacji sygnatur metadanych.  
  
## <a name="related-sections"></a>Sekcje pokrewne  

 [Statyczne funkcje globalne metadanych](metadata-global-static-functions.md)  
  
 [Wyliczenia metadanych](metadata-enumerations.md)  
  
 [Metadane — Struktury](metadata-structures.md)  
  
 [Unie metadanych](metadata-unions.md)
