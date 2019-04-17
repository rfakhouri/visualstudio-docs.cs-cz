---
title: -ResetSettings (devenv.exe) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /ResetSettings switch
- ResetSettings switch
- /ResetSettings Devenv switch
ms.assetid: 1d41021c-6f58-4bd5-b122-d1c995812192
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: a81c0082bc9b8e31c6c64ff1785f5f380709f3b5
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59650964"
---
# <a name="resetsettings-devenvexe"></a>/ResetSettings (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Obnoví [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] výchozí nastavení a automaticky spouští [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] integrovaného vývojového prostředí. Volitelně obnoví nastavení zadaného souboru .vssettings.  
  
 Výchozí nastavení jsou určena podle profilu, který byl vybrán při [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] prvním spuštění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Devenv /ResetSettings SettingsFile  
```  
  
## <a name="arguments"></a>Arguments  
 `SettingsFile`  
 Úplná cesta a název souboru .vssettings vyrovnat [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
 K obnovení profilu Obecné vývojové nastavení použijte `General`.  
  
## <a name="remarks"></a>Poznámky  
 Pokud ne `SettingsFile` není zadán, zobrazí se výzva k výběru výchozí kolekce nastavení při příštím spuštění [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="example"></a>Příklad  
 Následující příkazový řádek použije nastavení uložená v souboru `MySettings.vssettings`.  
  
```  
Devenv.exe /ResetSettings "C:\My Files\MySettings.vssettings"  
```  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)
