---
title: IDebugPortSupplier3::CanPersistPorts | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugPortSupplier3::CanPersistPorts
helpviewer_keywords:
- IDebugPortSupplier3::CanPersistPorts
ms.assetid: 4127760c-e602-4e86-9232-457e382a52c7
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 11bc6e21e8b70a5bd95c001f4173a7da3f3fe4be
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66340061"
---
# <a name="idebugportsupplier3canpersistports"></a>IDebugPortSupplier3::CanPersistPorts
Tato metoda určuje, zda dodavatele portu můžete zachovaly porty (je zápis na disk) mezi vyvolání ladicího programu.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT CanPersistPorts();
```

```csharp
int CanPersistPorts();
```

## <a name="parameters"></a>Parametry
 Žádné

## <a name="return-value"></a>Návratová hodnota
 `S_OK` Pokud porty můžete nastavit jako trvalý, nebo `S_FALSE` k označení, že porty nelze nastavit jako trvalý.

## <a name="remarks"></a>Poznámky
 Pokud dodavatele portu můžete zachovat porty, měl by to dělat, když je zničen a při vytváření její instance znovu je načtěte.

## <a name="see-also"></a>Viz také:
- [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)