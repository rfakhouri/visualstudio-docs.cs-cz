---
title: IActiveScriptError::GetSourceLineText | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptError.GetSourceLineText
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptError_GetSourceLineText
ms.assetid: 64f7f37f-7288-4dbe-b626-a35d90897f36
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 702f1655b244116e1bb7dca3d5fc90de3d1f5bdf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62955003"
---
# <a name="iactivescripterrorgetsourcelinetext"></a>IActiveScriptError::GetSourceLineText
Načte řádku ve zdrojovém souboru, kde došlo k chybě skriptovací modul byl spuštěn skript.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetSourceLineText(  
    BSTR *pbstrSourceLine  // address of buffer for source line  
);  
```  
  
## <a name="parameter"></a>Parametr  
 `pbstrSourceLine`  
 [out] Adresa vyrovnávací paměti, která přijímá řádku zdrojového kódu, ve kterém došlo k chybě.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` v případě úspěšného ověření nebo `E_FAIL` Pokud nebyl načten řádku ve zdrojovém souboru.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptError](../../winscript/reference/iactivescripterror.md)