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
ms.openlocfilehash: a55328c4148aa911d86b8f2daf05ba84a50ff444
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62867973"
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

#### <a name="parameters"></a>Parametry
 `pNewObject`

 [in] Objekt, který chcete nastavit.

 `error`

 [out] Pokud došlo k chybě nastavení objektu, tento řetězec obsahuje chybovou zprávu.

 `pException`

 [out] Pokud došlo k chybě, tento objekt obsahuje informace o výjimce.

## <a name="return-value"></a>Návratová hodnota
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.

## <a name="remarks"></a>Poznámky
 Záleží implementátora k určení, jak se vrátí informace o chybě. Je však možné, že některé volající může použít jenom vzhled zobrazíte, pokud byl vrácen objekt výjimky vědět, že došlo k chybě, takže tato metoda by měla vždycky vrátí objekt výjimky, když došlo k chybě. Chybový řetězec by měl být rovněž dodán v případě, že volající vyžaduje, aby využívání.

## <a name="see-also"></a>Viz také
- [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)
- [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)