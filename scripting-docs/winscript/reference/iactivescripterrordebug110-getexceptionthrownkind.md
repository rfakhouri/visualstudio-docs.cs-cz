---
title: IActiveScriptErrorDebug110::GetExceptionThrownKind | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptErrorDebug110::QueryIsFirstChance
ms.assetid: ecc16e54-93e4-4322-ae13-afa7cd860032
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a58add60560f22681f18225d844814e3547b671f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63436074"
---
# <a name="iactivescripterrordebug110getexceptionthrownkind"></a>IActiveScriptErrorDebug110::GetExceptionThrownKind
Vrací hodnotu, která označuje druh vyvolané výjimky.  
  
> [!IMPORTANT]
> [Iactivescripterrordebug110 – rozhraní](../../winscript/reference/iactivescripterrordebug110-interface.md) je implementováno komponentou PDM verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetExceptionThrownKind(  
   SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND*  pExceptionKind  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pExceptionKind`  
 [out] Typ výjimky, která je vyvolána (například první příležitosti nebo neošetřená výjimka), reprezentovaný [výčet SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND](../../winscript/reference/script-error-debug-exception-thrown-kind-enumeration.md) hodnota výčtu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Value|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptErrorDebug110 – rozhraní](../../winscript/reference/iactivescripterrordebug110-interface.md)