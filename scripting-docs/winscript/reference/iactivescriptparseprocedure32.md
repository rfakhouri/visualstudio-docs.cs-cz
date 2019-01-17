---
title: IActiveScriptParseProcedure32 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 387a856b-f5dc-4371-8620-bd574e046c2c
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: 10cdff328216d06a3326dd3595ef8fc78bc9cfc9
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348110"
---
# <a name="iactivescriptparseprocedure32"></a>IActiveScriptParseProcedure32
Pokud Windows skriptovací stroj umožňuje textem zdrojového kódu pro postupy, které přidají ke skriptu, implementuje `IActiveScriptParseProcedure32` rozhraní. Pro interpretované skriptovací jazyky, které mají žádné nezávislé vývojovém prostředí, jako je například jazyk VBScript, to poskytuje alternativní mechanismus (jiné než `IActiveScriptParse32` nebo `IPersist`*) Chcete-li přidat skript procedury do oboru názvů.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|||  
|-|-|  
|Metoda|Popis|  
|[IActiveScriptParseProcedure32::ParseProcedureText](../../winscript/reference/iactivescriptparseprocedure32-parseproceduretext.md)|Analyzuje daný kód postupu a postup přidá do oboru názvů.|  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní aktivních skriptů](../../winscript/reference/active-script-interfaces.md)