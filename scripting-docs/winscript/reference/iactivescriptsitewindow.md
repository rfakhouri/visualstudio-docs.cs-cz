---
title: Iactivescriptsitewindow – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptSiteWindow interface
ms.assetid: 96d5c493-2c0b-47e2-848b-4a8dacdcd65c
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a160b17f4a46237ab78b378664a046fe8a0e7d4
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345718"
---
# <a name="iactivescriptsitewindow"></a>IActiveScriptSiteWindow
Toto rozhraní je implementováno hostitele, kteří podporují uživatelského rozhraní na stejný objekt jako [iactivescriptsite –](../../winscript/reference/iactivescriptsite.md) . Hostitelé, kteří nepodporují uživatelské rozhraní, jako jsou třeba servery, by implementovat `IActiveScriptSiteWindow` rozhraní. Skriptovací stroj přistupuje k tomuto rozhraní voláním `QueryInterface` z `IActiveScriptSite`.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptSiteWindow::GetWindow](../../winscript/reference/iactivescriptsitewindow-getwindow.md)|Načte popisovač okna, která může fungovat jako vlastník automaticky otevírané okno, které se musí zobrazit skriptovací stroj.|  
|[IActiveScriptSiteWindow::EnableModeless](../../winscript/reference/iactivescriptsitewindow-enablemodeless.md)|Způsobí, že hostitel k povolení nebo zakázání její hlavní okno, stejně jako všechna nemodální dialogová okna.|  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní aktivních skriptů](../../winscript/reference/active-script-interfaces.md)