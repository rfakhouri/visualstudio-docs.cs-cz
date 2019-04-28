---
title: Ijsdebugdatatarget::writememory – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IJsDebugDataTarget.WriteMemory
apilocation:
- jscript9diag.dll
ms.assetid: 0d3c04c3-9ef8-4842-a145-3d29bca75062
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 622de16cc5f755c5d69059a0e0f28d881121861c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62558174"
---
# <a name="ijsdebugdatatargetwritememory-method"></a>IJsDebugDataTarget::WriteMemory – metoda
Čtení paměti cílového procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT WriteMemory(  
   UINT64 address,  
   const BYTE *pMemory,  
   DWORD size  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `address`  
 [in] Základní adresa, ze které probíhá zápis paměti v cílovém procesu.  
  
 `pMemory`  
 [in] Data, která mají být zapsána do adresního prostoru určeného procesu.  
  
 `size`  
 [in] Počet bajtů k zápisu do procesu.  
  
## <a name="return-value"></a>Návratová hodnota  
  
## <a name="remarks"></a>Poznámky  
 Předtím, než dojde k přenosu dat, systém ověří, že všechna data v základní adrese a paměti o zadané velikosti jsou přístupné pro zápis, a pokud není dostupný, funkce vyvolá chybu E_JsDEBUG_INVALID_MEMORY_ADDRESS.  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [IJsDebugDataTarget – rozhraní](../../winscript/reference/ijsdebugdatatarget-interface.md)