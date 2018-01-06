---
title: IDebugMemoryBytes2::WriteAt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMemoryBytes2::WriteAt
helpviewer_keywords:
- IDebugMemoryBytes2::WriteAt method
- WriteAt method
ms.assetid: 61cc3704-47fa-4d9b-aa62-bb4585ac8fb1
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 8f10efd1e9a06ca8425d972f43736b49e6ef4a83
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmemorybytes2writeat"></a>IDebugMemoryBytes2::WriteAt
Zapíše zadaný počet bajtů paměti, počínaje zadaná adresa.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT WriteAt(   
   IDebugMemoryContext2* pStartContext,  
   DWORD                 dwCount,  
   BYTE*                 rgbMemory  
);  
```  
  
```csharp  
int WriteAt(  
   IDebugMemoryContext2 pStartContext,  
   uint                 dwCount,  
   byte[]               rgbMemory  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pStartContext`  
 [v] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objekt, který určuje, kde Zahájit zápis bajtů.  
  
 `dwCount`  
 [v] Počet bajtů k zápisu.  
  
 `rgbMemory`  
 [v] Bajty k zápisu. Toto pole se předpokládá, že nejméně `dwCount` velikost bajtů.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` Pokud nejsou všechny bajty může být zapsána nebo vrátí kód chyby (obvykle `E_FAIL`).  
  
## <a name="remarks"></a>Poznámky  
 Pokud počáteční adresa není v rámci okna paměti reprezentována to [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md) objektu, dojde k žádné zápis a chybový kód `E_FAIL` je vrácen – i v případě, že se překrývá velikost k zápisu do prostoru v paměti.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)