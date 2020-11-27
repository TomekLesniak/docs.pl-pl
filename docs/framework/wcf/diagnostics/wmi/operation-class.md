---
title: Operation — klasa
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 6b47d933dc84813532398830c92c95210208a709
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/26/2020
ms.locfileid: "96269161"
---
# <a name="operation-class"></a>Operation — klasa

Operacja  
  
## <a name="syntax"></a>Składnia  
  
```csharp
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## <a name="methods"></a>Metody  

 Klasa operacji nie definiuje żadnych metod.  
  
## <a name="properties"></a>Właściwości  

 Klasa operacji ma następujące właściwości:  
  
### <a name="action"></a>Akcja  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Akcja WS-Addressing komunikatu żądania.  
  
### <a name="asyncpattern"></a>AsyncPattern  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wskazuje, że operacja jest zaimplementowana asynchronicznie za pomocą `Begin` pary metod [Open/Close Angle] i `End` [nawias ostry "Open/Close] w kontrakcie usługi.  
  
### <a name="behaviors"></a>Zachowania  

 Typ danych: tablica zachowań  
  
 Typ dostępu: tylko do odczytu  
  
 Zachowania skojarzone z tą operacją.  
  
### <a name="iscallback"></a>IsCallback  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość true, gdy operacja jest operacją wywołania zwrotnego.  
  
### <a name="isinitiating"></a>Operację IsInitiating  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wskazuje, czy metoda implementuje operację, która może inicjować sesję na serwerze.  
  
### <a name="isoneway"></a>IsOneWay  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wskazuje, czy operacja zwraca komunikat odpowiedzi.  
  
### <a name="isterminating"></a>IsTerminating  

 Typ danych: wartość logiczna  
  
 Typ dostępu: tylko do odczytu  
  
 Wskazuje, czy operacja zwraca komunikat odpowiedzi.  
  
### <a name="methodsignature"></a>MethodSignature  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Podpis metody operacji.  
  
### <a name="name"></a>Nazwa  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Nazwa operacji.  
  
### <a name="parametertypes"></a>ParameterTypes  

 Typ danych: tablica ciągów  
  
 Typ dostępu: tylko do odczytu  
  
 Typy parametrów operacji.  
  
### <a name="replyaction"></a>ReplyAction  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Wartość akcji protokołu SOAP dla komunikatu odpowiedzi operacji.  
  
### <a name="returntype"></a>Atrybuty  

 Typ danych: ciąg  
  
 Typ dostępu: tylko do odczytu  
  
 Zwracany typ operacji.  
  
## <a name="requirements"></a>Wymagania  
  
|PLIK|Zadeklarowany w ServiceModel. mof.|  
|---------|-----------------------------------|  
|Przestrzeń nazw|Zdefiniowane w root\ServiceModel|  
  
## <a name="see-also"></a>Zobacz też

- <xref:System.ServiceModel.Description.OperationDescription>
