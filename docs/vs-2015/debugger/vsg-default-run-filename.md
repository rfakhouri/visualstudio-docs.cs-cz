---
title: VSG_DEFAULT_RUN_FILENAME | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea549d2f-c857-458c-93c7-bc5a2d11d15d
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d82052c48444c8c22f205326cfb5ce614ac36aa7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628853"
---
# <a name="vsgdefaultrunfilename"></a>VSG_DEFAULT_RUN_FILENAME
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [VSG_DEFAULT_RUN_FILENAME](https://docs.microsoft.com/visualstudio/debugger/graphics/vsg-default-run-filename).  
  
Definuje výchozí název souboru pro soubor protokolu grafiky.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
#define VSG_DEFAULT_FILENAME filename  
```  
  
#### <a name="parameters"></a>Parametry  
 `filename`  
 Název souboru zadaný ve výchozím nastavení pro soubor protokolu grafiky při informací grafiky je zachycena prostřednictvím kódu programu.  
  
## <a name="value"></a>Hodnota  
 Řetězcový literál, který představuje název souboru grafiky souboru protokolu. Ve výchozím nastavení, L"default.vsglog".  
  
```cpp  
#define VSG_DEFAULT_FILENAME L"default.vsglog"  
```  
  
## <a name="remarks"></a>Poznámky  
 Pokud se symbol preprocesoru `DONT_SAVE_VSGLOG_TO_TEMP` je definován, pak název souboru je relativní vzhledem k aktuální adresář zachycené aplikace, nebo je absolutní cesta; v opačném případě je relativní k adresáři dočasné soubory uživatele a nemůže být absolutní cesta.  
  
 Chcete-li změnit název definovaný souboru, je třeba znovu definovat ho předtím, než zahrnete `vsgcapture.h` ve svém programu.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak změnit výchozí název souboru zachytávací soubor:  
  
```cpp  
// Redefine the default capture filename before including vsgcapture.h  
#define VSG_DEFAULT_FILENAME L"capture.vsglog"  
  
#include <vsgcapture.h>  
```  
  
## <a name="see-also"></a>Viz také  
 [DONT_SAVE_VSGLOG_TO_TEMP](../debugger/dont-save-vsglog-to-temp.md)



