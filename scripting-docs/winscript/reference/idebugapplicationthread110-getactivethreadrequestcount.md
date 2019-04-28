---
title: IDebugApplicationThread110::GetActiveThreadRequestCount | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThread110::GetActiveThreadRequestCount
ms.assetid: 025d2072-1d7f-4448-8aa3-38a014313570
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3df2f0c44e42cf9e2c2aa846db4b88821fd73996
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440569"
---
# <a name="idebugapplicationthread110getactivethreadrequestcount"></a>IDebugApplicationThread110::GetActiveThreadRequestCount
Vrátí počet vláken požadavků z vlákna PDM přepínání mechanismy, které jsou právě zpracovávána. Toto číslo je obvykle 0 nebo 1. Nicméně číslo může být vyšší, pokud jedno vlákno volání spustil zpracování, ale které jsou aktivuje synchronní volání z vlákna, nebo v opačném případě se pozastaví vlákna a umožňuje příchozí volání na opětovné zpracování (například, že se budou spouštět [ Iremotedebugapplicationevents – rozhraní](../../winscript/reference/iremotedebugapplicationevents-interface.md) událost, která je vydané pro vlákno ladicího programu).  
  
> [!IMPORTANT]
> [Idebugapplicationthread110 – rozhraní](../../winscript/reference/idebugapplicationthread110-interface.md) je implementováno komponentou Pdm verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetActiveThreadRequestCount([out, annotation("_Out_")] UINT * puiThreadRequests);  
```  
  
#### <a name="parameters"></a>Parametry  
 `puiThreadRequests`  
 [out] Počet požadavků vlákna.  
  
## <a name="see-also"></a>Viz také  
 [IDebugApplicationThread110 – rozhraní](../../winscript/reference/idebugapplicationthread110-interface.md)