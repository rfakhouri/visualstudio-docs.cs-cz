---
title: Iactivescriptsitewindow – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 3691a874121c00dcccc69958eb5746a2c1d78122
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58149455"
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