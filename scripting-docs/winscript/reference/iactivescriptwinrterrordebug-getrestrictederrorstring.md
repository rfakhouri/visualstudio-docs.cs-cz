---
title: IActiveScriptWinRTErrorDebug::GetRestrictedErrorString | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptWinRTErrorDebug::GetRestrictedErrorString
ms.assetid: d901e049-fb1b-4101-a04a-1395d657f1cf
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e739d12674d64d5e47915c9f9e4c525e68d8b061
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349839"
---
# <a name="iactivescriptwinrterrordebuggetrestrictederrorstring"></a>IActiveScriptWinRTErrorDebug::GetRestrictedErrorString
Vrátí modulu Windows Runtime s omezením pomocí specifikátoru řetězec chyby, pokud je k dispozici.  
  
> [!IMPORTANT]
>  [Iactivescriptwinrterrordebug – rozhraní](../../winscript/reference/iactivescriptwinrterrordebug-interface.md) je implementováno komponentou Pdm verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetRestrictedErrorString([out] BSTR * errorString);   
```  
  
#### <a name="parameters"></a>Parametry  
 `errorString`  
 [out] Řetězec, který chybě s omezeným přístupem.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptWinRTErrorDebug – rozhraní](../../winscript/reference/iactivescriptwinrterrordebug-interface.md)