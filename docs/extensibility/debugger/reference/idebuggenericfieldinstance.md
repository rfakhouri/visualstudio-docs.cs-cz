---
title: IDebugGenericFieldInstance | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugGenericFieldInstance interface
ms.assetid: f68b4761-be8b-4801-9d4b-cde90e01d95e
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 189d670892b50958edff3b256874441aebd72be5
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66330505"
---
# <a name="idebuggenericfieldinstance"></a>IDebugGenericFieldInstance
Představuje instanci pole pro obecný typ spravovaného kódu.

## <a name="syntax"></a>Syntaxe

```
IDebugGenericFieldInstance : IUnknown
```

## <a name="methods"></a>Metody
 Toto rozhraní implementuje následujících metod:

|Metoda|Popis|
|------------|-----------------|
|[GetTypeArguments](../../../extensibility/debugger/reference/idebuggenericfieldinstance-gettypearguments.md)|Načte argumenty parametrů typu pro tuto instanci.|
|[TypeArgumentCount](../../../extensibility/debugger/reference/idebuggenericfieldinstance-typeargumentcount.md)|Vrátí číslo typu parametru argumenty pro tuto instanci.|

## <a name="requirements"></a>Požadavky
 Záhlaví: Sh.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll