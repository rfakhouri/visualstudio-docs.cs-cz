---
title: Ienumdebugpropertyinfo – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 736bea847908e3c70d6caf2f8e41af38608f4f23
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62963426"
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