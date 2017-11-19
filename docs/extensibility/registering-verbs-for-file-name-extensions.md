---
title: "Registrace příkazy pro přípony názvu souboru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: verbs, registering
ms.assetid: 81a58e40-7cd0-4ef4-a475-c4e1e84d6e06
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8f430486c613e6281404110d4441d2a3d2100534
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="registering-verbs-for-file-name-extensions"></a>Registrace příkazy pro přípony názvu souboru
Přidružení příponu názvu souboru pomocí aplikace má obvykle upřednostňovat, která nastane po dvojitém kliknutí uživatele. Upřednostňovaná tato akce je spojena se slovesem, například otevřená, který odpovídá akci.  
  
 Můžete zaregistrovat příkazy, které jsou přidruženy programový identifikátor (ProgID) pro rozšíření pomocí klávesy prostředí umístěný na HKEY_CLASSES_ROOT\\*progid*\shell. Další informace najdete v tématu [typy souborů](http://msdn.microsoft.com/library/windows/desktop/cc144148\(v=vs.85\).aspx).  
  
## <a name="registering-standard-verbs"></a>Registrace standardní příkazy  
 Operační systém rozpozná standardní akce:  
  
-   Otevřít  
  
-   Upravit  
  
-   Přehrávání  
  
-   Tisk  
  
-   Náhled  
  
 Pokud je to možné, zaregistrujte standardní operaci. Nejběžnější volba je příkaz Otevřít. Použijte příkaz upravit pouze v případě, že je zrušte rozdíl mezi otevření souboru a úpravy souboru. Například otevřete soubor HTM zobrazí se v prohlížeči, zatímco úpravy něho soubor .htm spustí HTML editor. Standardní příkazy lokalizace v národním prostředí operačního systému.  
  
> [!NOTE]
>  Při registraci standardní příkazy, nenastavujte výchozí hodnota pro klíč otevřete. Výchozí hodnota obsahuje řetězec zobrazení v nabídce. Operační systém poskytuje tento řetězec pro standardní příkazy.  
  
 Soubory projektu by měla zaregistrovat spustit novou instanci třídy [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] když uživatel otevře soubor. Následující příklad ilustruje standardní příkaz registrace pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] projektu.  
  
```  
[HKEY_CLASSES_ROOT\.csproj]  
@="VisualStudio.csproj.8.0"  
  
[HKEY_CLASSES_ROOT\.csproj\OpenWithList]  
[HKEY_CLASSES_ROOT\.csproj\OpenWithList\VSLauncher.exe]  
@=""  
  
[HKEY_CLASSES_ROOT\.csproj\OpenWithProgids]  
"VisualStudio.csproj.8.0"=""  
  
[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe]  
[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe\Shell]  
[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe\Shell\Open]  
[HKEY_CLASSES_ROOT\Applications\VSLauncher.exe\Shell\Open\Command]  
@="C:\\Program Files\\Common Files\\Microsoft Shared\\MSEnv\\VSLauncher.exe \"%1\""  
  
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0]  
@="C# Project file"  
  
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\DefaultIcon]  
@="C:\\VisualStudioPath\\VC#\\VCSPackages\\csproj.dll,0"  
  
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\shell]  
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\shell\Open]  
[HKEY_CLASSES_ROOT\VisualStudio.csproj.8.0\shell\Open\Command]  
@="\"C:\\Program Files\\Common Files\\Microsoft Shared\\MSEnv\\VSLauncher.exe\" \"%1\""  
```  
  
 K otevření souboru v existující instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], zaregistrujte DDEEXEC klíč. Následující příklad ilustruje standardní příkaz registrace pro [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] soubor cs.  
  
```  
[HKEY_CLASSES_ROOT\.cs]  
@="VisualStudio.cs.8.0"  
  
[HKEY_CLASSES_ROOT\.cs\OpenWithList]  
[HKEY_CLASSES_ROOT\.cs\OpenWithList\devenv.exe]  
@=""  
  
[HKEY_CLASSES_ROOT\.cs\OpenWithProgids]  
"VisualStudio.cs.8.0"=""  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0]  
@="C# Source file"  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\DefaultIcon]  
@="C:\\VisualStudioPath\\VC#\\VCSPackages\\csproj.dll,1"  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell]  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open]  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\Command]  
@="\"C:\\VisualStudioPath\\Common7\\IDE\\devenv.exe\" /dde \"%1\""  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\ddeexec]  
@="Open(\"%1\")"  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\ddeexec\Application]  
@="VisualStudio.8.0"  
  
[HKEY_CLASSES_ROOT\VisualStudio.cs.8.0\shell\Open\ddeexec\Topic]  
@="system"  
```  
  
## <a name="setting-the-default-verb"></a>Příkaz výchozí nastavení  
 Příkaz výchozí je akce, která se spustí, až uživatel poklikáním soubor v Průzkumníku Windows. Příkaz výchozí je příkaz jako výchozí hodnota parametru HKEY_CLASSES_ROOT\\*progid*\Shell klíč. Pokud není zadaná žádná hodnota, je výchozím slovesem první příkaz určený v HKEY_CLASSES_ROOT\\*progid*\Shell seznam klíčů.  
  
> [!NOTE]
>  Pokud chcete změnit výchozí akce pro rozšíření v nasazení vedle sebe, zvažte dopad na instalaci a odebrání. Během instalace se přepíše původní výchozí hodnotu.  
  
## <a name="see-also"></a>Viz také  
 [Správa přidružení souboru vedle sebe](../extensibility/managing-side-by-side-file-associations.md)