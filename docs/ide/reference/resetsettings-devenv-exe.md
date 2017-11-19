---
title: "-Resetsettings – (devenv.exe) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /ResetSettings switch
- ResetSettings switch
- /ResetSettings Devenv switch
ms.assetid: 1d41021c-6f58-4bd5-b122-d1c995812192
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c4f65035e1030406ced4c5f0c98ebd1d1e66c5d2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="resetsettings-devenvexe"></a>/ResetSettings (devenv.exe)
Obnoví [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] výchozí nastavení a automaticky spouští [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE. Volitelně obnoví nastavení na soubor zadaný .vssettings.  
  
 Určuje výchozí nastavení profilu, který byl vybrán při [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] byl nejprve spustit.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Devenv /ResetSettings SettingsFile  
```  
  
## <a name="arguments"></a>Arguments  
 `SettingsFile`  
 Úplná cesta a název souboru .vssettings použít [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Chcete-li obnovit profil obecná nastavení pro vývoj, použijte `General`.  
  
## <a name="remarks"></a>Poznámky  
 Pokud žádné `SettingsFile` je zadán, zobrazí se výzva k výběru kolekce výchozí nastavení při dalším spuštění [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="example"></a>Příklad  
 Následující příkazový řádek aplikuje nastavení uložené v souboru `MySettings.vssettings`.  
  
```  
Devenv.exe /ResetSettings "C:\My Files\MySettings.vssettings"  
```  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení sady Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)   
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)