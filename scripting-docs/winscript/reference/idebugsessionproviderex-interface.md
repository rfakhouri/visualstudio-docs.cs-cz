---
title: Idebugsessionproviderex – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 26c5da2d-8c93-4d2b-94d2-97aaa377dcfe
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c9bf341adeaeb17c8986b1b30b12f58113aef562
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62978993"
---
# <a name="idebugsessionproviderex-interface"></a>IDebugSessionProviderEx – rozhraní
Primární rozhraní poskytnuté ladicím programu integrovaného vývojového prostředí pro povolení ladění iniciované hostitele a jazyk. Zjistí ladicí relace pro běžící aplikaci. Toto rozhraní je implementováno ladění správcem počítače.  
  
 Kromě metod zděděných z `IUnknown`, `IDebugSessionProviderEx` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugSessionProviderEx:CanJITDebug](../../winscript/reference/idebugsessionproviderex-canjitdebug.md)|Určuje, zda ladění JIT je možné pomocí zadané aplikace.|  
|[IDebugSessionProviderEx:StartDebugSession](../../winscript/reference/idebugsessionproviderex-startdebugsession.md)|Spustí relaci ladění pomocí zadané aplikace.|