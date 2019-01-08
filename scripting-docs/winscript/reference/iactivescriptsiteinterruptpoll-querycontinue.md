---
title: IActiveScriptSiteInterruptPoll::QueryContinue | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteInterruptPoll.QueryContinue
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteInterruptPoll::QueryContinue
ms.assetid: 41ac3807-f8b4-4a0e-bcc6-556bc89f3904
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9b43211dca57a404d5625cfc2d7ede67a70a0a40
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54087981"
---
# <a name="iactivescriptsiteinterruptpollquerycontinue"></a>IActiveScriptSiteInterruptPoll::QueryContinue
Umožňuje hostiteli k určení, zda by měla ukončit skriptu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT QueryContinue();  
```  
  
#### <a name="parameters"></a>Parametry  
 Tato metoda nemá žádné parametry.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Volání bylo úspěšné a hostitele povoluje skript, který chcete pokračovat v běhu.|  
|`S_FALSE`|Že bylo volání úspěšné a hostitele požadavků, které skript ukončit.|  
  
## <a name="remarks"></a>Poznámky  
 Hostované skriptu by měla ukončit, pokud návratová hodnota `QueryContinue` je metoda `S_OK`. Vrácená hodnota `S_FALSE` označuje, že hostitel výslovně požaduje, že skript ukončit.  
  
 Použít s více vlákny hostitele `IActiveScript::InterruptScriptThread` metoda ukončení skriptu.  
  
## <a name="see-also"></a>Viz také  
 [Iactivescriptsiteinterruptpoll – rozhraní](../../winscript/reference/iactivescriptsiteinterruptpoll-interface.md)   
 [IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)