---
title: VSG_DEFAULT_RUN_FILENAME | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea549d2f-c857-458c-93c7-bc5a2d11d15d
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f7fe31b96911329089174772094784c0d0f3371c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="vsgdefaultrunfilename"></a>VSG_DEFAULT_RUN_FILENAME
Definuje výchozí název souboru grafického souboru protokolu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
#define VSG_DEFAULT_FILENAME filename  
```  
  
#### <a name="parameters"></a>Parametry  
 `filename`  
 Název souboru musí být zadána ve výchozím nastavení do souboru protokolu grafiky při zachycenou grafických informací prostřednictvím kódu programu.  
  
## <a name="value"></a>Hodnota  
 Řetězcový literál, který představuje název souboru grafiky souboru protokolu. Ve výchozím nastavení, L"default.vsglog".  
  
```C++  
#define VSG_DEFAULT_FILENAME L"default.vsglog"  
```  
  
## <a name="remarks"></a>Poznámky  
 Pokud na symbol preprocesoru `DONT_SAVE_VSGLOG_TO_TEMP` je definován, pak název souboru je vůči aktuálnímu adresáři zaznamenané aplikace, nebo je absolutní cestu; jinak, je relativní vzhledem k adresáři dočasné soubory uživatele a nemůže být absolutní cesta.  
  
 Chcete-li změnit název definované souboru, je třeba znovu definovat ji předtím, než zahrnete `vsgcapture.h` v programu.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak změnit výchozí název souboru zachytávání:  
  
```C++  
// Redefine the default capture filename before including vsgcapture.h  
#define VSG_DEFAULT_FILENAME L"capture.vsglog"  
  
#include <vsgcapture.h>  
```  
  
## <a name="see-also"></a>Viz také  
 [DONT_SAVE_VSGLOG_TO_TEMP](dont-save-vsglog-to-temp.md)