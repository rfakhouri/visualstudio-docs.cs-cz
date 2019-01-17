---
title: Scriptgctype – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: f289cc7d-2a69-4720-bee0-ea27d054f308
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b25ffb530bf16fff0008bb73b55ecb0c523efe0d
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349098"
---
# <a name="scriptgctype-enumeration"></a>SCRIPTGCTYPE – výčet
Typ kolekce paměti k provedení. Používáno [IActiveScriptGarbageCollector::CollectGarbage](../../winscript/reference/iactivescriptgarbagecollector-collectgarbage.md) metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
typedef enum tagSCRIPTGCTYPE {    SCRIPTGCTYPE_NORMAL           = 0,    SCRIPTGCTYPE_EXHAUSTIVE       = 1,} SCRIPTGCTYPE;  
```  
  
## <a name="enumeration-values"></a>Hodnoty výčtu  
  
|||  
|-|-|  
|SCRIPTGCTYPE_NORMAL|Normální uvolňování paměti proveďte. Celočíselná hodnota je 0.|  
|SCRIPTGCTYPE_EXHAUSTIVE|Proveďte úplné uvolňování paměti. Celočíselná hodnota je 1.|  
  
## <a name="see-also"></a>Viz také  
 [Konstanty, výčty a kódy chyb aktivních skriptů](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)