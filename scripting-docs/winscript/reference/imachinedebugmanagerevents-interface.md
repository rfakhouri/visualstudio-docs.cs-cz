---
title: Imachinedebugmanagerevents – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IMachineDebugManagerEvents interface
ms.assetid: 468de2f4-49e0-4f6f-ba0c-0f5f6832c092
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f9aab3d7abeecd22e830c68f174896df0e7df2da
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54344023"
---
# <a name="imachinedebugmanagerevents-interface"></a>IMachineDebugManagerEvents – rozhraní
Signály změny ve spuštěném seznam aplikací, které spravuje správce počítače ladění. Toto rozhraní je možné pomocí ladicího programu integrovaného vývojového prostředí pro zobrazení seznamu dynamických aplikací.  
  
 Kromě metod zděděných z `IUnknown`, `IMachineDebugManagerEvents` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IMachineDebugManagerEvents::onAddApplication](../../winscript/reference/imachinedebugmanagerevents-onaddapplication.md)|Zpracovává událost, když aplikace se přidá do běhu seznamu aplikací.|  
|[IMachineDebugManagerEvents::onRemoveApplication](../../winscript/reference/imachinedebugmanagerevents-onremoveapplication.md)|Zpracuje událost odebrání aplikace spouštění seznam aplikací.|