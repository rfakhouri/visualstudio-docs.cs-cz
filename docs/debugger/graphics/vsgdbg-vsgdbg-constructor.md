---
title: VsgDbg::VsgDbg (konstruktor) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 670651e6-5e79-4845-b0c2-671beb7055a8
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7231e0cc5c9d5946fabe504c16813ea47b24bdbc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="vsgdbgvsgdbg-constructor"></a>VsgDbg::VsgDbg (konstruktor)
Vytvoří instanci objektu `VsgDbg` třídy s nebo bez Příprava v aplikaci součást diagnostiky grafiky aktivně zaznamenání a zaznamenání grafických informací ve výchozím nastavení, na základě zadaného parametru logická hodnota.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
VsgDbg(  
  bDefaultInit  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `bDefaultInit`  
 `true`k určení, že je v aplikaci součást diagnostiky grafiky jako připravené k aktivně zachycení a zaznamenání grafických informací; `false` k určení, že aplikace nesmí připravte se na aktivním zachycení a zaznamenání grafických informací v tuto chvíli.  
  
## <a name="remarks"></a>Poznámky  
 Při volání konstruktoru s `bDefaultInit` nastavena na `true`, název souboru souboru protokolu grafika je dáno jak `DONT_SAVE_VSGLOG_TO_TEMP` a `VSG_DEFAULT_RUN_FILENAME` preprocesoru značky jsou definovány před `vsgcapture.h` je součástí vaší aplikace.  
  
 Při volání konstruktoru s `bDefaultInit` nastavena na `false`, v aplikaci součást diagnostiky grafiky mohly být připraveny aktivně zaznamenání a zaznamenání grafických informací později při volání `Init` funkce.  
  
## <a name="see-also"></a>Viz také  
 [VsgDbg:: ~ VsgDbg (destruktor)](vsgdbg-tilde-vsgdbg-destructor.md)   
 [Init –](init.md)   
 [DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)   
 [VSG_DEFAULT_RUN_FILENAME](vsg-default-run-filename.md)