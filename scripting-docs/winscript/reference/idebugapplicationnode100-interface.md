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
ms.openlocfilehash: d8de6f57cabe808df1506870fe65da31ef74e644
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63436034"
---
# <a name="idebugapplicationnode100-interface"></a>IDebugApplicationNode100 – rozhraní
`IDebugApplicationNode100` Rozhraní rozšiřuje funkce [idebugapplicationnode – rozhraní](../../winscript/reference/idebugapplicationnode-interface.md). Instance tohoto rozhraní můžete získat pomocí volání QueryInterface u implementace [idebugapplicationnode – rozhraní](../../winscript/reference/idebugapplicationnode-interface.md).  
  
> [!IMPORTANT]
> Toto rozhraní je implementováno PDM v10.0 a větší. Nachází se v souboru activdbg100.h.  
  
## <a name="methods"></a>Metody  
 `IDebugApplicationNode100` Rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugApplicationNode100::GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md)|Získá textové dokumenty, které jsou skryty pomocí zadaného filtru.|  
|[IDebugApplicationNode100::QueryIsChildNode](../../winscript/reference/idebugapplicationnode100-queryischildnode.md)|Určuje, zda zadaný dokument patří do jedné z podřízených uzlů tohoto uzlu.|  
|[IDebugApplicationNode100::SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)|Nastaví filtr na konkrétním [idebugapplicationnodeevents – rozhraní](../../winscript/reference/idebugapplicationnodeevents-interface.md) implementace. Umožňuje skriptu ladicí programy k filtrování vygenerovaný kompilátorem podřízené uzly aplikace tak, aby PDM už bude odesílat události při vytvoření nebo odebrání uzlů. Ve výchozím nastavení se pošle všem uzlům.|