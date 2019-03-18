---
title: IActiveScript – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScript interface
ms.assetid: d8acee11-7f0d-4999-b97a-66774af16f71
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b7e3a0172a798eab9a743f446dff3d339a785b2
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58150996"
---
# <a name="iactivescript"></a>IActiveScript
Poskytuje metody, které jsou nezbytné k inicializaci skriptovací stroj. Skriptovací stroj musí implementovat `IActiveScript` rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScript::SetScriptSite](../../winscript/reference/iactivescript-setscriptsite.md)|Informuje o tom skriptovacího stroje ze [iactivescriptsite –](../../winscript/reference/iactivescriptsite.md) poskytované hostitelem lokality.|  
|[IActiveScript::GetScriptSite](../../winscript/reference/iactivescript-getscriptsite.md)|Načte objekt lokality přidružený modul skriptu Windows.|  
|[IActiveScript::SetScriptState](../../winscript/reference/iactivescript-setscriptstate.md)|Vloží skriptovací stroj do zadaného stavu.|  
|[IActiveScript::GetScriptState](../../winscript/reference/iactivescript-getscriptstate.md)|Načte aktuální stav skriptovací stroj.|  
|[IActiveScript::Close](../../winscript/reference/iactivescript-close.md)|Způsobí, že skriptovací stroj opustit všechny aktuálně načtené skriptu, přijít o jejím stavu a uvolnit všechny ukazatele rozhraní, které je jiné objekty, tedy zadáte uzavřeného stavu.|  
|[IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md)|Přidá do oboru názvů skriptovací stroj název položky kořenové úrovně.|  
|[IActiveScript::AddTypeLib](../../winscript/reference/iactivescript-addtypelib.md)|Přidá knihovnu typů do oboru skriptu.|  
|[IActiveScript::GetScriptDispatch](../../winscript/reference/iactivescript-getscriptdispatch.md)|Načte `IDispatch` rozhraní pro spouštění skriptu.|  
|[IActiveScript::GetCurrentScriptThreadID](../../winscript/reference/iactivescript-getcurrentscriptthreadid.md)|Načte identifikátor skriptovací stroj definované pro aktuálně spuštěné vlákno.|  
|[IActiveScript::GetScriptThreadID](../../winscript/reference/iactivescript-getscriptthreadid.md)|Načte identifikátor skriptovací stroj definované pro vlákno přidružené k dané vlákno Microsoft Win32.|  
|[IActiveScript::GetScriptThreadState](../../winscript/reference/iactivescript-getscriptthreadstate.md)|Načte aktuální stav vlákna skriptu.|  
|[IActiveScript::InterruptScriptThread](../../winscript/reference/iactivescript-interruptscriptthread.md)|Přeruší provádění spuštěné vlákno skriptu.|  
|[IActiveScript::Clone](../../winscript/reference/iactivescript-clone.md)|Klonuje aktuální skriptovací stroj (bez jakékoli aktuální stav provádění), vrátí načíst skriptovací stroj, který nemá žádná lokalita v aktuálním vlákně.|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace skriptovacích rozhraní systému Windows](../../winscript/reference/windows-script-interfaces-reference.md)