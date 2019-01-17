---
title: IActiveScriptParse – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptParse interface
ms.assetid: 8c967d70-f582-4f64-9e79-49f40c4dcb7c
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8325ffcb21f1871ca742611e6587df02ef3b89c8
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349007"
---
# <a name="iactivescriptparse"></a>IActiveScriptParse
Pokud skript Windows modul umožňuje nezpracovaný text skriptlety kódu mají být přidány do skriptu nebo umožňuje textu výrazu, který se má vyhodnotit v době běhu implementuje `IActiveScriptParse` rozhraní. Pro interpretované skriptovací jazyky, které mají žádné nezávislé vývojovém prostředí, jako je například jazyk VBScript, to poskytuje alternativní mechanismus (jiné než `IPersist*`) Chcete-li získat kód skriptu do skriptovací stroj a připojit fragmenty skript do různých objektu události.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptParse::InitNew](../../winscript/reference/iactivescriptparse-initnew.md)|Inicializuje skriptovací stroj.|  
|[IActiveScriptParse::AddScriptlet](../../winscript/reference/iactivescriptparse-addscriptlet.md)|Přidá skriptlet kódu do skriptu.|  
|[IActiveScriptParse::ParseScriptText](../../winscript/reference/iactivescriptparse-parsescripttext.md)|Analyzuje daný skriptlet kódu, přidává deklarace do oboru názvů a hodnotí kód podle potřeby.|  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní aktivních skriptů](../../winscript/reference/active-script-interfaces.md)