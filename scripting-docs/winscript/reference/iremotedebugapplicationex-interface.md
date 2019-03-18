---
title: Iremotedebugapplicationex – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplicationEx Interface
ms.assetid: 8e16164d-dbb2-4488-9507-25ae34f343dc
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab9e25a28ade1ac73b9e4837dae61e2d91f24c45
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58144404"
---
# <a name="iremotedebugapplicationex-interface"></a>IRemoteDebugApplicationEx – rozhraní
Představuje běžící aplikaci. Nemusí se tak, aby odpovídaly k procesu operačního systému. Ladicí program obvykle, zaměřuje na aplikace pro ladění. Správce ladění procesu obvykle implementují objektu aplikace.  
  
 Kromě metod zděděných z `IUnknown`, `IRemoteDebugApplicationEx` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IRemoteDebugApplicationEx:GetHostPid](../../winscript/reference/iremotedebugapplicationex-gethostpid.md)|Vrátí ID procesu pro hostitelskou aplikaci.|  
|GetHostMachineName|Vrátí název počítače, na kterém běží hostitelská aplikace na.|  
|[IRemoteDebugApplicationEx:SetLocale](../../winscript/reference/iremotedebugapplicationex-setlocale.md)|Nastaví jazyk pro lokalizaci ladicího programu.|  
|[IRemoteDebugApplicationEx:ForceStepMode](../../winscript/reference/iremotedebugapplicationex-forcestepmode.md)|Vynutí ladicí program v režimu krokování.|  
|[IRemoteDebugApplicationEx:RevokeBreak](../../winscript/reference/iremotedebugapplicationex-revokebreak.md)|Odvolá příkaz break.|  
|SetProxyBlanketAndAddRef|Aktualizuje informace o zabezpečení COM na serveru proxy pro objekt ladicího programu k zajištění kompatibility ve vzdálené ladění z operačního systému Windows 95.|  
|ReleaseFromSetProxyBlanket|AddRef verzí z SetProxyBlanketAndAddRef.|