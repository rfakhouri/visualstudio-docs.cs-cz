---
title: IEEVisualizerDataProvider::SetObjectForVisualizer | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer
helpviewer_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer method
ms.assetid: 40dad2be-57ff-4f74-9d82-c48039c125c4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: cd7bd4bfd113da8cfd311d1022967d8c99f915b5
ms.sourcegitcommit: 6196d0b7fdcb08ba6d28a8151ad36b8d1139f2cc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2019
ms.locfileid: "65223934"
---
# <a name="ieevisualizerdataprovidersetobjectforvisualizer"></a>IEEVisualizerDataProvider::SetObjectForVisualizer
Tato metoda se změní objekt, který představuje vizualizér.

## <a name="syntax"></a>Syntaxe

```cpp
HRESULT SetObjectForVisualizer(
   IDebugObject*  pNewObject,
   BSTR*          error,
   IDebugObject** pException
);
```

```csharp
int SetObjectForVisualizer(
   IDebugObject     pNewObject,
   out string       error,
   out IDebugObject pException
);
```

## <a name="parameters"></a>Parametry
 `pNewObject`\

 [in] Objekt, který chcete nastavit.

 `error`\

 [out] Pokud došlo k chybě nastavení objektu, tento řetězec obsahuje chybovou zprávu.

 `pException`\

 [out] Pokud došlo k chybě, tento objekt obsahuje informace o výjimce.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Záleží implementátora k určení, jak se vrátí informace o chybě. Je však možné, že některé volající může použít jenom vzhled zobrazíte, pokud byl vrácen objekt výjimky vědět, že došlo k chybě, takže tato metoda by měla vždycky vrátí objekt výjimky, když došlo k chybě. Chybový řetězec by měl být rovněž dodán v případě, že volající vyžaduje, aby využívání.

## <a name="see-also"></a>Viz také:
- [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)