---
title: Idebugstackframesnifferex – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: 76f10d6bbb34c61e87a1be0f61dcd7db168274e7
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348487"
---
# <a name="idebugstackframesnifferex-interface"></a>IDebugStackFrameSnifferEx – rozhraní
Poskytuje způsob, jak vytvořit výčet logického zásobníku známé komponenta. Toto rozhraní implementují obvykle skriptovací stroje. Použití Správce ladění procesu toto rozhraní najít všechny rámce zásobníku přidružené k dané vlákno.  
  
> [!NOTE]
>  Toto rozhraní je volat z vlákna, které vás zajímají. Implementace rozhraní musí identifikovat aktuální vlákno a vrátí odpovídající enumerátor.  
  
 Kromě metod zděděných z `IDebugStackFrameSniffer`, `IDebugStackFrameSnifferEx` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugStackFrameSnifferEx::EnumStackFramesEx](../../winscript/reference/idebugstackframesnifferex-enumstackframesex.md)|Vrátí enumerátor rámce zásobníku pro aktuální vlákno.|