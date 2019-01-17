---
title: IActiveScriptSite::OnEnterScript | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSite.OnEnterScript
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSite_OnEnterScript
ms.assetid: 1ed9178c-fe80-41c4-b74d-23b85f9cddbf
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ccef1b2bf63c4421843d3a33cab2e4f471a48251
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346511"
---
# <a name="iactivescriptsiteonenterscript"></a>IActiveScriptSite::OnEnterScript
Informuje o hostiteli, že byl zahájen skriptovací modul spouští kód skriptu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT OnEnterScript(void);  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí `S_OK` v případě úspěšného ověření.  
  
## <a name="remarks"></a>Poznámky  
 Skriptovací stroj musí volání této metody na každou položku nebo návratový do skriptovací stroj. Například pokud skript volá objekt, který potom aktivuje událost zpracovává skriptovací stroj skriptovací stroj musí volat `IActiveScriptSite::OnEnterScript` před spouštěním události a musí volat [IActiveScriptSite::OnLeaveScript](../../winscript/reference/iactivescriptsite-onleavescript.md) Metoda po spuštění události, ale před vrácením objektu, která vyvolala událost. Volání této metody mohou být vnořené. Každé volání této metody vyžaduje odpovídající volání `IActiveScriptSite::OnLeaveScript`.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)