---
title: Iactivescriptsitedebug32 – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03f42217-303d-46e7-9792-61a5ab95252c
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
ms.openlocfilehash: e7937311e01274570e34bd639a0dc5f68206a3aa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62992445"
---
# <a name="iactivescriptsitedebug32-interface"></a>IActiveScriptSiteDebug32 Interface
Implementace hostitelů `IActiveScriptSiteDebug32` rozhraní provádět správu dokumentů a k účasti v ladění. `IActiveScriptSite` Objekt obvykle poskytuje implementaci `IActiveScriptSiteDebug32` rozhraní. Pokud to uděláte, zavolejte `IActiveScriptSite::QueryInterface` metodu k získání `IActiveScriptSiteDebug32` rozhraní.  
  
 Kromě metod zděděných z `IUnknown`, `IActiveScriptSiteDebug32` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptSiteDebug32::GetApplication](../../winscript/reference/iactivescriptsitedebug32-getapplication.md)|Vrátí objekt ladění aplikace související s touto lokalitou skriptu.|  
|[IActiveScriptSiteDebug32::GetDocumentContextFromPosition](../../winscript/reference/iactivescriptsitedebug32-getdocumentcontextfromposition.md)|Použít modul jazyka delegovat `IDebugCodeContext::GetSourceContext`.|