---
title: IActiveScriptSiteWindow::EnableModeless | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteWindow.EnableModeless
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteWindow_EnableModeless
ms.assetid: 83fe4f62-8e97-4f03-bc6f-d90aa888657d
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4cea23890539ca80abf8e3e58b0f8c48b7ca1fc9
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093012"
---
# <a name="iactivescriptsitewindowenablemodeless"></a>IActiveScriptSiteWindow::EnableModeless
Způsobí, že hostitel k povolení nebo zakázání její hlavní okno, stejně jako všechna nemodální dialogová okna.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT EnableModeless(  
    BOOL fEnable  // enable flag  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `fEnable`  
 [in] Příznak, který, pokud `TRUE`, umožňuje hlavní okno a nemodální dialogová okna nebo pokud `FALSE`, zakazuje je.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` v případě úspěšného ověření nebo `E_FAIL` Pokud došlo k chybě.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je stejné jako `IOleInPlaceFrame::EnableModeless` metody.  
  
 Volání této metody mohou být vnořené.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptSiteWindow](../../winscript/reference/iactivescriptsitewindow.md)