---
title: Iapplicationdebuggerui – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: f138492e5b0a465bb0f101c15457ed1021ab3d5a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62991097"
---
# <a name="iapplicationdebuggerui-interface"></a>IApplicationDebuggerUI – rozhraní
Implementováno ladicím programu integrovaného vývojového prostředí (IDE) (kromě `IApplicationDebugger`) pro externí komponenta poskytují větší kontrolu nad uživatelského rozhraní (UI) ladicího programu.  
  
 Kromě metod zděděných z `IUnknown`, `IApplicationDebuggerUI` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IApplicationDebuggerUI::BringDocumentToTop](../../winscript/reference/iapplicationdebuggerui-bringdocumenttotop.md)|Zobrazí se okno, obsahující zadanou ladění dokument nahoru v ladicím programu uživatelského rozhraní.|  
|[IApplicationDebuggerUI::BringDocumentContextToTop](../../winscript/reference/iapplicationdebuggerui-bringdocumentcontexttotop.md)|Zobrazí se okno obsahující daný dokument kontext do horní části v uživatelském rozhraní ladicího programu a posune okno kontextu.|