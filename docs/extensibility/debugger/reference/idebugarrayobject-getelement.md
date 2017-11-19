---
title: IDebugArrayObject::GetElement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugArrayObject::GetElement
helpviewer_keywords: IDebugArrayObject::GetElement method
ms.assetid: 08b44341-7bf1-4a8c-8b79-98ae5785b195
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 451c758ef067bfd162e5451a629983ef2130a1d9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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