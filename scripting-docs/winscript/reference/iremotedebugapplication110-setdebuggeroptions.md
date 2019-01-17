---
title: IRemoteDebugApplication110::SetDebuggerOptions | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IRemoteDebugApplication110::SetDebuggerOptions
ms.assetid: 58e9fd18-3e0d-47fa-8893-f316146bde84
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 74662b6cfcfb641a59ac93c862bd38c6fa16a900
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346771"
---
# <a name="iremotedebugapplication110setdebuggeroptions"></a>IRemoteDebugApplication110::SetDebuggerOptions
Volá se, aby aktualizovat možnosti ladicího programu. Tato metoda by měla být volána po [IRemoteDebugApplication::ConnectDebugger](../../winscript/reference/iremotedebugapplication-connectdebugger.md). [IRemoteDebugApplication::DisconnectDebugger](../../winscript/reference/iremotedebugapplication-disconnectdebugger.md) metoda automaticky obnoví na výchozí možnosti. Možnosti výchozí na hodnotu 0 (SDO_NONE).  
  
> [!IMPORTANT]
>  [Iremotedebugapplication – rozhraní](../../winscript/reference/iremotedebugapplication-interface.md) je implementováno komponentou Pdm verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetDebuggerOptions(        [in] enum SCRIPT_DEBUGGER_OPTIONS mask,        [in] enum SCRIPT_DEBUGGER_OPTIONS value    );  
```  
  
#### <a name="parameters"></a>Parametry  
 `mask`  
 [Výčet SCRIPT_DEBUGGER_OPTIONS](../../winscript/reference/script-debugger-options-enumeration.md) masky.  
  
 `value`  
 [Výčet SCRIPT_DEBUGGER_OPTIONS](../../winscript/reference/script-debugger-options-enumeration.md) hodnotu.  
  
## <a name="see-also"></a>Viz také  
 [Iremotedebugapplication – rozhraní](../../winscript/reference/iremotedebugapplication-interface.md)   
 [IRemoteDebugApplication110 – rozhraní](../../winscript/reference/iremotedebugapplication110-interface.md)