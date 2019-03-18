---
title: Idebugapplicationnodeevents – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNodeEvents interface
ms.assetid: 02e0bb17-84ce-458b-bae6-608a9899e535
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7412e258c7f67f44bde6f69b593a1eecb1d84e07
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58150507"
---
# <a name="idebugapplicationnodeevents-interface"></a>IDebugApplicationNodeEvents – rozhraní
Poskytuje rozhraní události pro `IDebugApplicationNode` rozhraní.  
  
 Kromě metod zděděných z `IUnknown`, `IDebugApplicationNodeEvents` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugApplicationNodeEvents::onAddChild](../../winscript/reference/idebugapplicationnodeevents-onaddchild.md)|Zpracovává událost, když je do objektu ladění aplikace uzlu přidat podřízený uzel.|  
|[IDebugApplicationNodeEvents::onRemoveChild](../../winscript/reference/idebugapplicationnodeevents-onremovechild.md)|Zpracovává událost, když je podřízený uzel odebrán z objektu uzlu ladění aplikace.|  
|[IDebugApplicationNodeEvents::onDetach](../../winscript/reference/idebugapplicationnodeevents-ondetach.md)|Zpracovává událost značící, že objekt uzlu ladění aplikace byla odpojena od nadřazeného uzlu.|  
|[IDebugApplicationNodeEvents::onAttach](../../winscript/reference/idebugapplicationnodeevents-onattach.md)|Zpracovává událost značící, že objekt uzlu ladění aplikace byl připojen k nadřazený uzel.|  
  
## <a name="see-also"></a>Viz také  
 [IDebugApplicationNode – rozhraní](../../winscript/reference/idebugapplicationnode-interface.md)