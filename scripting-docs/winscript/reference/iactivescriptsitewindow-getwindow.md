---
title: IActiveScriptSiteWindow::GetWindow | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 7b6efa066765339375a8315695aa9c1de2f9c46b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992078"
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