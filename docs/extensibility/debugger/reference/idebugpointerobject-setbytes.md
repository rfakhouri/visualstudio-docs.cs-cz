---
title: IDebugPointerObject::SetBytes | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDebugPointerObject::SetBytes
helpviewer_keywords:
- IDebugPointerObject::SetBytes method
ms.assetid: 8c578b38-38d7-46f3-bb2e-8a730fccd334
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 9bab2459d2de40fdc3ea44fe7e5e92c138a5f006
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugpointerobjectsetbytes"></a>IDebugPointerObject::SetBytes
Nastaví hodnotu odkazoval z řady po sobě jdoucích bajtů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetBytes(   
   DWORD  dwStart,  
   DWORD  dwCount,  
   BYTE*  pBytes,  
   DWORD* pdwBytes  
);  
```  
  
```csharp  
int SetBytes(  
   uint     dwStart,   
   uint     dwCount,   
   byte[]   pBytes,   
   out uint pdwBytes  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwStart`  
 [v] Posun v bajtech, od začátku objekt ukazuje.  
  
 `dwCount`  
 [v] Počet bajtů k nastavení.  
  
 `pBytes`  
 [v] Pole bajtů představující novou hodnotu. Tato hodnota je uložena do objektu, počínaje daným posunem.  
  
 `pdwBytes`  
 [out] Vrátí že počet bajtů ve skutečnosti nastavit.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda se používá, pokud je ukazatel reprezentovaná to [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md) odkazuje na primitivní typ nebo jednoduchý pole jednoduchých typů (tj. pole, které může být reprezentovaný jednoduché pořadí bajtů). To `IDebugPointerObject` objekt nemůže být nulovým odkazem. (musí odkazovat na adresu v paměti).  
  
## <a name="see-also"></a>Viz také  
 [GetBytes](../../../extensibility/debugger/reference/idebugpointerobject-getbytes.md)   
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)