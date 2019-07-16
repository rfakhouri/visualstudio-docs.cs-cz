---
title: IDebugPointerObject::SetBytes | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugPointerObject::SetBytes
helpviewer_keywords:
- IDebugPointerObject::SetBytes method
ms.assetid: 8c578b38-38d7-46f3-bb2e-8a730fccd334
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 9d467b037f4e2affea53a142304507f876630999
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68202960"
---
# <a name="idebugpointerobjectsetbytes"></a>IDebugPointerObject::SetBytes
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nastaví hodnotu, na který je odkazováno v řadě po sobě jdoucích bajtů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
