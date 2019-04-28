---
title: Struktura asyncvoidmethodbuilder Structure – vnitřní členy | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, AsyncVoidMethodBuilder structure [.NET Framework]
- AsyncVoidMethodBuilder structure [.NET Framework debug engines]
ms.assetid: fe2970ab-d4c5-4355-a8e4-772ee0a57178
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 0a4c51d76d38680945eaccbd3ace256813668c51
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62890867"
---
# <a name="asyncvoidmethodbuilder-structure---internal-members"></a>Struktura asyncvoidmethodbuilder Structure – vnitřní členy
Toto téma popisuje interní členy <xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder> třídy. Obecné informace o této třídy, najdete v článku <xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder> téma referenčních informací.

 **Namespace:** <xref:System.Runtime.CompilerServices?displayProperty=fullName>

 **Sestavení:** mscorlib (v knihovně mscorlib.dll)

 Protože tyto vnitřní členy nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.

## <a name="syntax"></a>Syntaxe

```csharp
.class public sequential ansi sealed beforefieldinit System.Runtime.CompilerServices.AsyncVoidMethodBuilder
       extends System.ValueType
       implements System.Runtime.CompilerServices.IAsyncMethodBuilder
```

## <a name="internal-members"></a>Vnitřní členy

|Název|Popis|
|----------|-----------------|
|[Vlastnost ObjectIdForDebugger](../../extensibility/debugger/asyncvoidmethodbuilder-objectidfordebugger-property.md)|Získá objekt, který slouží k jednoznačné identifikaci tohoto Tvůrce ladicímu programu.|
|[m_objectIdForDebugger pole](../../extensibility/debugger/asyncvoidmethodbuilder-m-objectidfordebugger-field.md)|Představuje laxně inicializovaný objekt použitý objektem ladicí program k jednoznačné identifikaci tohoto Tvůrce.|

## <a name="see-also"></a>Viz také:
- <xref:System.Runtime.CompilerServices.AsyncVoidMethodBuilder>
- [Interní informace o paralelním rozšíření pro rozhraní .NET Framework](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)