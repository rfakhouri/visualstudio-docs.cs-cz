---
title: IDebugSourceServerModule | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- IDebugSourceServerModule interface
ms.assetid: 38213060-451d-46e6-8b4a-efc123e01a2c
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5bb686ff492ca836d35b21d54298876314ecb8d5
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66321913"
---
# <a name="idebugsourceservermodule"></a>IDebugSourceServerModule
Představuje informace o zdrojovém serveru, který je obsažen v souboru PDB.

## <a name="syntax"></a>Syntaxe

```
IDebugSourceServerModule : IUnknown
```

## <a name="notes-for-implementers"></a>Poznámky pro implementátory
 Toto rozhraní je implementováno ladicím modulem a spotřebovány ladicím programem uživatelského rozhraní.

## <a name="methods"></a>Metody
 V následující tabulce jsou uvedeny metody objektu `IDebugSourceServerModule`.

|Metoda|Popis|
|------------|-----------------|
|[GetSourceServerData](../../../extensibility/debugger/reference/idebugsourceservermodule-getsourceserverdata.md)|Načte pole informace o zdrojovém serveru.|

## <a name="requirements"></a>Požadavky
 Záhlaví: Msdbg.h

 Obor názvů: Microsoft.VisualStudio.Debugger.Interop

 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll