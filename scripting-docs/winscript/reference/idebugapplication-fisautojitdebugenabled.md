---
title: IDebugApplication::FIsAutoJitDebugEnabled | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDebugApplication.FIsAutoJitDebugEnabled
apilocation:
- pdm.dll
helpviewer_keywords:
- IDebugApplication::FIsAutoJitDebugEnabled
ms.assetid: 0551dd3b-e6eb-442a-8201-418f96fe62df
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f594c5ce48ebd31a265ed438db176c5707d9b079
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58152074"
---
# <a name="idebugapplicationfisautojitdebugenabled"></a>IDebugApplication::FIsAutoJitDebugEnabled
Určuje, zda ladicí program just-in-time (JIT) je zaregistrován vlečný hostitelům automatického ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
BOOL FIsAutoJitDebugEnabled();  
```  
  
#### <a name="parameters"></a>Parametry  
 Tato metoda nemá žádné parametry.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud metoda uspěje a JIT ladící program registrován na automatické ladění vlečný hostitele, vrátí metoda `TRUE`. V opačném případě vrátí `FALSE`.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda určuje, zda JIT ladící program registrován vlečný hostitelům automatického ladění.  
  
## <a name="see-also"></a>Viz také  
 [IDebugApplication – rozhraní](../../winscript/reference/idebugapplication-interface.md)