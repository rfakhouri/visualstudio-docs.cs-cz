---
title: Iactivescriptsitedebug – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptSiteDebug interface
ms.assetid: 2557ee09-688b-4c03-a821-180c24dfa0e6
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3cd8043648586ed3c614cbb137e51d992d7ae29b
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58145775"
---
# <a name="iactivescriptsitedebug-interface"></a>IActiveScriptSiteDebug – rozhraní
Implementace hostitelů `IActiveScriptSiteDebug` rozhraní provádět správu dokumentů a k účasti v ladění. `IActiveScriptSite` Objekt obvykle poskytuje implementaci `IActiveScriptSiteDebug` rozhraní. Pokud to uděláte, zavolejte `IActiveScriptSite::QueryInterface` metodu k získání `IActiveScriptSiteDebug` rozhraní.  
  
 Kromě metod zděděných z `IUnknown`, `IActiveScriptSiteDebug` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptSiteDebug::GetDocumentContextFromPosition](../../winscript/reference/iactivescriptsitedebug-getdocumentcontextfromposition.md)|Použít modul jazyka delegovat `IDebugCodeContext::GetSourceContext`.|  
|[IActiveScriptSiteDebug::GetApplication](../../winscript/reference/iactivescriptsitedebug-getapplication.md)|Vrátí objekt ladění aplikace související s touto lokalitou skriptu.|  
|[IActiveScriptSiteDebug::GetRootApplicationNode](../../winscript/reference/iactivescriptsitedebug-getrootapplicationnode.md)|Získá uzlu aplikace v rámci skriptu, které by se měl přidat dokumenty.|  
|[IActiveScriptSiteDebug::OnScriptErrorDebug](../../winscript/reference/iactivescriptsitedebug-onscripterrordebug.md)|Umožňuje inteligentního hostitele pro určení způsobu zpracování chyb za běhu.|