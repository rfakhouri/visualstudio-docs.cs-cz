---
title: IDebugPointerObject::SetBytes | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPointerObject::SetBytes
helpviewer_keywords:
- IDebugPointerObject::SetBytes method
ms.assetid: 8c578b38-38d7-46f3-bb2e-8a730fccd334
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 73067f74fb0b44d4a9dc06686d5defdd56210b4d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55017887"
---
# <a name="idebugpointerobjectsetbytes"></a>IDebugPointerObject::SetBytes
Nastaví hodnotu, na který je odkazováno v řadě po sobě jdoucích bajtů.  
  
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
 [in] Posun v bajtech od začátku objekt odkazoval.  
  
 `dwCount`  
 [in] Počet bajtů, které mají nastavit.  
  
 `pBytes`  
 [in] Pole bajtů představuje novou hodnotu. Tato hodnota bude uložena do objektu, spuštění na dané pozici.  
  
 `pdwBytes`  
 [out] Vrátí že počet bajtů ve skutečnosti nastavit.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda se používá, pokud ukazatel reprezentovaný tímto objektem [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md) odkazuje na primitivní typ nebo jednoduchý pole primitivní typy (to znamená, pole, které může být reprezentován jednoduché pořadí bajtů). To `IDebugPointerObject` objektu nemůže být nulový odkaz (musí odkazovat na adresu v paměti).  
  
## <a name="see-also"></a>Viz také  
 [Provedení metody GetBytes](../../../extensibility/debugger/reference/idebugpointerobject-getbytes.md)   
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)