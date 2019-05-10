---
title: 'CA2310: Nepoužívejte nezabezpečené deserializátor NetDataContractSerializer'
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
- CA2310
- DoNotUseInsecureDeserializerNetDataContractSerializer
ms.openlocfilehash: e4af6bbfbd7e14b99f39ffa0adb5d1117c200d9a
ms.sourcegitcommit: db30651dc0ce4d0b274479b23a6bd102a5559098
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/06/2019
ms.locfileid: "65135557"
---
# <a name="ca2310-do-not-use-insecure-deserializer-netdatacontractserializer"></a>CA2310: Nepoužívejte nezabezpečené deserializátor NetDataContractSerializer

|||
|-|-|
|TypeName|DoNotUseInsecureDeserializerNetDataContractSerializer|
|CheckId|CA2310|
|Kategorie|Microsoft.Security|
|Narušující změna|Pevné|

## <a name="cause"></a>Příčina

A <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType> metody deserializace byla volána nebo odkazovat.

## <a name="rule-description"></a>Popis pravidla

[!INCLUDE[insecure-deserializers-description](includes/insecure-deserializers-description-md.md)]

Toto pravidlo vyhledá <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=nameWithType> deserializace volání metody nebo odkazy. Pokud chcete k deserializaci pouze tehdy, když <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder> je nastavena na omezení typů, vypněte toto pravidlo a povolit pravidla [CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md) a [CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md) místo.

## <a name="how-to-fix-violations"></a>Jak vyřešit porušení

- Pokud je to možné, použijte zabezpečené serializátor, a **Nepovolit útočníkovi zadat libovolný typ k deserializaci**. Některé bezpečnější serializátory patří:
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -Nikdy nepoužívejte <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>. Pokud je nutné použít typ překladače, omezení deserializovaný typy k očekávaným seznamem.
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - Newtonsoft Json.NET - TypeNameHandling.None použití. Pokud musíte použít jinou hodnotu pro TypeNameHandling, omezte na očekávaným seznamem s vlastní ISerializationBinder deserializovaný typy.
  - Protocol Buffers
- Ujistěte se, manipulací serializovaná data. Po serializaci podepište kryptograficky serializovaná data. Před deserializace ověřte kryptografický podpis. Chraňte kryptografické klíče z je zveřejněn a návrh pro rotace klíčů.
- Zakázání deserializovaný typů. Implementovat vlastní <xref:System.Runtime.Serialization.SerializationBinder?displayProperty=nameWithType>. Před deserializace s <xref:System.Runtime.Serialization.NetDataContractSerializer>, nastavte <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder> vlastnost instance vašeho vlastního <xref:System.Runtime.Serialization.SerializationBinder>. V přepsané <xref:System.Runtime.Serialization.SerializationBinder.BindToType%2A> metodu, pokud je očekáván typ vyvolat výjimku.
- Pokud omezíte deserializovaný typy, můžete toto pravidlo zakázání a povolení pravidla [CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md) a [CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md). Pravidla [CA2311](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md) a [CA2312](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md) zobrazíte nápovědu, jak zajistit, aby <xref:System.Runtime.Serialization.NetDataContractSerializer.Binder> před deserializace je vždy nastavena vlastnost.

## <a name="when-to-suppress-warnings"></a>Kdy potlačit upozornění

[!INCLUDE[insecure-deserializers-common-safe-to-suppress](includes/insecure-deserializers-common-safe-to-suppress-md.md)]

## <a name="pseudo-code-examples"></a>Příklady pseudo kódu

### <a name="violation"></a>Porušení

```csharp
using System.IO;
using System.Runtime.Serialization;

public class ExampleClass
{
    public object MyDeserialize(byte[] bytes)
    {
        NetDataContractSerializer serializer = new NetDataContractSerializer();
        return serializer.Deserialize(new MemoryStream(bytes));
    }
}
```

```vb
Imports System.IO
Imports System.Runtime.Serialization

Public Class ExampleClass
    Public Function MyDeserialize(bytes As Byte()) As Object
        Dim serializer As NetDataContractSerializer = New NetDataContractSerializer()
        Return serializer.Deserialize(New MemoryStream(bytes))
    End Function
End Class
```

## <a name="related-rules"></a>Související pravidla

[CA2311: Nelze deserializovat bez první nastavení NetDataContractSerializer.Binder](ca2311-do-not-deserialize-without-first-setting-netdatacontractserializer-binder.md)

[CA2312: Ujistěte se, že NetDataContractSerializer.Binder nastavený před deserializaci](ca2312-ensure-netdatacontractserializer-binder-is-set-before-deserializing.md)
