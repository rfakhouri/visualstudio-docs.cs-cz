---
title: Idebugdocumenthost – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentHost interface
ms.assetid: 2fed4220-b6a2-47c6-bf28-daad7dd5c42d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 46684bf2264813a8daaa466b98119496ba85d4b9
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346537"
---
# <a name="idebugdocumenthost-interface"></a>IDebugDocumentHost – rozhraní
Zpřístupňuje funkce specifické pro hostitele, jako je například syntaxe obarvení ladicímu programu. `IDebugDocumentHelper::SetDebugDocumentHost` Metoda má toto rozhraní jako argument.  
  
 Kromě metod zděděných z `IUnknown`, `IDebugDocumentHost` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugDocumentHost::GetDeferredText](../../winscript/reference/idebugdocumenthost-getdeferredtext.md)|Vrátí rozsah znaků, které byly přidány pomocí `IDebugDocumentHelper::AddDeferredText`, v původním dokumentu hostitele.|  
|[IDebugDocumentHost::GetScriptTextAttributes](../../winscript/reference/idebugdocumenthost-getscripttextattributes.md)|Vrátí text atributy pro blok textu dokumentu.|  
|[IDebugDocumentHost::OnCreateDocumentContext](../../winscript/reference/idebugdocumenthost-oncreatedocumentcontext.md)|Upozorňuje hostitele, že se vytváří nový kontext dokumentu a umožňuje hostiteli volitelně vrátit objekt, který řídí nový kontext.|  
|[IDebugDocumentHost::GetPathName](../../winscript/reference/idebugdocumenthost-getpathname.md)|Vrátí úplnou cestu (včetně názvu souboru) dokumentu zdrojový soubor.|  
|[IDebugDocumentHost::GetFileName](../../winscript/reference/idebugdocumenthost-getfilename.md)|Vrátí název dokumentu, bez informace o cestě.|  
|[IDebugDocumentHost::NotifyChanged](../../winscript/reference/idebugdocumenthost-notifychanged.md)|Upozorňuje hostitele, že zdrojový dokument se uložil a že jeho obsah je třeba aktualizovat.|