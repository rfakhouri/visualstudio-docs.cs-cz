---
title: Iapplicationdebuggerui – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IApplicationDebuggerUI interface
ms.assetid: b8828817-ca24-4012-802c-7dcaeea65dc8
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e3c5f9e4cabeb4fba31bb039a7cf673ca1759860
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348903"
---
# <a name="iapplicationdebuggerui-interface"></a>IApplicationDebuggerUI – rozhraní
Implementováno ladicím programu integrovaného vývojového prostředí (IDE) (kromě `IApplicationDebugger`) pro externí komponenta poskytují větší kontrolu nad uživatelského rozhraní (UI) ladicího programu.  
  
 Kromě metod zděděných z `IUnknown`, `IApplicationDebuggerUI` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IApplicationDebuggerUI::BringDocumentToTop](../../winscript/reference/iapplicationdebuggerui-bringdocumenttotop.md)|Zobrazí se okno, obsahující zadanou ladění dokument nahoru v ladicím programu uživatelského rozhraní.|  
|[IApplicationDebuggerUI::BringDocumentContextToTop](../../winscript/reference/iapplicationdebuggerui-bringdocumentcontexttotop.md)|Zobrazí se okno obsahující daný dokument kontext do horní části v uživatelském rozhraní ladicího programu a posune okno kontextu.|