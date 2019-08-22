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
f1_keywords:
- CA2300
- DoNotUseInsecureDeserializerBinaryFormatter
ms.openlocfilehash: 8a2bc2929b53843749d939f16057a11c0e944e33
ms.sourcegitcommit: 673b9364fc9a96b027662dcb4cf5d61cab60ef11
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/21/2019
ms.locfileid: "69891212"
---
# <a name="ca2300-do-not-use-insecure-deserializer-binaryformatter"></a>CA2300: Nepoužívat nezabezpečený deserializátor BinaryFormatter

|||
|-|-|
|TypeName|DoNotUseInsecureDeserializerBinaryFormatter|
|CheckId|CA2300|
|Kategorie|Microsoft.Security|
|Narušující změna|Bez přerušení|

## <a name="cause"></a>příčina

<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> Byla volána nebo odkazována metoda deserializace.

## <a name="rule-description"></a>Popis pravidla

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

Toto pravidlo vyhledá <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=nameWithType> volání nebo odkazy metody deserializace. Pokud chcete provést deserializaci pouze v případě <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> , že je vlastnost nastavena na hodnotu omezit typy, zakažte toto pravidlo a místo toho povolte pravidla [CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md) a [CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md) .

## <a name="how-to-fix-violations"></a>Jak opravit porušení

- Pokud je to možné, použijte místo toho zabezpečený serializátor a nepovolujte **útočníkovi zadání libovolného typu k**deserializaci. Mezi bezpečnější serializátory patří:
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType>– Nikdy nepoužívejte <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>. Pokud je nutné použít překladač typů, omezte deserializovatelné typy na očekávaný seznam.
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - Newtonsoft Json.NET – použijte TypeNameHandling. None. Pokud je nutné použít jinou hodnotu pro TypeNameHandling, omezte deserializovatelné typy na očekávaný seznam pomocí vlastního ISerializationBinder.
  - Vyrovnávací paměti protokolu
- Proveďte serializovanou manipulaci s daty. Po serializaci kryptograficky podepisují Serializovaná data. Před deserializací ověřte kryptografický podpis. Chránit kryptografický klíč před zveřejněním a návrhem pro střídání klíčů.
- Omezí deserializovatelné typy. Implementujte vlastní <xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>. Před deserializací pomocí <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> nastavte vlastnost na instanci vašeho vlastního <xref:System.Runtime.Serialization.SerializationBinder>. Pokud je typ <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> v přepsané metodě neočekávaný, vyvolejte výjimku pro zastavení deserializace.
  - Pokud omezíte deserializovatelné typy, možná budete chtít zakázat toto pravidlo a povolit pravidla [CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md) a [CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md). Rules [CA2301](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md) a [CA2302](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md) Help <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Binder> zajistí, že vlastnost je vždy nastavena před deserializací.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

[!INCLUDE[insecure-deserializers-common-safe-to-suppress](includes/insecure-deserializers-common-safe-to-suppress-md.md)]

## <a name="pseudo-code-examples"></a>Příklady kódu pseudo

### <a name="violation"></a>Selhání

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

[CA2301: Nevolejte BinaryFormatter. deserializovat bez prvotního nastavení BinaryFormatter. Binder](ca2301-do-not-call-binaryformatter-deserialize-without-first-setting-binaryformatter-binder.md)

[CA2302: Před voláním metody BinaryFormatter. deserializace se ujistěte, že je nastaven BinaryFormatter. Binder.](ca2302-ensure-binaryformatter-binder-is-set-before-calling-binaryformatter-deserialize.md)