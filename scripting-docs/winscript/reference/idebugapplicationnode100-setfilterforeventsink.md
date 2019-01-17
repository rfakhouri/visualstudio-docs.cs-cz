---
title: IDebugApplicationNode100::SetFilterForEventSink | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNode100::SetFilterForEventSink
ms.assetid: cfb34efe-c6e1-4692-8ffd-3ede3a24cd4b
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4b273b770a1d82edbf5bbbe26c0865060234b852
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54346485"
---
# <a name="idebugapplicationnode100setfilterforeventsink"></a>IDebugApplicationNode100::SetFilterForEventSink
Nastaví filtr na konkrétním [idebugapplicationnodeevents – rozhraní](../../winscript/reference/idebugapplicationnodeevents-interface.md) implementace. Umožňuje skriptu ladicí programy k filtrování vygenerovaný kompilátorem podřízené uzly aplikace tak, aby PDM už bude odesílat události, kdy tyto vytvořené nebo odebrat. Ve výchozím nastavení se pošle všem uzlům.  
  
> [!IMPORTANT]
>  [Idebugapplicationnode100 – rozhraní](../../winscript/reference/idebugapplicationnode100-interface.md) je implementováno pomocí PDM v10.0 a větší. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT SetFilterForEventSink(        [in] DWORD dwCookie,        [in] APPLICATION_NODE_EVENT_FILTER filter        );  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwCookie`  
 Soubor cookie filtru.  
  
 `filter`  
 Filtr.  
  
## <a name="see-also"></a>Viz také  
 [IDebugApplicationNode100 – rozhraní](../../winscript/reference/idebugapplicationnode100-interface.md)