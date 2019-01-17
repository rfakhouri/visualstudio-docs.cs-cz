---
title: IActiveScriptErrorDebug110 Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: 067a62ec8b87c448577cfd6e5789ae5e073b5fb8
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345900"
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