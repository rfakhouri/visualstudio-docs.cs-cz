---
title: IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptSiteDebugEx.OnCanNotJITScriptErrorDebug
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug
ms.assetid: 83f81476-bf12-47f2-897d-1d37d21137d4
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 70dd250359d52ae0929fb5fb2c60087f66af2160
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54095118"
---
# <a name="iactivescriptsitedebugexoncannotjitscripterrordebug"></a>IActiveScriptSiteDebugEx::OnCanNotJITScriptErrorDebug
Informuje o tom, že hostitel o Chyba za běhu skriptu při ladění procesu Správce JIT ladicí program nenajde.  
  
 Implementace ladicího programu v hostiteli, zpracovávejte [IActiveScriptSiteDebug::OnScriptErrorDebug](../../winscript/reference/iactivescriptsitedebug-onscripterrordebug.md). Založené na akci uživatele, hostitele můžete připojit ladicí program a vrátit, nebo vrátit spouštění v ladicím programu OnScriptErrorDebug `pfEnterDebugger` parametru. Byste měli také implementovat toto rozhraní k odeslání oznámení o chybě za běhu i v případě, že neexistují žádné externí ladicích programů, které může být interpretován pomocí Správce ladění procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT OnCanNotJITScriptErrorDebug(  
   IActiveScriptErrorDebug*  pErrorDebug  
   BOOL *pfCallOnScriptErrorWhenContinuing  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pErrorDebug`  
 [in] Chyba za běhu, ke které došlo.  
  
 `pfCallOnScriptErrorWhenContinuingt`  
 [out] Zda má být volána [IActiveScriptSiteDebug::OnScriptErrorDebug](../../winscript/reference/iactivescriptsitedebug-onscripterrordebug.md) Pokud se uživatel rozhodne pokračovat bez ladění.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Byste měli také implementovat toto rozhraní k odeslání oznámení.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptSiteDebugEx – rozhraní](../../winscript/reference/iactivescriptsitedebugex-interface.md)