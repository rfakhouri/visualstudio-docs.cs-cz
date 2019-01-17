---
title: Isimpleconnectionpoint – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- ISimpleConnectionPoint interface
ms.assetid: f632a82f-942d-4291-963e-e9fa2b162493
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4a756fa3f933f4adff56c41a86aee19a0a2a93aa
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346407"
---
# <a name="isimpleconnectionpoint-interface"></a>ISimpleConnectionPoint – rozhraní
Poskytuje jednoduchý způsob pro popisující a výčet události odesílané v bodě připojení. Toto rozhraní také umožňuje snadno připojit `IDispatch` objekt těchto událostí. Toto rozhraní je implementováno pomocí v procesu ladění správce (PDM) a používané skriptovacích strojů ukládaných.  
  
 Toto rozhraní je k dispozici `IDebugHelper::CreateSimpleConnectionPoint`.  
  
 Kromě metod zděděných z `IUnknown`, `ISimpleConnectionPoint` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[ISimpleConnectionPoint::Advise](../../winscript/reference/isimpleconnectionpoint-advise.md)|Naváže připojení mezi objektu bodu jednoduchých připojení a jímkou klienta.|  
|[ISimpleConnectionPoint::DescribeEvents](../../winscript/reference/isimpleconnectionpoint-describeevents.md)|Vrátí identifikátor DISPID a název pro každou jednotlivou událost v zadaném rozsahu událostí.|  
|[ISimpleConnectionPoint::GetEventCount](../../winscript/reference/isimpleconnectionpoint-geteventcount.md)|Vrátí počet událostí, které jsou zveřejněné na tomto rozhraní.|  
|[ISimpleConnectionPoint::Unadvise](../../winscript/reference/isimpleconnectionpoint-unadvise.md)|Ukončí připojení k advisory dříve vytvořeno prostřednictvím `ISimpleConnectionPoint::Advise`.|  
  
## <a name="see-also"></a>Viz také  
 [IDebugProperty – rozhraní](../../winscript/reference/idebugproperty-interface.md)