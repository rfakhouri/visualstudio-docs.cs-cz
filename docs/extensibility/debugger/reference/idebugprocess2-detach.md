---
title: IDebugProcess2::Detach | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::Detach
helpviewer_keywords:
- IDebugProcess2::Detach
ms.assetid: ee2b9084-2db1-4e49-a1d9-387284b7c3f8
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ba166f67ad47da1e219ff767517e9b0664fe12aa
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56713435"
---
# <a name="idebugprocess2detach"></a>IDebugProcess2::Detach
Ladicí program z tohoto procesu se odpojí odpojíte všechny programy v procesu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Detach( 
   void 
);
```

```csharp
int Detach();
```

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Všechny programy a procesu pokračovat v běhu, ale už nejsou součástí relace ladění. Po odpojení operace dokončena, žádné další ladění, bude odeslána události pro tento proces (a jeho programy).

## <a name="see-also"></a>Viz také
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)