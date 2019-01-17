---
title: IActiveScriptSite | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: b7ebbd5301ea1d8ea7cabf235ae3f3c7bb1ba3b2
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346888"
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