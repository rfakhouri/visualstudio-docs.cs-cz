---
title: Ijsdebugprocess – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: a7ad5525-55b7-4c68-a4f7-c508f7877712
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ecdec77a8bcb3c1fb8a1dc64c63b363b4f001fde
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54086655"
---
# <a name="ijsdebugprocess-interface"></a>IJsDebugProcess – rozhraní
Poskytuje rutiny pro kontrolu a řízení cílových procesů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
IJsDebugProcess : public IUnknown;  
```  
  
## <a name="members"></a>Členové  
  
### <a name="public-methods"></a>Veřejné metody  
  
|Název|Popis|  
|----------|-----------------|  
|[IJsDebugProcess::CreateBreakPoint – metoda](../../winscript/reference/ijsdebugprocess-createbreakpoint-method.md)|Nastaví zarážku na pozici zadaného dokumentu.|  
|[IJsDebugProcess::CreateStackWalker – metoda](../../winscript/reference/ijsdebugprocess-createstackwalker-method.md)|Metoda výroby pro zásobník.|  
|[IJsDebugProcess::PerformAsyncBreak – metoda](../../winscript/reference/ijsdebugprocess-performasyncbreak-method.md)|Vloží skriptovací stroj do režimu přerušení způsobí jeho přerušení v další instrukci skriptu.|  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace skriptovacích rozhraní systému Windows](../../winscript/reference/windows-script-interfaces-reference.md)