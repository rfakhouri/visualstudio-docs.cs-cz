---
title: IActiveScriptSite | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptSite interface
ms.assetid: 4d604a11-5365-46cf-ab71-39b3dbbe9f22
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 67e16e2825f03c9ae452e639d6a086bee584ac95
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58152639"
---
# <a name="iactivescriptsite"></a>IActiveScriptSite
Implementovat hostitelem pro vytvoření webu pro modul skriptu Windows. Tato lokalita bude obvykle spojené s kontejnerem všechny objekty, které jsou viditelné pro skript (například ovládací prvky ActiveX). Tento kontejner se obvykle odpovídají dokumentu nebo zobrazení stránky. Microsoft Internet Explorer by například vytvořit kontejner, pro každou stránku HTML, který se zobrazí. Každý ActiveX na stránce a skriptovací stroj, ovládací prvek (nebo jiné automatizační objekt) by vyčíslitelné v tomto kontejneru.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|||  
|-|-|  
|Metoda|Popis|  
|[IActiveScriptSite::GetLCID](../../winscript/reference/iactivescriptsite-getlcid.md)|Načte identifikátor národního prostředí, kterou hostitel používá pro zobrazení prvků uživatelského rozhraní.|  
|[IActiveScriptSite::GetItemInfo](../../winscript/reference/iactivescriptsite-getiteminfo.md)|Získá informace o položce, která byla přidána na modul pomocí volání [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) metody.|  
|[IActiveScriptSite::GetDocVersionString](../../winscript/reference/iactivescriptsite-getdocversionstring.md)|Načte řetězec definované hostitele, který jednoznačně identifikuje aktuální verzi dokumentu z pohledu hostitele.|  
|[IActiveScriptSite::OnScriptTerminate](../../winscript/reference/iactivescriptsite-onscriptterminate.md)|Volá se při dokončení provádění skriptu.|  
|[IActiveScriptSite::OnStateChange](../../winscript/reference/iactivescriptsite-onstatechange.md)|Informuje o hostiteli, že skriptovací stroj změnil stavy.|  
|[IActiveScriptSite::OnScriptError](../../winscript/reference/iactivescriptsite-onscripterror.md)|Informuje o hostiteli, provádění došlo k chybě při spuštění skriptu modulu.|  
|[IActiveScriptSite::OnEnterScript](../../winscript/reference/iactivescriptsite-onenterscript.md)|Informuje o hostiteli, že byl zahájen skriptovací modul spouští kód skriptu.|  
|[IActiveScriptSite::OnLeaveScript](../../winscript/reference/iactivescriptsite-onleavescript.md)|Informuje o hostiteli, skriptovací stroj vrátil z spuštěním skriptu kódu.|  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní aktivních skriptů](../../winscript/reference/active-script-interfaces.md)