---
title: Struktura AsyncTaskMethodBuilder – vnitřní členy | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines, AsyncTaskMethodBuilder structure [.NET Framework]
- AsyncTaskMethodBuilder structure [.NET Framework debug engines]
ms.assetid: f32f5857-7ef8-45fd-8b5a-7f644eb98b11
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8e19e44d8b73618f1093e90e3364df7dc43c0af3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62890963"
---
# <a name="asynctaskmethodbuilder-structure---internal-members"></a>Struktura AsyncTaskMethodBuilder – vnitřní členy
Toto téma popisuje interní členy <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder> třídy. Obecné informace o této třídy, najdete v článku <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder> téma referenčních informací.

 **Namespace:** <xref:System.Runtime.CompilerServices?displayProperty=fullName>

 **Sestavení:** mscorlib (v knihovně mscorlib.dll)

 Protože tyto vnitřní členy nemůže získat přístup z rozhraní .NET Framework, je k dispozici v Common Intermediate Language (CIL) následující syntaxi.

## <a name="syntax"></a>Syntaxe

```csharp
.class public sequential ansi sealed beforefieldinit System.Runtime.CompilerServices.AsyncTaskMethodBuilder
       extends System.ValueType
       implements System.Runtime.CompilerServices.IAsyncMethodBuilder
```

## <a name="internal-members"></a>Vnitřní členy

|Název|Popis|
|----------|-----------------|
|[Vlastnost ObjectIdForDebugger](../../extensibility/debugger/asynctaskmethodbuilder-objectidfordebugger-property.md)|Získá objekt, který slouží k jednoznačné identifikaci tohoto Tvůrce ladicímu programu.|
|[m_builder pole](../../extensibility/debugger/asynctaskmethodbuilder-m-builder-field.md)|Reprezentuje obecný tvůrce objektu, ke kterému tato instance neobecných delegátů.|

## <a name="see-also"></a>Viz také:
- <xref:System.Runtime.CompilerServices.AsyncTaskMethodBuilder>
- [Interní informace o paralelním rozšíření pro rozhraní .NET Framework](../../extensibility/debugger/parallel-extension-internals-for-the-dotnet-framework.md)