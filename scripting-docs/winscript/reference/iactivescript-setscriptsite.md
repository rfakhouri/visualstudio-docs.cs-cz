---
title: IActiveScript::SetScriptSite | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScript.SetScriptSite
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScript_SetScriptSite
ms.assetid: 47d94c32-09f8-4539-ac56-0236026f627b
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3fdf5f3ae84d1a991d67170b5f2b02114b91ee05
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58157065"
---
# <a name="iactivescriptsetscriptsite"></a>IActiveScript::SetScriptSite
Informuje o tom skriptovacího stroje ze [iactivescriptsite –](../../winscript/reference/iactivescriptsite.md) lokality rozhraní, které jsou poskytovány tímto hostitelem. Volejte tuto metodu před všemi ostatními [IActiveScript –](../../winscript/reference/iactivescript.md) metody rozhraní se používá.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SetScriptSite(  
    IActiveScriptSite *pScriptSite  // address of host script site  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pScriptSite`  
 [in] Adresa hostitele zadaný skript serveru chcete přidružit k této instanci skriptovací stroj. Lokality musí jednoznačně přiřazen k této instanci skriptovací stroj; nemůže být sdílen s další skriptovací moduly.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí jednu z následujících hodnot:  
  
|Návratová hodnota|Význam|  
|------------------|-------------|  
|`S_OK`|Úspěch.|  
|`E_FAIL`|Došlo k nespecifikované chybě; skriptovací modul se nepodařilo dokončit inicializace webu.|  
|`E_INVALIDARG`|Argument byl neplatný.|  
|`E_POINTER`|Byl zadán neplatný ukazatel.|  
|`E_UNEXPECTED`|Volání nebylo očekáváno (například web již byl nastaven).|  
  
## <a name="see-also"></a>Viz také  
 [IActiveScript](../../winscript/reference/iactivescript.md)