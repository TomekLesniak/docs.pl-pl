---
ms.openlocfilehash: f011f6ebe0fa85a59f3e69c93bba9eddc4c1689b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497022"
---
### <a name="reflection-objects-can-no-longer-be-passed-from-managed-code-to-out-of-process-dcom-clients"></a>Obiektów odbicia nie można już przekazywać z kodu zarządzanego do pozaprocesowych klientów DCOM.

#### <a name="details"></a>Szczegóły

Obiektów odbicia nie można już przekazywać z kodu zarządzanego do pozaprocesowych klientów DCOM. Dotyczy to następujących typów:

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <xref:System.Reflection.MemberInfo?displayProperty=fullName> (i jego typy pochodne, w tym <xref:System.Reflection.FieldInfo?displayProperty=fullName> , <xref:System.Reflection.MethodInfo?displayProperty=fullName> , <xref:System.Type?displayProperty=fullName> i <xref:System.Reflection.TypeInfo?displayProperty=fullName> )
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>

Wywołania do <code>IMarshal</code> zwracanego obiektu <code>E_NOINTERFACE</code> .

#### <a name="suggestion"></a>Sugestia

Aktualizuj kod kierujący do pracy z obiektami nieodbicia.

| Nazwa    | Wartość       |
|:--------|:------------|
| Zakres   |Mały|
|Wersja|4,6|
|Typ|Środowisko uruchomieniowe|

#### <a name="affected-apis"></a>Dotyczy interfejsów API

- <xref:System.Reflection.Assembly?displayProperty=fullName>
- <xref:System.Reflection.FieldInfo?displayProperty=fullName>
- <xref:System.Reflection.MemberInfo?displayProperty=fullName>
- <xref:System.Reflection.MethodBody?displayProperty=fullName>
- <xref:System.Reflection.MethodInfo?displayProperty=fullName>
- <xref:System.Reflection.Module?displayProperty=fullName>
- <xref:System.Reflection.ParameterInfo?displayProperty=fullName>
- <xref:System.Reflection.TypeInfo?displayProperty=fullName>
- <xref:System.Type?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Reflection.Assembly`
- `T:System.Reflection.FieldInfo`
- `T:System.Reflection.MemberInfo`
- `T:System.Reflection.MethodBody`
- `T:System.Reflection.MethodInfo`
- `T:System.Reflection.Module`
- `T:System.Reflection.ParameterInfo`
- `T:System.Reflection.TypeInfo`
- `T:System.Type`

-->
