---
title: IDebugProcess2::Terminate | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugProcess2::Terminate
helpviewer_keywords:
- IDebugProcess2::Terminate
ms.assetid: 5e6bf373-0fe9-4321-b04a-473a65f664d9
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 8a4b44cfc9655c619089d341156328b77594dad9
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66314154"
---
# <a name="idebugprocess2terminate"></a>IDebugProcess2::Terminate
Ukončí proces.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT Terminate( 
   void 
);
```

```csharp
int Terminate();
```

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Když se proces ukončí, jsou ukončeny všechny programy v rámci tohoto procesu; žádný je, že bude možné spustit jakýkoli další kód.

## <a name="see-also"></a>Viz také:
- [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)