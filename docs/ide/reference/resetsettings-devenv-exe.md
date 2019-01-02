---
title: -ResetSettings (devenv.exe)
ms.date: 11/16/2018
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 160cbf93cee8ff778a4f84ee833c7fac3d7f26b1
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53830661"
---
# <a name="resetsettings-devenvexe"></a>/ResetSettings (devenv.exe)

Obnoví výchozí nastavení sady Visual Studio a automaticky spustí rozhraní IDE sady Visual Studio. Volitelně obnoví nastavení zadaného *vssettings* souboru.

Výchozí nastavení jsou určena podle profilu, který byl vybrán při prvním spuštění sady Visual Studio.

> [!TIP]
> Zjistěte, jak resetovat nastavení pomocí integrovaného vývojového prostředí (IDE), najdete v článku [Resetovat nastavení](../environment-settings.md#reset-settings).

## <a name="syntax"></a>Syntaxe

```cmd
Devenv /ResetSettings SettingsFile
```

## <a name="arguments"></a>Arguments

`SettingsFile`

Úplná cesta a název *vssettings* souboru do sady Visual Studio.

K obnovení profilu Obecné vývojové nastavení použijte `General`.

## <a name="remarks"></a>Poznámky

Pokud ne `SettingsFile` není zadána, budete vyzváni k výběru výchozí kolekce nastavení při příštím spuštění aplikace Visual Studio.

## <a name="example"></a>Příklad

Následující příkazový řádek použije nastavení uložená v souboru `MySettings.vssettings`.

```cmd
Devenv.exe /ResetSettings "C:\My Files\MySettings.vssettings"
```

## <a name="see-also"></a>Viz také:

- [Nastavení prostředí](../environment-settings.md)
- [Přizpůsobení prostředí IDE sady Visual Studio](../../ide/personalizing-the-visual-studio-ide.md)
- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)