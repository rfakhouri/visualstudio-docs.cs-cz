---
title: -Resetsettings – (devenv.exe)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Devenv, /ResetSettings switch
- ResetSettings switch
- /ResetSettings Devenv switch
ms.assetid: 1d41021c-6f58-4bd5-b122-d1c995812192
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3c3d3a6ef558b510cfde716716daf97a549fbba4
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
---
# <a name="resetsettings-devenvexe"></a>/ResetSettings (devenv.exe)

Obnoví výchozí nastavení sady Visual Studio a Visual Studio IDE automaticky spustí. Volitelně můžete do určeného obnoví nastavení *vssettings* souboru.

Výchozí nastavení určuje profil, který byl vybrán při byla první spuštění sady Visual Studio.

## <a name="syntax"></a>Syntaxe

```cmd
Devenv /ResetSettings SettingsFile
```

## <a name="arguments"></a>Arguments

`SettingsFile`

Úplná cesta a název *vssettings* souboru chcete použít pro Visual Studio.

Chcete-li obnovit profil obecná nastavení pro vývoj, použijte `General`.

## <a name="remarks"></a>Poznámky

Pokud žádné `SettingsFile` je zadán, zobrazí se výzva k výběru kolekce výchozí nastavení při dalším spuštění sady Visual Studio.

## <a name="example"></a>Příklad

Následující příkazový řádek aplikuje nastavení uložené v souboru `MySettings.vssettings`.

```cmd
Devenv.exe /ResetSettings "C:\My Files\MySettings.vssettings"
```

## <a name="see-also"></a>Viz také

- [Přizpůsobení sady Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)
- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)