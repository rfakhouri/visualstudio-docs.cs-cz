---
title: Iactivescriptparseprocedure – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptParseProcedure interface
ms.assetid: 741a35bb-5b92-489e-ba8a-a406b42125fc
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 78db05160adef51c414f4c4804f33d47812a9b38
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349540"
---
# <a name="iactivescriptparseprocedure"></a>IActiveScriptParseProcedure
Pokud Windows skriptovací stroj umožňuje textem zdrojového kódu pro postupy, které přidají ke skriptu, implementuje `IActiveScriptParseProcedure` rozhraní. Pro interpretované skriptovací jazyky, které mají žádné nezávislé vývojovém prostředí, jako je například jazyk VBScript, to poskytuje alternativní mechanismus (jiné než `IActiveScriptParse` nebo `IPersist`*) Chcete-li přidat skript procedury do oboru názvů.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|||  
|-|-|  
|Metoda|Popis|  
|[IActiveScriptParseProcedure::ParseProcedureText](../../winscript/reference/iactivescriptparseprocedure-parseproceduretext.md)|Analyzuje daný kód postupu a postup přidá do oboru názvů.|  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní aktivních skriptů](../../winscript/reference/active-script-interfaces.md)