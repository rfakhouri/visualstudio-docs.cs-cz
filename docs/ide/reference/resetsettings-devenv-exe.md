---
title: -ResetSettings (devenv.exe)
ms.date: 12/10/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- Devenv, /ResetSettings switch
- ResetSettings switch
- /ResetSettings Devenv switch
- settings [Visual Studio], resetting
ms.assetid: 1d41021c-6f58-4bd5-b122-d1c995812192
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 50b5d977776a754a03bb8cba232369f5823ed770
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54990235"
---
# <a name="resetsettings-devenvexe"></a>/ResetSettings (devenv.exe)

Obnoví výchozí nastavení sady Visual Studio a automaticky spustí rozhraní IDE sady Visual Studio. Tento přepínač volitelně obnoví nastavení do souboru zadaného nastavení.

Výchozí nastavení pocházejí z profilu, který byl vybrán při prvním spuštění sady Visual Studio.

> [!TIP]
> Zjistěte, jak resetovat nastavení pomocí integrovaného vývojového prostředí (IDE), najdete v článku [Resetovat nastavení](../environment-settings.md#reset-settings).

## <a name="syntax"></a>Syntaxe

```shell
devenv /ResetSettings [SettingsFile|DefaultCollectionSpecifier]
```

## <a name="arguments"></a>Arguments

- *SettingsFile*

  Volitelné. Úplná cesta a název souboru s nastavením pro použití se sadou Visual Studio.

- *DefaultCollectionSpecifier*

  Volitelné. Specifikátor, představující výchozí kolekce nastavení chcete obnovit. Zvolte jednu z specifikátory kolekce výchozí uvedené v tabulce.

  | Výchozí název kolekce | Specifikátor kolekce |
  | --- | --- |
  | **Obecné** | `General` |
  | **JavaScript** | `JavaScript` |
  | **Visual Basic** | `VB` |
  | **Visual C#** | `CSharp` |
  | **Visual C++** | `VC` |
  | **Vývoj pro web** | `Web` |
  | **Vývoj pro web (jenom kód)** | `WebCode` |

## <a name="remarks"></a>Poznámky

Pokud ne *Soubor_nastavení* není zadána, rozhraní IDE otevře pomocí stávajícího nastavení.

## <a name="example"></a>Příklad

První příklad použije nastavení uložená v souboru `MySettings.vssettings`.

Druhý příklad obnoví vizuál C# výchozí profil.

```shell
devenv /resetsettings "%USERPROFILE%\MySettings.vssettings"

devenv /resetsettings CSharp
```

## <a name="see-also"></a>Viz také:

- [Nastavení prostředí](../environment-settings.md)
- [Přizpůsobení prostředí IDE sady Visual Studio](../../ide/personalizing-the-visual-studio-ide.md)
- [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)