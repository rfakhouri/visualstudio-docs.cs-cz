---
title: IActiveScriptSite::OnLeaveScript | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.OnLeaveScript
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_OnLeaveScript
ms.assetid: 79af0e22-fbe3-4fae-8a5f-7af8b857678d
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7d08d58fc788d2d10ed044808ca40a5f4ea929c3
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54093155"
---
# <a name="iactivescriptsiteonleavescript"></a>IActiveScriptSite::OnLeaveScript
Informuje o hostiteli, skriptovací stroj vrátil z spuštěním skriptu kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT OnLeaveScript(void);  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` v případě úspěšného ověření.  
  
## <a name="remarks"></a>Poznámky  
 Skriptovací stroj musí tuto metodu volat před vrácením řízení volající aplikace, kterou zadali skriptovací stroj. Například pokud skript volá objekt, který potom aktivuje událost zpracovává skriptovací stroj skriptovací stroj musí volat [IActiveScriptSite::OnEnterScript](../../winscript/reference/iactivescriptsite-onenterscript.md) metodu před spuštěním události a musí volat `IActiveScriptSite::OnLeaveScript`po spuštění události návrat zpět k objektu, která vyvolala událost. Volání této metody mohou být vnořené. Všechna volání `IActiveScriptSite::OnEnterScript` vyžaduje odpovídající volání této metody.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)