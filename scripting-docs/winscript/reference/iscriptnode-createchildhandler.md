---
title: IScriptNode::CreateChildHandler | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IScriptNode.CreateChildHandler
apilocation:
- scrobj.dll
helpviewer_keywords:
- IScriptNode::CreateChildHandler
ms.assetid: 4ce5eb10-1a3f-43b0-a4b7-599a397ed3a2
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bca8b30021d39638f3755bace2625bb38a44242d
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58149244"
---
# <a name="iscriptnodecreatechildhandler"></a>IScriptNode::CreateChildHandler
Přidá skriptletu jako podřízené instance `IScriptNode`.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT CreateChildHandler(  
   LPCOLESTR          pszDefaultName,  
   LPCOLESTR          *prgpszNames,  
   ULONG              cpszNames,  
   LPCOLESTR          pszEvent,  
   LPCOLESTR          pszDelimiter,  
   ITypeInfo*         ptiSignature,  
   ULONG              iMethodSignature,  
   ULONG              isn,  
   DWORD              dwCookie,  
   IScriptEntry       **ppse  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszDefaultName`  
 [in] Adresa výchozí název, který chcete přidružit k skriptletu.  
  
 `prgpszNames`  
 [v size_is (`cpszNames`)] seznam identifikátorů z plně kvalifikovaný název hostitele.  
  
 `cpszNames`  
 [in] Počet identifikátorů v `prgpszNames` parametru.  
  
 `pszEvent`  
 [in] Adresa vyrovnávací paměti, která identifikuje název události spojené se skriptletem.  
  
 `pszDelimiter`  
 [in] Adresa koncového ze skriptu bloku oddělovač. Pro analýzu, hostitel obvykle používá oddělovač (například dvěma jednoduchými uvozovkami), k zjištění konce bloku skriptu.  
  
 Oddělovač umožňuje předzpracování skript, modul pro vytváření. Modul může například nahradit jednoduchou uvozovku s dvěma jednoduchými uvozovkami pro použití jako oddělovače. Modul zjistí, jak se používá jako oddělovač.  
  
 Nastavte na hodnotu NULL, pokud žádný oddělovač slouží k identifikaci konec bloku skriptu.  
  
 `ptiSignature`  
 [in] Informace o typu objektu funkce.  
  
 `iMethodSignature`  
 [in] Index na funkci `ITypeInfo``ptiSignature` parametru.  
  
 `isn`  
 [in] Index pro podřízenou položku v nadřazeném prvku.  
  
 `dwCookie`  
 [in] Aplikaci hodnotu definovanou uživatelem, který slouží k položce přidružit objekt hostitele.  
  
 `ppse`  
 [out] Adresa proměnné, která přijímá ukazatel `IScriptEntry` rozhraní instance podřízené.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
 Skriptletu určuje obslužné rutiny události. Tato metoda vytvoří skriptletu, pokud je volán `IScriptNode` objekt, který představuje webovou stránku. Tato metoda neproběhne úspěšně, pokud je volána jinými rozhraními.  
  
## <a name="see-also"></a>Viz také  
 [Iscriptnode – rozhraní](../../winscript/reference/iscriptnode-interface.md)   
 [IScriptEntry – rozhraní](../../winscript/reference/iscriptentry-interface.md)