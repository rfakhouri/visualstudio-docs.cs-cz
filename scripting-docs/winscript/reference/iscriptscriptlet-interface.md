---
title: Iscriptscriptlet – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IScriptScriptlet interface
ms.assetid: b9981908-a337-4228-864c-c741f111ab2d
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c11aada6b8c39c7dd5f0b2a6b30cdd837aa0edda
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58151255"
---
# <a name="iscriptscriptlet-interface"></a>IScriptScriptlet – rozhraní
Objekt, který implementuje `IScriptScriptlet` rozhraní představuje skriptu obslužné rutiny události.  
  
 Kromě metod zděděných z `IScriptEntry`, `IScriptScriptlet` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IScriptScriptlet::GetEventName](../../winscript/reference/iscriptscriptlet-geteventname.md)|Vrátí název události, která souvisí se skriptletem.|  
|[IScriptScriptlet:: GetSimpleEventName](../../winscript/reference/iscriptscriptlet-getsimpleeventname.md)|Vrátí název jednoduché události, která souvisí s skriptletu. Toto je název jednoho slova, který neobsahuje žádné prázdné znaky.|  
|[IScriptScriptlet::GetSubItemName](../../winscript/reference/iscriptscriptlet-getsubitemname.md)|Vrátí poslední identifikátor v plně kvalifikovaný název hostitele objektů skriptletu.|  
|[IScriptScriptlet::SetEventName](../../winscript/reference/iscriptscriptlet-seteventname.md)|Nastaví název události, která souvisí se skriptletem.|  
|[IScriptScriptlet::SetSimpleEventName](../../winscript/reference/iscriptscriptlet-setsimpleeventname.md)|Nastaví název jednoduché události, která souvisí s skriptletu. Toto je název jednoho slova, který neobsahuje žádné prázdné znaky.|  
|[IScriptScriptlet::SetSubItemName](../../winscript/reference/iscriptscriptlet-setsubitemname.md)|Nastaví poslední identifikátor v plně kvalifikovaný název hostitele objektů skriptletu.|  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní pro vytváření aktivních skriptů](../../winscript/reference/active-script-authoring-interfaces.md)