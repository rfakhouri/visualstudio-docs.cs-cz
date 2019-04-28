---
title: IActiveScriptWinRTErrorDebug::GetRestrictedErrorReference | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptWinRTErrorDebug::GetRestrictedErrorReference
ms.assetid: fcf60971-9518-4b24-a3a6-1e2e30a02cea
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d4696c66ec331c08f3419d79f0f48feb3bf9d80f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63432962"
---
# <a name="iactivescriptwinrterrordebuggetrestrictederrorreference"></a>IActiveScriptWinRTErrorDebug::GetRestrictedErrorReference
Vrátí modulu Windows Runtime s omezením pomocí specifikátoru chyba odkazu, pokud je k dispozici.  
  
> [!IMPORTANT]
> [Iactivescriptwinrterrordebug – rozhraní](../../winscript/reference/iactivescriptwinrterrordebug-interface.md) je implementováno komponentou Pdm verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetRestrictedErrorReference([out] BSTR * referenceString);  
```  
  
#### <a name="parameters"></a>Parametry  
 `referenceString`  
 [out] Chyba řetězec odkazu.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptWinRTErrorDebug – rozhraní](../../winscript/reference/iactivescriptwinrterrordebug-interface.md)