---
title: Aktivních skriptů konstanty, výčty a kódy chyb | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: aab24471-5817-45c0-be07-ffe4648923ed
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 090b494e904fbef1c0d3d8b380f7a184a6042788
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62953995"
---
# <a name="active-script-constants-enumerations-and-error-codes"></a>Konstanty, výčty a kódy chyb aktivních skriptů
Tato část popisuje, výčty a kódy chyb používané Windows skriptovací stroje.  
  
## <a name="constants"></a>Konstanty  
  
|Konstanta|Popis|  
|--------------|-----------------|  
|[SCRIPTTHREADID – konstanty](../../winscript/reference/scriptthreadid-constants.md)|Určuje typ vlákna.|  
  
## <a name="properties"></a>Vlastnosti  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[SCRIPTPROP_HOSTKEEPALIVE – vlastnost](../../winscript/reference/scriptprop-hostkeepalive-property.md)|Slouží k určení, zda skriptovací stroj nutné udržovat plně funkční, pokud existují zbývající odkazy.|  
  
## <a name="enumerations"></a>Výčty  
  
|Výčet|Popis|  
|-----------------|-----------------|  
|[SCRIPTGCTYPE – výčet](../../winscript/reference/scriptgctype-enumeration.md)|Typ kolekce paměti k provedení.|  
|[SCRIPTLANGUAGEVERSION – výčet](../../winscript/reference/scriptlanguageversion-enumeration.md)|Určuje možné skriptování verze.|  
|[SCRIPTSTATE – výčet](../../winscript/reference/scriptstate-enumeration.md)|Určuje stav skriptovací stroj.|  
|||  
|[SCRIPTTHREADSTATE – výčet](../../winscript/reference/scriptthreadstate-enumeration.md)|Určuje stav vlákna v skriptovací stroj.|  
|[SCRIPTTRACEINFO – výčet](../../winscript/reference/scripttraceinfo-enumeration.md)|Představuje událost skriptu, který je trasován. Používáno [iactivescriptsitetraceinfo::sendscripttraceinfo – metoda](../../winscript/reference/iactivescriptsitetraceinfo-sendscripttraceinfo-method.md).|  
|[SCRIPTUICHANDLING – výčet](../../winscript/reference/scriptuichandling-enumeration.md)|Představuje způsob, že ovládací prvek uživatelského rozhraní by měly být zpracovány.|  
|[SCRIPTUICITEM – výčet](../../winscript/reference/scriptuicitem-enumeration.md)|Představuje typ položky uživatelského rozhraní. Používáno [iactivescriptsiteuicontrol::getuibehavior – metoda](../../winscript/reference/iactivescriptsiteuicontrol-getuibehavior-method.md).|  
  
## <a name="error-codes"></a>Chybové kódy  
  
|Kód chyby|Popis|  
|----------------|-----------------|  
|[SCRIPT_E_PROPAGATE – kód chyby](../../winscript/reference/script-e-propagate-error-code.md)|Chyba skriptu je rozšířen volajícímu, což může být v jiném vlákně.|  
|[SCRIPT_E_RECORDED – kód chyby](../../winscript/reference/script-e-recorded-error-code.md)|Byl předán chybu mezi skriptovací stroj a hostitelem.|  
|[SCRIPT_E_REPORTED – kód chyby](../../winscript/reference/script-e-reported-error-code.md)|Skriptovací modul oznámil nezpracovanou výjimku k hostiteli.|  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní aktivních skriptů](../../winscript/reference/active-script-interfaces.md)