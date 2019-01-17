---
title: IActiveScriptSiteWindow::GetWindow | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteWindow.GetWindow
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteWindow_GetWindow
ms.assetid: 6284e38c-9dfb-4d69-903d-f243f78c0331
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 268a54ccdcbd70ed159758720db0735f16d81492
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349046"
---
# <a name="iactivescriptsitewindowgetwindow"></a>IActiveScriptSiteWindow::GetWindow
Načte popisovač okna, které může fungovat jako vlastník automaticky otevírané okno, které se musí zobrazit skriptovací stroj.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetWindow(  
    HWND *phwnd  // address of variable for window handle  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `phwnd`  
 [out] Adresa proměnné, která přijímá popisovač okna.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` v případě úspěšného ověření nebo `E_FAIL` Pokud došlo k chybě.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je podobný `IOleWindow::GetWindow` metody.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptSiteWindow](../../winscript/reference/iactivescriptsitewindow.md)