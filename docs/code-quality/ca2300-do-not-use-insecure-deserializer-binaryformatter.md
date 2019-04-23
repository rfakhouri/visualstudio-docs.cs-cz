---
title: 'CA2300: Nepoužívat nezabezpečený deserializátor BinaryFormatter'
ms.date: 04/05/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 400c259cf7aac5b6f3ea4a6c196ebaa77e29289b
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60079633"
---
# <a name="ca2300-do-not-use-insecure-deserializer-binaryformatter"></a>CA2300: Nepoužívat nezabezpečený deserializátor BinaryFormatter

|||
|-|-|
|TypeName|DoNotUseInsecureDeserializerBinaryFormatter|
|CheckId|CA2300|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

A <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> metody deserializace byla volána nebo odkazovat.

## <a name="rule-description"></a>Popis pravidla

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

Toto pravidlo vyhledá <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> deserializace volání metody nebo odkazy. Pokud chcete k deserializaci pouze tehdy, když <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> je nastavena na omezení typů, vypněte toto pravidlo a povolit pravidla [CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md) a [CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md) místo.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

- Pokud je to možné, použijte zabezpečené serializátor, a **Nepovolit útočníkovi zadat libovolný typ k deserializaci**. Některé bezpečnější serializátory patří:
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -Nikdy nepoužívejte <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>. Pokud je nutné použít typ překladače, omezení deserializovaný typy k očekávaným seznamem.
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - NewtonSoft Json.NET - TypeNameHandling.None použití. Pokud musíte použít jinou hodnotu pro TypeNameHandling, omezte na očekávaným seznamem s vlastní ISerializationBinder deserializovaný typy.
  - Protocol Buffers
- Ujistěte se, manipulací serializovaná data. Po serializaci podepište kryptograficky serializovaná data. Před deserializace ověřte kryptografický podpis. Je zveřejněn chránit kryptografické klíče a návrh pro rotace klíčů.
- Zakázání deserializovaný typů. Implementovat vlastní <xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>. Před deserializace s <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>, nastavte <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> vlastnost instance vašeho vlastního <xref:System.Runtime.Serialization.SerializationBinder>. V přepsané <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> metodu, pokud neočekávaný typ poté vyvolají výjimku.
- Pokud omezíte deserializovaný typy, můžete toto pravidlo zakázání a povolení pravidla [CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md) a [CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md). Pravidla [CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md) a [CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md) zobrazíte nápovědu, jak zajistit, aby <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> před deserializace je vždy nastavena vlastnost.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

[!INCLUDE[insecure-deserializers-common-safe-to-suppress](includes/insecure-deserializers-common-safe-to-suppress-md.md)]

## <a name="pseudo-code-examples"></a>Příklady pseudo kódu

### <a name="violation"></a>Porušení

```csharp
using System.IO;
using System.Runtime.Serialization.Formatters.Binary;

public class ExampleClass
{
    public object MyDeserialize(byte[] bytes)
    {
        BinaryFormatter formatter = new BinaryFormatter();
        return formatter.Deserialize(new MemoryStream(bytes));
    }
}
```

```vb
Imports System.IO
Imports System.Runtime.Serialization.Formatters.Binary

Public Class ExampleClass
    Public Function MyDeserialize(bytes As Byte()) As Object
        Dim formatter As BinaryFormatter = New BinaryFormatter()
        Return formatter.Deserialize(New MemoryStream(bytes))
    End Function
End Class
```

## <a name="related-rules"></a>Související pravidla

[CA2301: Nevolejte BinaryFormatter.Deserialize bez první nastavení BinaryFormatter.Binder](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md)

[CA2302: Ujistěte se, že BinaryFormatter.Binder nastavený před voláním BinaryFormatter.Deserialize](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md)