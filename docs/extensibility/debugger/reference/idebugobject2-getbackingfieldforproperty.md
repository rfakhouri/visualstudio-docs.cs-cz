---
title: IDebugObject2::GetBackingFieldForProperty | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugObject2::GetBackingFieldForProperty
helpviewer_keywords:
- IDebugObject2::GetBackingFieldForProperty method
ms.assetid: e72c6338-5573-4fad-8075-f3ade3435424
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 9aaf4111670ad67f6a01bde60bf5f35c3b793983
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66317344"
---
# <a name="idebugobject2getbackingfieldforproperty"></a>IDebugObject2::GetBackingFieldForProperty
Získá pole nebo proměnné (pokud existuje), který může být zálohování vlastnost reprezentovaný tímto objektem.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetBackingFieldForProperty(
   IDebugObject2** ppObject
);
```

```csharp
int GetBackingFieldForProperty(
   out IDebugObject2 ppObject
);
```

## <a name="parameters"></a>Parametry
`ppObject`\
[out] [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) objekt popisující pole zálohování.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md) objekt představuje vlastnost třídy spravovaného kódu, to znamená, že metoda get a/nebo nastavení přístupového objektu. Tyto vlastnosti se obecně vyžadují proměnná obsahuje hodnotu manipulovat vlastnost. Tato proměnná je označována jako pole zálohování. Pokud tam není žádné pole zálohování pro objekt, ujistěte se, vrátí hodnotu null: některé volající nemusí věnovat pozornost návratovou hodnotu, ale místo toho bude vypadat zobrazíte, pokud byla vrácena hodnota null v `ppObject`.

## <a name="see-also"></a>Viz také:
- [IDebugObject2](../../../extensibility/debugger/reference/idebugobject2.md)