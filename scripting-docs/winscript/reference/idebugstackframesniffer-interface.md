---
title: Idebugstackframesniffer – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugStackFrameSniffer interface
ms.assetid: 5669598e-a6bd-4694-9cb2-bd908be72bed
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0e753261098133eb97f5010dcef5f602d283aac4
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58149481"
---
# <a name="idebugstackframesniffer-interface"></a>IDebugStackFrameSniffer – rozhraní
Poskytuje způsob, jak vytvořit výčet logického zásobníku známé komponenta. Toto rozhraní implementují obvykle skriptovací stroje. Použití Správce ladění procesu toto rozhraní najít všechny rámce zásobníku přidružené k dané vlákno.  
  
> [!NOTE]
>  Ladicí program volá tato rozhraní z vlákna, které vás zajímají. Skriptovací stroj musí identifikovat aktuální vlákno a vrátí odpovídající enumerátor.  
  
## <a name="methods"></a>Metody  
 Kromě metod zděděných z `IUnknown`, `IDebugStackFrameSniffer` rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugStackFrameSniffer::EnumStackFrames](../../winscript/reference/idebugstackframesniffer-enumstackframes.md)|Vrátí enumerátor rámce zásobníku pro aktuální vlákno.|