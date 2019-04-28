---
title: Idebugdocumenthelper – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentHelper interface
ms.assetid: b652a31e-b87b-45f1-b586-94f2b6e822db
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7322ea5e2026ff3f4491ed1106dceb97a5f11c73
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63000896"
---
# <a name="idebugdocumenthelper-interface"></a>IDebugDocumentHelper – rozhraní
Poskytnout implementace pro mnoho rozhraní nutná pro inteligentní hostování, jako `IDebugDocument`, `IDebugDocumentContext`, `IDebugDocumentProvider`, `IDebugDocumentText`, a `IDebugDocumentTextEvents` rozhraní.  
  
 Kromě metod zděděných z `IUnknown`, `IDebugDocumentHelper` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugDocumentHelper::Init](../../winscript/reference/idebugdocumenthelper-init.md)|Inicializuje dokumentu nápovědu ladicího programu s názvem a počáteční atributy.|  
|[IDebugDocumentHelper::Attach](../../winscript/reference/idebugdocumenthelper-attach.md)|Tento dokument se přidá do stromu dokumentu.|  
|[IDebugDocumentHelper::Detach](../../winscript/reference/idebugdocumenthelper-detach.md)|Tento dokument se odebere ze stromu dokumentu.|  
|[IDebugDocumentHelper::AddUnicodeText](../../winscript/reference/idebugdocumenthelper-addunicodetext.md)|Přidá řetězec znaků Unicode pro ukončení tohoto dokumentu.|  
|[IDebugDocumentHelper::AddDBCSText](../../winscript/reference/idebugdocumenthelper-adddbcstext.md)|Připojí znaky DBCS řetězec do konce tohoto dokumentu.|  
|[IDebugDocumentHelper::SetDebugDocumentHost](../../winscript/reference/idebugdocumenthelper-setdebugdocumenthost.md)|Nastaví `IDebugDocumentHost` pro tento dokument.|  
|[IDebugDocumentHelper::AddDeferredText](../../winscript/reference/idebugdocumenthelper-adddeferredtext.md)|Pomocná rutina upozorní, že daný text je k dispozici, ale neposkytuje znaky.|  
|[IDebugDocumentHelper::DefineScriptBlock](../../winscript/reference/idebugdocumenthelper-definescriptblock.md)|Označuje, že do pomocné rutiny, která konkrétní rozsah znaků je blok skriptu, který zpracovává modul skriptu.|  
|[IDebugDocumentHelper::SetDefaultTextAttr](../../winscript/reference/idebugdocumenthelper-setdefaulttextattr.md)|Nastaví výchozí atributy určený pro text, který není v bloku skriptu.|  
|[IDebugDocumentHelper::SetTextAttributes](../../winscript/reference/idebugdocumenthelper-settextattributes.md)|Nastaví atributy na oblast textu.|  
|[IDebugDocumentHelper::SetLongName](../../winscript/reference/idebugdocumenthelper-setlongname.md)|Nastaví dlouhý název dokumentu.|  
|[IDebugDocumentHelper::SetShortName](../../winscript/reference/idebugdocumenthelper-setshortname.md)|Nastaví krátký název dokumentu.|  
|[IDebugDocumentHelper::SetDocumentAttr](../../winscript/reference/idebugdocumenthelper-setdocumentattr.md)|Nastaví vlastnosti pro tento dokument.|  
|[IDebugDocumentHelper::GetDebugApplicationNode](../../winscript/reference/idebugdocumenthelper-getdebugapplicationnode.md)|Vrátí uzel ladění aplikace odpovídající do tohoto dokumentu.|  
|[IDebugDocumentHelper::GetScriptBlockInfo](../../winscript/reference/idebugdocumenthelper-getscriptblockinfo.md)|Načte rozsah znaků a skriptovací stroj odpovídající blok skriptu.|  
|[IDebugDocumentHelper::CreateDebugDocumentContext](../../winscript/reference/idebugdocumenthelper-createdebugdocumentcontext.md)|Vytvoří nový kontext dokumentu ladění.|  
|[IDebugDocumentHelper::BringDocumentToTop](../../winscript/reference/idebugdocumenthelper-bringdocumenttotop.md)|Přináší tento dokument nahoru v ladicím programu uživatelského rozhraní.|  
|[IDebugDocumentHelper::BringDocumentContextToTop](../../winscript/reference/idebugdocumenthelper-bringdocumentcontexttotop.md)|Kontext tohoto dokumentu přináší do horní části v uživatelském rozhraní ladicího programu.|