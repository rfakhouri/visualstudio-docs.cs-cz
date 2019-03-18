---
title: Iactivescriptparseprocedureold – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptParseProcedureOld
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptParseProcedureOld interface
ms.assetid: d94b391e-4c24-46da-a01f-2c134ca4f041
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 99fa06086bfad56b266b043716e82181aa4c97d5
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58160625"
---
# <a name="iactivescriptparseprocedureold-interface"></a>IActiveScriptParseProcedureOld – rozhraní
Umožňuje textem zdrojového kódu pro postupy mají být přidány do skriptu. U interpretovaných skriptovací jazyky, které nemají nezávislé vývojovém prostředí, jako je například jazyk VBScript, získáte alternativní mechanismus (jiné než `IActiveScriptParse` nebo `IPersist*`) přidat skript procedury do oboru názvů.  
  
> [!NOTE]
>  Toto rozhraní je zastaralé nahrazený `IActiveScriptParseProcedure` rozhraní.  
  
## <a name="methods"></a>Metody  
 Kromě metod zděděných z `IUnknown`, `IActiveScriptParseProcedureOld` rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptParseProcedureOld::ParseProcedureText](../../winscript/reference/iactivescriptparseprocedureold-parseproceduretext.md)|Analyzuje daný kód postupu a postup přidá do oboru názvů.|  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptParseProcedure](../../winscript/reference/iactivescriptparseprocedure.md)