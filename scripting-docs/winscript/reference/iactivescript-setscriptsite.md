---
title: IActiveScript::SetScriptSite | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: b2a96732e904c7249dc5228ef414c3315012ec56
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097432"
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