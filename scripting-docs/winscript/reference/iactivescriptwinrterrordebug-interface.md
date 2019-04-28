---
title: Iactivescriptwinrterrordebug – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 52e7728b4143231912227e5e55faa5eef01b7490
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63425790"
---
# <a name="iactivescriptwinrterrordebug-interface"></a>IActiveScriptWinRTErrorDebug – rozhraní
Implementováno modulem JavaScript poskytnout rozšířené informace o prostředí Windows Runtime chybě z [breakreason – výčet](../../winscript/reference/breakreason-enumeration.md) událostí. Vám pomůžou QueryInterface získat ze [iactivescripterror –](../../winscript/reference/iactivescripterror.md) objektu.  
  
> [!IMPORTANT]
> Toto rozhraní je implementováno komponentou PDM verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="methods"></a>Metody  
 `IActiveScriptWinRTErrorDebug` Rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptWinRTErrorDebug::GetCapabilitySid](../../winscript/reference/iactivescriptwinrterrordebug-getcapabilitysid.md)|Vrátí funkci SID pro prostředí Windows Runtime chybu, pokud je k dispozici.|  
|[IActiveScriptWinRTErrorDebug::GetRestrictedErrorReference](../../winscript/reference/iactivescriptwinrterrordebug-getrestrictederrorreference.md)|Vrátí modulu Windows Runtime s omezením pomocí specifikátoru chybový řetězec odkazu, pokud je k dispozici.|  
|[IActiveScriptWinRTErrorDebug::GetRestrictedErrorString](../../winscript/reference/iactivescriptwinrterrordebug-getrestrictederrorstring.md)|Vrátí modulu Windows Runtime s omezením pomocí specifikátoru řetězec chyby, pokud je k dispozici.|