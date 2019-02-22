---
title: IDebugArrayObject::GetElement | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugArrayObject::GetElement
helpviewer_keywords:
- IDebugArrayObject::GetElement method
ms.assetid: 08b44341-7bf1-4a8c-8b79-98ae5785b195
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 735b92bb649344c055f7a645b961925e3cbd4d6e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56684621"
---
# <a name="idebugarrayobjectgetelement"></a>IDebugArrayObject::GetElement
Získá prvek pole.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT GetElement( 
   DWORD          dwIndex,
   IDebugObject** ppElement
);
```

```csharp
int GetElement(
   [In] uint dwIndex,
   out IDebugObject ppElement
);
```

#### <a name="parameters"></a>Parametry
 `dwIndex`

 [in] Index prvku.

 `ppElement`

 [out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) rozhraní, které představuje element.

## <a name="return-value"></a>Návratová hodnota
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Tato metoda považuje všechny prvky objektu pole jednorozměrné pole, i když objekt pole je vícerozměrné. Mějme například pole `myarray[3][2][6]` a `dwIndex` parametr 20, vrátí tato metoda element z `myarray[1][1][2]`a `dwIndex` parametr 21 vracel element z `myarray[1][1][3]`. Použití [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md) metodou ke zjištění celkový počet prvků v poli.

## <a name="see-also"></a>Viz také
- [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)