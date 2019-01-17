---
title: Ienumdebugpropertyinfo – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IEnumDebugPropertyInfo interface
ms.assetid: c5eea4da-8414-408a-a8f6-6a9ca8745868
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 744794a5b68c9d2e256a9d85cd7ce063dbf975ad
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349956"
---
# <a name="ienumdebugpropertyinfo-interface"></a>IEnumDebugPropertyInfo – rozhraní
Vytvoří výčet `DebugPropertyInfo` struktury.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IEnumDebugPropertyInfo`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IEnumDebugPropertyInfo::Next](../../winscript/reference/ienumdebugpropertyinfo-next.md)|Načte zadaný počet `DebugPropertyInfo` struktury v sekvenci výčtu.|  
|[IEnumDebugPropertyInfo::Skip](../../winscript/reference/ienumdebugpropertyinfo-skip.md)|Vynechá zadaný počet `DebugPropertyInfo` struktury v sekvenci výčtu.|  
|[IEnumDebugPropertyInfo::Reset](../../winscript/reference/ienumdebugpropertyinfo-reset.md)|Návrat na začátek pořadí výčtu.|  
|[IEnumDebugPropertyInfo::Clone](../../winscript/reference/ienumdebugpropertyinfo-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|  
|[IEnumDebugPropertyInfo::GetCount](../../winscript/reference/ienumdebugpropertyinfo-getcount.md)|Získá počet `DebugPropertyInfo` struktury v enumerátor.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: dbgprop.h  
  
## <a name="see-also"></a>Viz také  
 [DebugPropertyInfo – struktura](../../winscript/reference/debugpropertyinfo-structure.md)