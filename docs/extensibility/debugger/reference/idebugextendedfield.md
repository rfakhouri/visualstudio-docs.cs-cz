---
title: IDebugExtendedField | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugExtendedField interface
ms.assetid: b491499c-af57-47da-87d6-34b7398f6591
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3a9e8f8e8414b6066bb8a407449a4b588d948bc4
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66333221"
---
# <a name="idebugextendedfield"></a>IDebugExtendedField
Rozšiřuje typy polí, které jsou k dispozici pro podporu obecných typů spravovaného kódu.

## <a name="syntax"></a>Syntaxe

```
IDebugExtendedField : IDebugField
```

## <a name="methods"></a>Metody
 Kromě metod na [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) rozhraní, toto rozhraní implementuje následujících metod:

|Metoda|Popis|
|------------|-----------------|
|[GetExtendedKind](../../../extensibility/debugger/reference/idebugextendedfield-getextendedkind.md)|Získá typ zadané rozšířené pole.|
|[IsClosedType](../../../extensibility/debugger/reference/idebugextendedfield-isclosedtype.md)|Určuje, zda pole představuje uzavřený typ.|

## <a name="requirements"></a>Požadavky
 Záhlaví: Sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll