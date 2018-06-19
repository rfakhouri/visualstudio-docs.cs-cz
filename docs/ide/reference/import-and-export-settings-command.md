---
title: Nastavení importu a exportu – příkaz
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- Tools.ImportandExportSettings
helpviewer_keywords:
- Tools.ImportandExportSettings
- Import and Export Settings command
ms.assetid: 94a06468-a44d-403d-a931-77bbc9d06e56
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4119abf74281e3c0dbb2b3d5f3ef472a0527a08f
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33704584"
---
# <a name="import-and-export-settings-command"></a>Nastavení importu a exportu – příkaz
Importuje, exportuje nebo obnoví [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nastavení.

## <a name="syntax"></a>Syntaxe

```cmd
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

Spuštění tohoto příkazu bez přepne otevře **nastavení importu a exportu** průvodce. Další informace najdete v tématu [synchronizovat nastavení](../../ide/synchronized-settings-in-visual-studio.md).

## <a name="example"></a>Příklad

Následující příkaz exportuje aktuální nastavení do souboru `MyFile.vssettings`.

```cmd
Tools.ImportandExportSettings /export:"c:\Files\MyFile.vssettings"
```

## <a name="see-also"></a>Viz také

- [Přizpůsobení sady Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)