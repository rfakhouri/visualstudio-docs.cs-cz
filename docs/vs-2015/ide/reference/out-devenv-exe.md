---
title: -Out (devenv.exe) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors [Visual Studio], builds
- Devenv, /out switch
- builds [Visual Studio], logs
- error logs [Visual Studio], command-line build errors
- error logs [Visual Studio]
- /out Devenv switch
- out Devenv switch
- builds [Visual Studio], errors
- output files, build errors
ms.assetid: 9002d8c2-36d4-451c-b489-8f01932f31f7
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4edcdf6da73c3f4c4ee9d221d7bbaef8e520c5e3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670752"
---
# <a name="out-devenvexe"></a>/Out (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [-Out (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/out-devenv-exe).  
  
  
Určuje soubor k uložení a zobrazení chyb při spuštění, sestavování, znovu sestavit nebo nasadit řešení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv /out FileName  
```  
  
## <a name="arguments"></a>Arguments  
 `FileName`  
 Požadováno. Cesta a název souboru, který se zobrazí chyby při vytváření spustitelného souboru.  
  
## <a name="remarks"></a>Poznámky  
 Pokud je zadaný název souboru, který neexistuje, vytvoří se soubor automaticky. Pokud soubor již existuje, výsledky jsou připojena k existující obsah souboru.  
  
 Chyby sestavení příkazového řádku se zobrazují v **příkaz** okno a Tvůrce řešení zobrazení **výstup** okna. Tato možnost je užitečná, pokud jsou spuštěny bezobslužném sestavování a potřebujete pro zobrazení výsledků.  
  
## <a name="example"></a>Příklad  
 Tento příklad se spouští `MySolution` a zapíše chyby do souboru `MyErrorLog.txt`.  
  
```  
devenv /run "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /out "C:\MyErrorLog.txt"  
```  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)   
 [Nebo spuštění (devenv.exe)](../../ide/reference/run-devenv-exe.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ Nasazení (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)



