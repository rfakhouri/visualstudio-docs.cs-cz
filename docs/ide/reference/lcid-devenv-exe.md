---
title: -LCID (devenv.exe) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- language default
- locale IDs, setting for IDE
- Devenv, /LCID switch
- locale IDs
- /l Devenv switch
- LCID devenv switch
- /lcid Devenv switch
ms.assetid: 3a3f4e70-ea66-4351-9d62-acb1dec30e8e
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: bdc04655ccfc8ca5f6c1e45e4378f15221b99f4c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="lcid-devenvexe"></a>/LCID (devenv.exe)
Nastaví výchozí jazyk používaný pro text, měny a dalších hodnot v rámci integrované vývojové prostředí (IDE).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv {/LCID|/l} LocaleID  
```  
  
## <a name="arguments"></a>Arguments  
 `LocaleID`  
 Požadováno. LCID (ID národního prostředí) jazyk, který zadáte.  
  
## <a name="remarks"></a>Poznámky  
 Načte IDE a nastaví výchozí přirozeného jazyka pro prostředí. Tato změna se mezi relacemi trvalé a odrážejí na **mezinárodní nastavení** podokně **prostředí** možnosti v **možnosti** dialogového okna v prostředí IDE.  
  
 Pokud zadaný jazyk není k dispozici v systému uživatele, přepínač LCID je ignorován.  
  
 Následující tabulka uvádí identifikátor LCID jazyky nepodporuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
|Jazyk|LCID|  
|--------------|----------|  
|Čínština (zjednodušená)|2052|  
|Čínština (tradiční)|1028|  
|Angličtina|1033|  
|Francouzština|1036|  
|Němčina|1031|  
|Italština|1040|  
|Japonština|1041|  
|Korejština|1042|  
|Španělština|3082|  
  
## <a name="example"></a>Příklad  
 Tento příklad načte IDE s řetězci anglické prostředky.  
  
```  
devenv /LCID 1033  
```  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)   
 [Mezinárodní nastavení, prostředí, dialogové okno Možnosti](../../ide/reference/international-settings-environment-options-dialog-box.md)   
 [Přizpůsobení rozložení oken](../../ide/customizing-window-layouts-in-visual-studio.md)