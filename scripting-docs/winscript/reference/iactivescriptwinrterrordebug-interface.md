---
title: Iactivescriptwinrterrordebug – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptWinRTErrorDebug Interface
ms.assetid: 58b45096-633f-479f-95c4-8eae7376d3a1
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2355b9aa38abbed2ca66964a07bb47082eb76c32
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346498"
---
# <a name="iactivescriptwinrterrordebug-interface"></a>IActiveScriptWinRTErrorDebug – rozhraní
Implementováno modulem JavaScript poskytnout rozšířené informace o prostředí Windows Runtime chybě z [breakreason – výčet](../../winscript/reference/breakreason-enumeration.md) událostí. Vám pomůžou QueryInterface získat ze [iactivescripterror –](../../winscript/reference/iactivescripterror.md) objektu.  
  
> [!IMPORTANT]
>  Toto rozhraní je implementováno komponentou PDM verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="methods"></a>Metody  
 `IActiveScriptWinRTErrorDebug` Rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptWinRTErrorDebug::GetCapabilitySid](../../winscript/reference/iactivescriptwinrterrordebug-getcapabilitysid.md)|Vrátí funkci SID pro prostředí Windows Runtime chybu, pokud je k dispozici.|  
|[IActiveScriptWinRTErrorDebug::GetRestrictedErrorReference](../../winscript/reference/iactivescriptwinrterrordebug-getrestrictederrorreference.md)|Vrátí modulu Windows Runtime s omezením pomocí specifikátoru chybový řetězec odkazu, pokud je k dispozici.|  
|[IActiveScriptWinRTErrorDebug::GetRestrictedErrorString](../../winscript/reference/iactivescriptwinrterrordebug-getrestrictederrorstring.md)|Vrátí modulu Windows Runtime s omezením pomocí specifikátoru řetězec chyby, pokud je k dispozici.|