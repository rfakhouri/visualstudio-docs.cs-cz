---
title: IActiveScript::GetScriptThreadState | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.GetScriptThreadState
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_GetScriptThreadState
ms.assetid: 7cac94d0-436e-4c29-895b-0c4afa0b3ccc
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a0066894830c111a8e0ad18f7acdc09d6114162e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62935604"
---
# <a name="iactivescriptgetscriptthreadstate"></a>IActiveScript::GetScriptThreadState
Načte aktuální stav vlákna skriptu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetScriptThreadState(  
    SCRIPTTHREADID stidThread,    // identifier of script thread  
    SCRIPTTHREADSTATE *pstsState  // receives state flag  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `stidThread`  
 [in] Identifikátor vlákna, pro který je požadován stavu, nebo jednu z následujících identifikátorů speciální vlákna:  
  
|Hodnota|Význam|  
|-----------|-------------|  
|SCRIPTTHREADID_BASE|Základní podprocesu. To znamená, že byla vytvořena instance vláken, ve kterém skriptovací stroje.|  
|SCRIPTTHREADID_CURRENT|Aktuálně spuštěné vlákno.|  
  
 `pstsState`  
 [out] Adresa proměnné, která přijímá stav označený vlákna. Stav je indikován jednu s názvem konstantní hodnoty, které jsou definované [scriptthreadstate – výčet](../../winscript/reference/scriptthreadstate-enumeration.md) výčtu. Pokud tento parametr identifikuje aktuální vlákno, může kdykoli změnit stav.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`E_POINTER`|Byl zadán neplatný ukazatel.|  
|`E_UNEXPECTED`|Volání nebylo očekáváno (například skriptovací stroj má ještě nebyly načteny nebo inicializován).|  
  
## <a name="remarks"></a>Poznámky  
 Tuto metodu lze volat z vlákna znaky bez výsledkem znaky popisek hostitele objektů nebo [iactivescriptsite –](../../winscript/reference/iactivescriptsite.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScript](../../winscript/reference/iactivescript.md)