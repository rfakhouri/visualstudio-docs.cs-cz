---
title: Isimpleconnectionpoint – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 0d18c8f9eef6ddb1a38473eb19984bd9cf7dbd96
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63001501"
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