---
title: IActiveScriptErrorDebug110 Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptErrorDebug110 Interface
ms.assetid: 5c1a4993-4cad-4ccf-89c2-53abfddfe1f2
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1bac0c15f31f12ae48f6669bf9a0853550f8c191
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58150644"
---
# <a name="iactivescripterrordebug110-interface"></a>IActiveScriptErrorDebug110 – rozhraní
Přidá funkce, které [iactivescriptdebug – rozhraní](../../winscript/reference/iactivescriptdebug-interface.md). Toto rozhraní je implementováno modulem JavaScript za účelem zjištění, proč došlo k události BREAKREASON_ERROR.  
  
> [!IMPORTANT]
>  Toto rozhraní je implementováno komponentou PDM verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="methods"></a>Metody  
 `IActiveScriptErrorDebug110` Rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptErrorDebug110::GetExceptionThrownKind](../../winscript/reference/iactivescripterrordebug110-getexceptionthrownkind.md)|Vrací druh výjimky pro vyvolanou výjimku.|