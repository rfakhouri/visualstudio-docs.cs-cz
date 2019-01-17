---
title: Idebugproperty – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugProperty interface
ms.assetid: 7e8f5341-23ef-4029-814d-f5c2307b9203
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2e5e5274e8a3d1c81ce010afc3893b27510a0fad
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348357"
---
# <a name="idebugproperty-interface"></a>IDebugProperty – rozhraní
Použít k popisu hierarchické vlastnosti entity, který se právě ladí, který má název, typ a hodnotu. Nejčastěji `IDebugProperty` se používá k popisu výsledek vyhodnocení výrazu, příkaz hodnocení nebo vyhodnocení registru.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugProperty` rozhraní.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugProperty::GetPropertyInfo](../../winscript/reference/idebugproperty-getpropertyinfo.md)|Získejte `DebugPropertyInfo` , který popisuje toto `IDebugProperty``.`|  
|[IDebugProperty::GetExtendedInfo](../../winscript/reference/idebugproperty-getextendedinfo.md)|Získá rozšířené informace o vlastnosti.|  
|[IDebugProperty::SetValueAsString](../../winscript/reference/idebugproperty-setvalueasstring.md)|Nastaví hodnotu vlastnosti z řetězce.|  
|[IDebugProperty::EnumMembers](../../winscript/reference/idebugproperty-enummembers.md)|Vytvoří výčet členů vlastnost.|  
|[IDebugProperty::GetParent](../../winscript/reference/idebugproperty-getparent.md)|Získá nadřazený vlastnosti.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: dbgprop.h