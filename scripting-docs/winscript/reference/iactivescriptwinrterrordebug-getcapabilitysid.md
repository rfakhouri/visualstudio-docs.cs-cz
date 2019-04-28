---
title: IActiveScriptWinRTErrorDebug::GetCapabilitySid | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptWinRTErrorDebug::GetCapabilitySid
ms.assetid: 469463d2-5e73-4c53-9ffd-d0ca7460aa5c
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6847dba8f2bd3051df4ab6f0940e7b405698e45b
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63432963"
---
# <a name="iactivescriptwinrterrordebuggetcapabilitysid"></a>IActiveScriptWinRTErrorDebug::GetCapabilitySid
Vrátí funkci SID pro prostředí Windows Runtime chybu, pokud je k dispozici.  
  
> [!IMPORTANT]
> [Iactivescriptwinrterrordebug – rozhraní](../../winscript/reference/iactivescriptwinrterrordebug-interface.md) je implementováno komponentou Pdm verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetCapabilitySid([out] BSTR * capabilitySid);  
```  
  
#### <a name="parameters"></a>Parametry  
 `capabilitySid`  
 Možnost SID chyby.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptWinRTErrorDebug – rozhraní](../../winscript/reference/iactivescriptwinrterrordebug-interface.md)