---
title: -LCID (devenv.exe) | Dokumentace Microsoftu
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
- language default
- locale IDs, setting for IDE
- Devenv, /LCID switch
- locale IDs
- /l Devenv switch
- LCID devenv switch
- /lcid Devenv switch
ms.assetid: 3a3f4e70-ea66-4351-9d62-acb1dec30e8e
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e84d02cef1c1a22fdcbfc6396037e54e2b8981b4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42671858"
---
# <a name="lcid-devenvexe"></a>/LCID (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [- LCID (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/lcid-devenv-exe).  
  
  
Nastaví výchozí jazyk používaný pro text, měny a jiné hodnoty v rámci integrovaného vývojového prostředí (IDE).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv {/LCID|/l} LocaleID  
```  
  
## <a name="arguments"></a>Arguments  
 `LocaleID`  
 Požadováno. Identifikátor LCID (ID národního prostředí) jazyka, který zadáte.  
  
## <a name="remarks"></a>Poznámky  
 Načte integrovaného vývojového prostředí a nastaví výchozí přirozeného jazyka pro prostředí. Tato změna je trvalá mezi relacemi a projeví na **mezinárodní nastavení** podokně **prostředí** možnosti **možnosti** dialogového okna v rozhraní IDE.  
  
 Pokud zadaný jazyk není k dispozici v systému uživatele, přepínač/LCID je ignorován.  
  
 V následující tabulce jsou uvedeny LCID jazyky podporovanými [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
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
 Tento příklad načte integrované vývojové prostředí s anglickou prostředky řetězců.  
  
```  
devenv /LCID 1033  
```  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)   
 [Mezinárodní nastavení, prostředí, dialogové okno Možnosti](../../ide/reference/international-settings-environment-options-dialog-box.md)   
 [Přizpůsobení rozložení oken](../../ide/customizing-window-layouts-in-visual-studio.md)



