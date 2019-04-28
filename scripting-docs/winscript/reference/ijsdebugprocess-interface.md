---
title: Ijsdebugprocess – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: a7ad5525-55b7-4c68-a4f7-c508f7877712
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 411679a03daf27046fdcede7ff48e76212bbd2fd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62557943"
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