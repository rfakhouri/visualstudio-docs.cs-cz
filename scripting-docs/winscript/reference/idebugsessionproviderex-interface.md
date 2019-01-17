---
title: Idebugsessionproviderex – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 26c5da2d-8c93-4d2b-94d2-97aaa377dcfe
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fae1cf673f47d3be586f83320b2d2c38c817e2cf
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349215"
---
# <a name="idebugsessionproviderex-interface"></a>IDebugSessionProviderEx – rozhraní
Primární rozhraní poskytnuté ladicím programu integrovaného vývojového prostředí pro povolení ladění iniciované hostitele a jazyk. Zjistí ladicí relace pro běžící aplikaci. Toto rozhraní je implementováno ladění správcem počítače.  
  
 Kromě metod zděděných z `IUnknown`, `IDebugSessionProviderEx` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugSessionProviderEx:CanJITDebug](../../winscript/reference/idebugsessionproviderex-canjitdebug.md)|Určuje, zda ladění JIT je možné pomocí zadané aplikace.|  
|[IDebugSessionProviderEx:StartDebugSession](../../winscript/reference/idebugsessionproviderex-startdebugsession.md)|Spustí relaci ladění pomocí zadané aplikace.|