---
title: IDebugEngine3::SetJustMyCodeState | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugEngine3::SetJustMyCodeState
helpviewer_keywords:
- IDebugEngine3::SetJustMyCodeState
ms.assetid: 8ec17fbf-df93-424a-b2ed-fd1e5ee51256
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: f53b0eb95a2a91f34917b05cadffda2f4aa9a8b1
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66322317"
---
# <a name="idebugengine3setjustmycodestate"></a>IDebugEngine3::SetJustMyCodeState
Tato metoda informuje o informace o stavu JustMyCode ladicího stroje.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetJustMyCodeState(
   BOOL           fUpdate,
   DWORD          dwModules,
   JMC_CODE_SPEC* rgJMCSpec
);
```

```csharp
int SetJustMyCodeState(
   int             fUpdate,
   uint            dwModules,
   JMC_CODE_SPEC[] rgJMCSpec
);
```

## <a name="parameters"></a>Parametry
`fUpdate`\
[in] Nenulový (`TRUE`) aktualizovat informace o aktuálním nula (`FALSE`) Chcete-li obnovit všechny informace (ignorování nic předtím nastavili).

`dwModules`\
[in] Počet struktur informace `rgJMCSpec.`

`rgJMCSpec`\
[in] Pole [JMC_CODE_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md) strukturách.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 JustMyCode je Princip ladění pouze kód, který patří uživateli a ignoruje všechny mezikódu, jako je například kód systému – i v případě, že zdrojový kód je k dispozici pro tento kód systému.

## <a name="see-also"></a>Viz také:
- [IDebugEngine3](../../../extensibility/debugger/reference/idebugengine3.md)
- [JMC_CODE_SPEC](../../../extensibility/debugger/reference/jmc-code-spec.md)