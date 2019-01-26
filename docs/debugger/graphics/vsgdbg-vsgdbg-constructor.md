---
title: VsgDbg::VsgDbg (konstruktor) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 670651e6-5e79-4845-b0c2-671beb7055a8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b4c4c987bd0f44f6b8a4bad945d249aaf832fc57
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55035273"
---
# <a name="vsgdbgvsgdbg-constructor"></a>VsgDbg::VsgDbg (konstruktor)
Vytvoří instanci objektu `VsgDbg` třídy s nebo bez přípravy komponentu v aplikaci diagnostiky grafiky k aktivně zachycení a zaznamenání grafických informací ve výchozím nastavení, založené na zadaný parametr logické hodnoty.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
VsgDbg(  
  bDefaultInit  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `bDefaultInit`  
 `true` Chcete-li určit, že má být připraveni aktivně zachycení a zaznamenání informací grafiky; součást diagnostiky grafiky v aplikaci `false` k určení, že aplikace by neměly být připravovány aktivně zachytit a zaznamenání grafických informací v tuto chvíli.  
  
## <a name="remarks"></a>Poznámky  
 Pokud je konstruktor volán s `bDefaultInit` nastavena na `true`, soubor název souboru protokolu grafiky je určen jak `DONT_SAVE_VSGLOG_TO_TEMP` a `VSG_DEFAULT_RUN_FILENAME` symboly preprocesoru jsou definovány před `vsgcapture.h` je součástí vaší aplikace.  
  
 Pokud je konstruktor volán s `bDefaultInit` nastavena na `false`, součást diagnostiky grafiky v aplikaci může být připraveni aktivně zachycení a zaznamenání informací grafiky později pomocí volání `Init` funkce.  
  
## <a name="see-also"></a>Viz také  
 [VsgDbg::~VsgDbg (Destructor)](vsgdbg-tilde-vsgdbg-destructor.md)   
 [Inicializace](init.md)   
 [DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)   
 [VSG_DEFAULT_RUN_FILENAME](vsg-default-run-filename.md)