---
author: dotpaul
ms.author: paulming
ms.date: 05/01/2019
ms.topic: include
ms.openlocfilehash: bc423f10cfbae0b7a0cdaedb72f6891a0e12d228
ms.sourcegitcommit: 748d9cd7328a30f8c80ce42198a94a4b5e869f26
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "68147114"
---
- Pokud je to možné, použijte zabezpečené serializátor, a **Nepovolit útočníkovi zadat libovolný typ k deserializaci**. Některé bezpečnější serializátory patří:
  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -Nikdy nepoužívejte <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>. Pokud je nutné použít typ překladače, omezení deserializovaný typy k očekávaným seznamem.
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - Newtonsoft Json.NET - TypeNameHandling.None použití. Pokud musíte použít jinou hodnotu pro TypeNameHandling, omezte na očekávaným seznamem s vlastní ISerializationBinder deserializovaný typy.
  - Protocol Buffers
- Ujistěte se, manipulací serializovaná data. Po serializaci podepište kryptograficky serializovaná data. Před deserializace ověřte kryptografický podpis. Chraňte kryptografické klíče z je zveřejněn a návrh pro rotace klíčů.