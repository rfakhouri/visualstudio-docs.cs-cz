---
title: IActiveScriptSite::OnLeaveScript | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: da39058a8f069c4799835108372d11849d86444e
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58160742"
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