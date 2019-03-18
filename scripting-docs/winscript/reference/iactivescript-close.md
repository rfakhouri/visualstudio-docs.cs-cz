---
title: IActiveScript::Close | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.Close
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_Close
ms.assetid: cc7dd63b-1d7e-410a-857b-09ea3aade275
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 53b71471ada55751de301391fdcc70387c1bb6c2
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58157046"
---
# <a name="iactivescriptclose"></a>IActiveScript::Close
Způsobí, že skriptovací stroj opustit všechny aktuálně načtené skriptu, přijít o jejím stavu a uvolnit všechny ukazatele rozhraní, které je jiné objekty, tedy zadáte uzavřeného stavu. Jímky událostí, text ihned prováděnou skriptu a vyvoláním makra, které jsou již probíhá jsou dokončeny před změny stavu (použijte [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md) zrušit spuštěné vlákno skriptu). Tato metoda musí být volána vytváření hostitele před rozhraní je všeobecně dostupné, aby se zabránilo problémům cyklický odkaz.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT Close(void);  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Hodnota|Význam|  
|-----------|-------------|  
|`S_OK`|Úspěch.|  
|`E_UNEXPECTED`|Volání nebylo očekáváno (například skriptovací stroj už je v uzavřeném stavu).|  
|`OLESCRIPT_S_PENDING`|Metoda byla úspěšně ve frontě, ale ještě nebyl změněn stav. Když změny stavu webu je volat zpět na [IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md) metody.|  
|`S_FALSE`|Metoda byla úspěšná, ale tento skript byl již uzavřen.|  
  
## <a name="see-also"></a>Viz také  
 [IActiveScript](../../winscript/reference/iactivescript.md)