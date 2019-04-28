---
title: Idebugstackframesnifferex – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugStackFrameSnifferEx interface
ms.assetid: fd6cf744-dee7-45f2-9a90-355b90372923
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dccd9210908922951c20378868c33b3389cbed4f
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63432241"
---
# <a name="idebugstackframesnifferex-interface"></a>IDebugStackFrameSnifferEx – rozhraní
Poskytuje způsob, jak vytvořit výčet logického zásobníku známé komponenta. Toto rozhraní implementují obvykle skriptovací stroje. Použití Správce ladění procesu toto rozhraní najít všechny rámce zásobníku přidružené k dané vlákno.  
  
> [!NOTE]
> Toto rozhraní je volat z vlákna, které vás zajímají. Implementace rozhraní musí identifikovat aktuální vlákno a vrátí odpovídající enumerátor.  
  
 Kromě metod zděděných z `IDebugStackFrameSniffer`, `IDebugStackFrameSnifferEx` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugStackFrameSnifferEx::EnumStackFramesEx](../../winscript/reference/idebugstackframesnifferex-enumstackframesex.md)|Vrátí enumerátor rámce zásobníku pro aktuální vlákno.|