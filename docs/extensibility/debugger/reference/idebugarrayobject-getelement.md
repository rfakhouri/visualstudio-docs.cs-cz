---
title: IDebugArrayObject::GetElement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugArrayObject::GetElement
helpviewer_keywords:
- IDebugArrayObject::GetElement method
ms.assetid: 08b44341-7bf1-4a8c-8b79-98ae5785b195
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e2e10eced58835044220da0650712dacb131ada3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugarrayobjectgetelement"></a>IDebugArrayObject::GetElement
Získá element pole.  
  
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
 [v] Index elementu.  
  
 `ppElement`  
 [out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) rozhraní, které představuje elementu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda zobrazí všechny elementy pole objektu jako jednorozměrné pole, i když je objekt array multidimenzionální. Například zadané pole `myarray[3][2][6]` a `dwIndex` parametr 20, vrátí tato metoda element ze `myarray[1][1][2]`a `dwIndex` parametr 21 by vrátit element ze `myarray[1][1][3]`. Použití [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md) metoda můžete určit celkový počet prvků v poli.  
  
## <a name="see-also"></a>Viz také  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)