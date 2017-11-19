---
title: DONT_SAVE_VSGLOG_TO_TEMP | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f27ab0e6-9575-4ca0-9901-37d3e5c3a2f5
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 264f67eb9a1fc7f8af739d7eea329de05230c7a8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="dontsavevsglogtotemp"></a>DONT_SAVE_VSGLOG_TO_TEMP
Podle jeho přítomnosti definuje, zda soubor protokolu grafika je uložena do adresáře uživatele dočasné soubory.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
#define DONT_SAVE_VSGLOG_TO_TEMP  
```  
  
## <a name="value"></a>Hodnota  
 Preprocesor – symbol, který podle přítomnosti nebo absenci Určuje, zda soubor protokolu grafika je uložena do adresáře dočasné soubory uživatele. Pokud je definována tento symbol, pak je název souboru definované `VSG_DEFAULT_RUN_FILENAME` je vůči aktuálnímu adresáři zaznamenané aplikace, nebo absolutní cesta; jinak, název souboru definované `VSG_DEFAULT_RUN_FILENAME` je relativní vzhledem k adresáři dočasné soubory uživatele a nemůže být absolutní cesta.  
  
## <a name="remarks"></a>Poznámky  
 V závislosti na oprávnění uživatele nemusí být možné uložit do libovolného umístění souboru protokolu grafiky. Doporučujeme vám, že dáváte přednost uložit grafických protokolů do složky dočasné soubory uživatele, nebo v jiném umístění známé funkční, pokud si nejste jistí, jestli by zvoleného umístění, je možné zapsat do uživatelem.  
  
 Abyste zabránili soubor protokolu grafiky ukládají do adresáře s dočasnými soubory, musí být definován `DONT_SAVE_VSGLOG_TO_TEMP` předtím, než zahrnete `vsgcapture.h`.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak uložit soubor protokolu grafiky do absolutní cesta na hostitelském počítači.  
  
```  
// Define DONT_SAVE_VSGLOG_TO_TEMP and VSG_DEFAULT_RUN_FILENAME before including vsgcapture.h  
#define DONT_SAVE_VSGLOG_TO_TEMP  
#define VSG_DEFAULT_RUN_FILENAME L"C:\\Graphics Diagnostics Captures\\default.vsglog"  
  
#include <vsgcapture.h>  
  
```  
  
## <a name="see-also"></a>Viz také  
 [VSG_DEFAULT_RUN_FILENAME](vsg-default-run-filename.md)