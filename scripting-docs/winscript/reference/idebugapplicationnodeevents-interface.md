---
title: Idebugapplicationnodeevents – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: 0396ed90437a98c8ee398f3c3acb0aeb5ddc77e2
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348409"
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