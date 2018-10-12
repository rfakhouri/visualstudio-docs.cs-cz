---
title: IDebugMemoryBytes2::WriteAt | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugMemoryBytes2::WriteAt
helpviewer_keywords:
- IDebugMemoryBytes2::WriteAt method
- WriteAt method
ms.assetid: 61cc3704-47fa-4d9b-aa62-bb4585ac8fb1
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 38196bfafc7d0b9e0cb7dcf4a585c43a382ca9df
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49278223"
---
# <a name="idebugmemorybytes2writeat"></a>IDebugMemoryBytes2::WriteAt
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Zapíše zadaný počet bajtů paměti, spouští se na zadané adrese.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [in] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objekt, který určuje, kde začít psát bajtů.  
  
 `dwCount`  
 [in] Počet bajtů k zápisu.  
  
 `rgbMemory`  
 [in] Bajty k zápisu. Toto pole je považován za nejméně `dwCount` bajty.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` Pokud ne všechny bajty může být napsaná nebo vrátí kód chyby (obvykle `E_FAIL`).  
  
## <a name="remarks"></a>Poznámky  
 Pokud počáteční adresa není v rámci okna paměť představovaného tímto rozhraním [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md) objektů, dojde k žádné psaní a chybovým kódem `E_FAIL` je vrácena – i v případě, že do paměťový prostor se překrývá velikost pro zápis.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)

