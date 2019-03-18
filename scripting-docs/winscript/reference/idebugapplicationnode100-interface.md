---
title: Idebugapplicationnode100 – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNode100 Interface
ms.assetid: 43966d4e-5f89-4a04-a08d-782347d00c2d
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f380245422047142b3f06757f6c1057302dd5d26
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58146042"
---
# <a name="idebugapplicationnode100-interface"></a>IDebugApplicationNode100 – rozhraní
`IDebugApplicationNode100` Rozhraní rozšiřuje funkce [idebugapplicationnode – rozhraní](../../winscript/reference/idebugapplicationnode-interface.md). Instance tohoto rozhraní můžete získat pomocí volání QueryInterface u implementace [idebugapplicationnode – rozhraní](../../winscript/reference/idebugapplicationnode-interface.md).  
  
> [!IMPORTANT]
>  Toto rozhraní je implementováno PDM v10.0 a větší. Nachází se v souboru activdbg100.h.  
  
## <a name="methods"></a>Metody  
 `IDebugApplicationNode100` Rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugApplicationNode100::GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md)|Získá textové dokumenty, které jsou skryty pomocí zadaného filtru.|  
|[IDebugApplicationNode100::QueryIsChildNode](../../winscript/reference/idebugapplicationnode100-queryischildnode.md)|Určuje, zda zadaný dokument patří do jedné z podřízených uzlů tohoto uzlu.|  
|[IDebugApplicationNode100::SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)|Nastaví filtr na konkrétním [idebugapplicationnodeevents – rozhraní](../../winscript/reference/idebugapplicationnodeevents-interface.md) implementace. Umožňuje skriptu ladicí programy k filtrování vygenerovaný kompilátorem podřízené uzly aplikace tak, aby PDM už bude odesílat události při vytvoření nebo odebrání uzlů. Ve výchozím nastavení se pošle všem uzlům.|