---
title: Scriptstate – výčet | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- SCRIPTSTATE
apilocation:
- scrobj.dll
helpviewer_keywords:
- SCRIPTSTATE enum
ms.assetid: 5f5deb05-c4bb-4964-8077-e624c6b2a14e
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fe6a05c5e73d26a8daa9e46c317422d85d1c40be
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58155547"
---
# <a name="scriptstate-enumeration"></a>SCRIPTSTATE – výčet
Určuje stav skriptovací stroj. Tento výčet je používán [IActiveScript::GetScriptState](../../winscript/reference/iactivescript-getscriptstate.md) , [IActiveScript::SetScriptState](../../winscript/reference/iactivescript-setscriptstate.md) , a [IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md) metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
typedef enum tagSCRIPTSTATE {  
    SCRIPTSTATE_UNINITIALIZED = 0,  
    SCRIPTSTATE_INITIALIZED   = 5,  
    SCRIPTSTATE_STARTED       = 1,  
    SCRIPTSTATE_CONNECTED     = 2,  
    SCRIPTSTATE_DISCONNECTED  = 3,  
    SCRIPTSTATE_CLOSED        = 4  
} SCRIPTSTATE;  
```  
  
## <a name="enumeration-values"></a>Hodnoty výčtu  
  
|||  
|-|-|  
|SCRIPTSTATE_UNINITIALIZED|Skript byl právě vytvořen, ale ještě nebyl inicializován pomocí `IPersist*` rozhraní a [IActiveScript::SetScriptSite](../../winscript/reference/iactivescript-setscriptsite.md) .|  
|SCRIPTSTATE_INITIALIZED|Skript byl inicializován, ale není spuštěna (připojení k jiné objekty nebo zpracování události) nebo spuštěním jakéhokoli kódu. Může být dotázán kód pro spuštění pomocí volání [IActiveScriptParse::ParseScriptText](../../winscript/reference/iactivescriptparse-parsescripttext.md) metody.|  
|SCRIPTSTATE_STARTED|Skript může spustit kód, ale není ještě zpracování událostí objektů přidal [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) metody.|  
|SCRIPTSTATE_CONNECTED|Skript je načten a připojen pro zpracování událostí.|  
|SCRIPTSTATE_DISCONNECTED|Skript je načten a má stav provádění za běhu, ale je dočasně odpojen od zpracování událostí.|  
|SCRIPTSTATE_CLOSED|Skript se zavřel. Skriptovací stroj už funguje a vrátí chyby pro většinu metod.|  
  
## <a name="see-also"></a>Viz také  
 [Konstanty, výčty a kódy chyb aktivních skriptů](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)