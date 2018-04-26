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
ms.openlocfilehash: cdec487781928c22a34e5e7586700ed0e91a31a7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="resetsettings-devenvexe"></a>/ResetSettings (devenv.exe)

Obnoví výchozí nastavení sady Visual Studio a Visual Studio IDE automaticky spustí. Volitelně můžete do určeného obnoví nastavení *vssettings* souboru.

Výchozí nastavení určuje profil, který byl vybrán při byla první spuštění sady Visual Studio.

## <a name="syntax"></a>Syntaxe

```
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

```
Devenv.exe /ResetSettings "C:\My Files\MySettings.vssettings"
```

## <a name="see-also"></a>Viz také

- [Přizpůsobení sady Visual Studio IDE](../../ide/personalizing-the-visual-studio-ide.md)
- [Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)