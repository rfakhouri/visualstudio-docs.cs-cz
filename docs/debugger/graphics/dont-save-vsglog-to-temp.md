---
title: DONT_SAVE_VSGLOG_TO_TEMP | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: f27ab0e6-9575-4ca0-9901-37d3e5c3a2f5
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b70ddf2933b8bd2d96db1636612cb35a6a759a1a
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31473803"
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