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
ms.openlocfilehash: a95841d9b9b8e67f34883efcc1a55a2daba7e8b7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
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

Spuštění tohoto příkazu bez přepne otevře **nastavení importu a exportu** průvodce. Další informace najdete v tématu [synchronizovat nastavení](../../ide/synchronized-settings-in-visual-studio.md).

## <a name="example"></a>Příklad

Tento příkaz vyexportuje nastavení asi do souboru `MyFile.vssettings`.

```shell
Tools.ImportandExportSettings /export:"c:\Files\MyFile.vssettings"
```

## <a name="see-also"></a>Viz také

- [Přizpůsobení sady Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)
- [Příkazy sady Visual Studio](../../ide/reference/visual-studio-commands.md)