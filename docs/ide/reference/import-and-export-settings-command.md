---
title: "Import a Export nastavení příkaz | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Tools.ImportandExportSettings
helpviewer_keywords:
- Tools.ImportandExportSettings
- Import and Export Settings command
ms.assetid: 94a06468-a44d-403d-a931-77bbc9d06e56
caps.latest.revision: "5"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 61924f7d9430661114f1fecc36d585e2d223604b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="import-and-export-settings-command"></a>Nastavení importu a exportu – příkaz
Importuje, exportuje nebo obnoví [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nastavení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Tools.ImportandExportSettings [/export:filename | /import:filename | /reset]  
```  
  
## <a name="switches"></a>Přepínače  
 / export:`filename`  
 Volitelné. Exportuje aktuální nastavení do zadaného souboru.  
  
 / import:`filename`  
 Volitelné. Naimportuje ho do zadaného souboru.  
  
 / Reset  
 Volitelné. Obnoví aktuální nastavení.  
  
## <a name="remarks"></a>Poznámky  
 Spuštění tohoto příkazu bez přepne otevře **nastavení importu a exportu** průvodce. Další informace najdete v tématu [postupy: nastavení sdílené složky mezi počítače nebo Visual Studio verze](http://msdn.microsoft.com/en-us/1131fb10-35c1-42da-9cd8-91aa3235b882).  
  
## <a name="example"></a>Příklad  
 Tento příkaz vyexportuje nastavení asi do souboru `MyFile.vssettings`.  
  
```  
Tools.ImportandExportSettings /export:"c:\Files\MyFile.vssettings"  
```  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení sady Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)