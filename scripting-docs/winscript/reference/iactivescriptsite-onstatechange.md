---
title: IActiveScriptSite::OnStateChange | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.OnStateChange
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_OnStateChange
ms.assetid: 3e9c5cbe-ca8e-426a-84fd-04e9c2daac7e
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ad5719a93aec2940f1180a6ff45a028b937b0dfe
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992537"
---
# <a name="iactivescriptsiteonstatechange"></a>IActiveScriptSite::OnStateChange
Informuje o hostiteli, že skriptovací stroj změnil stavy.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT OnStateChange(  
    SCRIPTSTATE ssScriptState  // new state of engine  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `ssScriptState`  
 [in] Hodnota, která označuje nové stavu skriptu. Zobrazit [IActiveScript::GetScriptState](../../winscript/reference/iactivescript-getscriptstate.md) metoda popis stavu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` v případě úspěšného ověření.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)