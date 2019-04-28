---
title: Iactivescripterrordebug – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IActiveScriptErrorDebug interface
ms.assetid: e5d50427-c033-4138-ac6e-3b2dfb3b750a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 936770859d3bdfe81c84245d32ae63346b142a01
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63009529"
---
# <a name="iactivescripterrordebug-interface"></a>IActiveScriptErrorDebug – rozhraní
Poskytuje informace o kontextu dokumentu za kompilace chyb a výjimek za běhu. `IActiveScriptError::QueryInterface` Podporuje metodu `IActiveScriptErrorDebug` rozhraní.  
  
 Kromě metod zděděných z `IActiveScriptError`, `IActiveScriptErrorDebug` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IActiveScriptErrorDebug::GetDocumentContext](../../winscript/reference/iactivescripterrordebug-getdocumentcontext.md)|Poskytuje kontext dokumentu pro tuto chybu.|  
|[IActiveScriptErrorDebug::GetStackFrame](../../winscript/reference/iactivescripterrordebug-getstackframe.md)|Poskytuje rámce zásobníku, který je v platnosti pro chyby za běhu.|