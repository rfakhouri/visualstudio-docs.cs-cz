---
title: -Out (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 891204811a0c27471e8ab4be315da14be4b80794
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="out-devenvexe"></a>/Out (devenv.exe)
Určuje soubor pro uložení a zobrazení chyb při spouštění, sestavení, znovu sestavit nebo nasazení řešení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv /out FileName  
```  
  
## <a name="arguments"></a>Arguments  
 `FileName`  
 Požadováno. Cesta a název souboru, který se zobrazí chyby při sestavování spustitelný soubor.  
  
## <a name="remarks"></a>Poznámky  
 Pokud je zadán název souboru, který ještě neexistuje, vytvoří se automaticky soubor. Pokud soubor již existuje, výsledky jsou připojena k existující obsah souboru.  
  
 Chyby sestavení příkazového řádku se zobrazí v **příkaz** okno a řešení Tvůrce zobrazení **výstup** okno. Tato možnost je užitečná, pokud běží bezobslužné sestavení a musí zobrazit výsledky.  
  
## <a name="example"></a>Příklad  
 Tento příklad spustí `MySolution` a zapíše chyby do souboru `MyErrorLog.txt`.  
  
```  
devenv /run "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /out "C:\MyErrorLog.txt"  
```  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)   
 [Nebo spusťte (devenv.exe)](../../ide/reference/run-devenv-exe.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ Nasadit (devenv.exe)](../../ide/reference/deploy-devenv-exe.md)