---
title: Iscriptentry – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IScriptEntry interface
ms.assetid: 86da3bc1-58b7-4d73-87ab-bc3ce34e3f41
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0dc50a6aa5cf032827feac6b483b141b79f60e77
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58148123"
---
# <a name="iscriptentry-interface"></a>IScriptEntry – rozhraní
Objekt, který implementuje `IScriptEntry` rozhraní představuje blok skriptu nebo objekt funkce.  
  
 Kromě metod zděděných z `IScriptNode`, `IScriptEntry` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IScriptEntry::GetBody](../../winscript/reference/iscriptentry-getbody.md)|Vrátí text, který odpovídá do těla `IScriptEntry` skriptovém bloku, blok funkce nebo skriptletu.|  
|[IScriptEntry::GetItemName](../../winscript/reference/iscriptentry-getitemname.md)|Vrátí název položky, který identifikuje `IScriptEntry` objektu.|  
|[IScriptEntry::GetName](../../winscript/reference/iscriptentry-getname.md)|U položky, které představují jeden objekt (například funkce) vrátí název objektu.|  
|[IScriptEntry::GetRange](../../winscript/reference/iscriptentry-getrange.md)|Vrátí počáteční pozice a délka položky.|  
|[IScriptEntry::GetSignature](../../winscript/reference/iscriptentry-getsignature.md)|Vrátí informace o typu `IScriptEntry` objektu funkce.|  
|[IScriptEntry::GetText](../../winscript/reference/iscriptentry-gettext.md)|Vrátí text, který odpovídá `IScriptEntry` bloku skriptu nebo zdrojový kód, který je součástí `IScriptScriptlet` obslužné rutiny události.|  
|[IScriptEntry::SetBody](../../winscript/reference/iscriptentry-setbody.md)|Nastaví text, který je v těle `IScriptEntry` bloku skriptu nebo `IScriptScriptlet` skriptletu.|  
|[IScriptEntry::SetItemName](../../winscript/reference/iscriptentry-setitemname.md)|Nastaví název položky, který identifikuje `IScriptEntry` objektu.|  
|[IScriptEntry::SetName](../../winscript/reference/iscriptentry-setname.md)|Položky, které představují jeden objekt (například funkce) nastaví název objektu.|  
|[IScriptEntry::SetSignature](../../winscript/reference/iscriptentry-setsignature.md)|Nastaví typ informace pro `IScriptEntry` objektu funkce.|  
|[IScriptEntry::SetText](../../winscript/reference/iscriptentry-settext.md)|Nastaví text, který odpovídá `IScriptEntry` bloku skriptu nebo zdrojový kód, který je součástí `IScriptScriptlet` obslužné rutiny události.|  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní pro vytváření aktivních skriptů](../../winscript/reference/active-script-authoring-interfaces.md)