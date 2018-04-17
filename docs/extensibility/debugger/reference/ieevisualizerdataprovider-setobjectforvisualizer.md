---
title: IEEVisualizerDataProvider::SetObjectForVisualizer | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer
helpviewer_keywords:
- IEEVisualizerDataProvider::SetObjectForVisualizer method
ms.assetid: 40dad2be-57ff-4f74-9d82-c48039c125c4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0d1a6272f8a04316c8695f301d5c45512b05f2d3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ieevisualizerdataprovidersetobjectforvisualizer"></a>IEEVisualizerDataProvider::SetObjectForVisualizer
Tato metoda mění objekt, který reprezentuje vizualizér.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetObjectForVisualizer(  
   IDebugObject*  pNewObject,  
   BSTR*          error,  
   IDebugObject** pException  
);  
```  
  
```csharp  
int SetObjectForVisualizer(  
   IDebugObject     pNewObject,  
   out string       error,  
   out IDebugObject pException  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pNewObject`  
 [v] Objekt nastavení.  
  
 `error`  
 [out] Pokud došlo k chybě nastavení objektu, tento řetězec obsahuje chybovou zprávu.  
  
 `pException`  
 [out] Pokud došlo k chybě, tento objekt obsahuje informace o výjimce.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Je implementátor k určení, jak se vrátí informace o chybě. Je však možné, že některé volající může použít jenom vzhled chcete zobrazit, pokud potřebujete vědět, že se vrátí objekt výjimky došlo k chybě, takže tato metoda by měla vždycky vrátí objekt výjimky, když došlo k chybě. Řetězec chyby by měl být uveden také v případě, že volající chce, aby jeho používání.  
  
## <a name="see-also"></a>Viz také  
 [IEEVisualizerDataProvider](../../../extensibility/debugger/reference/ieevisualizerdataprovider.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)