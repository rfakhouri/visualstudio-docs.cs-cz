---
title: IRemoteDebugApplication110 Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplication110 Interface
ms.assetid: 785ab46a-8827-41cb-806a-132e6b2c8f47
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f280e2b869a3046ecb2d3fac37facdcc1bfeb7fb
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349878"
---
# <a name="iremotedebugapplication110-interface"></a>IRemoteDebugApplication110 – rozhraní
Používají k zajištění nové možnosti, které mohou být volány skript ladicí programy a volající v procesu.  
  
> [!IMPORTANT]
>  Toto rozhraní je implementováno komponentou PDM verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="methods"></a>Metody  
 `IRemoteDebugApplication110` Rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IRemoteDebugApplication110::SetDebuggerOptions](../../winscript/reference/iremotedebugapplication110-setdebuggeroptions.md)|Volá se, aby aktualizovat možnosti ladicího programu. Možnosti výchozí na hodnotu 0 (SDO_NONE).|  
|[IRemoteDebugApplication110::GetCurrentDebuggerOptions](../../winscript/reference/iremotedebugapplication110-getcurrentdebuggeroptions.md)|Vrátí aktuální sadu možností, které jsou povolené.|  
|[IRemoteDebugApplication110::GetMainThread](../../winscript/reference/iremotedebugapplication110-getmainthread.md)|Pro hostitele, které volají setsite – vrátí hlavního vlákna.|