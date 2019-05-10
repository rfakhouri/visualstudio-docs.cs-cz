---
title: 'CA2305: Nepoužívejte nezabezpečené deserializátor LosFormatter'
ms.date: 05/01/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
f1_keywords:
- CA2305
- DoNotUseInsecureDeserializerLosFormatter
ms.openlocfilehash: 4e589bbea53dd6a73a6e6e4fc44b6cb397d6dcbd
ms.sourcegitcommit: db30651dc0ce4d0b274479b23a6bd102a5559098
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/06/2019
ms.locfileid: "65135566"
---
# <a name="ca2305-do-not-use-insecure-deserializer-losformatter"></a>CA2305: Nepoužívejte nezabezpečené deserializátor LosFormatter

|||
|-|-|
|TypeName|DoNotUseInsecureDeserializerLosFormatter|
|CheckId|CA2305|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

A <xref:System.Web.UI.LosFormatter?displayProperty=nameWithType> metody deserializace byla volána nebo odkazovat.

## <a name="rule-description"></a>Popis pravidla

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

Toto pravidlo vyhledá <xref:System.Web.UI.LosFormatter?displayProperty=nameWithType> deserializace volání metody nebo odkazy.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

[!INCLUDE[insecure-deserializers-fixes-for-always-insecure-deserializers](includes/insecure-deserializers-fixes-for-always-insecure-deserializers-md.md)]

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

[!INCLUDE[insecure-deserializers-common-safe-to-suppress](includes/insecure-deserializers-common-safe-to-suppress-md.md)]

## <a name="pseudo-code-examples"></a>Příklady pseudo kódu

### <a name="violation"></a>Porušení

```csharp
using System.IO;
using System.Web.UI;

public class ExampleClass
{
    public object MyDeserialize(byte[] bytes)
    {
        LosFormatter formatter = new LosFormatter();
        return formatter.Deserialize(new MemoryStream(bytes));
    }
}
```

```vb
Imports System.IO
Imports System.Web.UI

Public Class ExampleClass
    Public Function MyDeserialize(bytes As Byte()) As Object
        Dim formatter As LosFormatter = New LosFormatter()
        Return formatter.Deserialize(New MemoryStream(bytes))
    End Function
End Class
```