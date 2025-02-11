---
title: Import a Export nastavení příkaz | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- Tools.ImportandExportSettings
helpviewer_keywords:
- Tools.ImportandExportSettings
- Import and Export Settings command
ms.assetid: 94a06468-a44d-403d-a931-77bbc9d06e56
caps.latest.revision: 12
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 91b34183e36c86290c14e3da7d17687d45cfe180
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65694664"
---
# <a name="import-and-export-settings-command"></a>Nastavení importu a exportu – příkaz
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Importy, exporty nebo obnoví [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] nastavení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Tools.ImportandExportSettings [/export:filename | /import:filename | /reset]  
```  
  
## <a name="switches"></a>Přepínače  
 /export:`filename`  
 Volitelné. Exportuje aktuální nastavení do zadaného souboru.  
  
 /import:`filename`  
 Volitelné. Naimportuje ho do zadaného souboru.  
  
 / Reset  
 Volitelné. Obnoví aktuální nastavení.  
  
## <a name="remarks"></a>Poznámky  
 Spuštění tohoto příkazu bez přepínače otevře **nastavení importu a exportu** průvodce. Další informace najdete v tématu [jak: Sdílení nastavení mezi počítači nebo verzemi sady Visual Studio](https://msdn.microsoft.com/1131fb10-35c1-42da-9cd8-91aa3235b882).  
  
## <a name="example"></a>Příklad  
 Následující příkaz exportuje aktuální nastavení do souboru `MyFile.vssettings`.  
  
```  
Tools.ImportandExportSettings /export:"c:\Files\MyFile.vssettings"  
```  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení nastavení pro vývoj v sadě Visual Studio](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)
