---
title: "devenv.exe InstallVSTemplates – přepínač | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Devenv, /InstallVSTemplates switch
- /InstallVSTemplates Devenv switch
- InstallVSTemplates switch
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 529979caa801ace8dd649cf1614f2eeb27ca070b
ms.sourcegitcommit: d16c6812b114a8672a58ce78e6988b967498c747
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2018
---
# <a name="installvstemplates-devenvexe"></a>/InstallVSTemplates (devenv.exe)

/ Installvstemplates přepínač registry projekt nebo položku šablony, které se nacházejí v  *\<cesta instalace sady Visual Studio >*\Common7\IDE\ProjectTemplates\ nebo  *\<Visual Studio Instalační cesta >*\Common7\IDE\ItemTemplates\ tak, že jsou dostupné prostřednictvím **nový projekt** a **přidat novou položku** dialogová okna.

> [!WARNING]
> Tento přepínač je podporována pouze pro vývoj partnera pro Visual Studio. Devenv musíte spustit jako správce Chcete-li použít [/Setup (devenv.exe)](../../ide/reference/setup-devenv-exe.md) a [/installvstemplates (devenv.exe)](../../ide/reference/installvstemplates-devenv-exe.md) přepínače. Další informace najdete v tématu [oprávnění uživatele](../../ide/user-permissions-and-visual-studio.md).

## <a name="syntax"></a>Syntaxe

```
devenv.exe /InstallVSTemplates
```

## <a name="see-also"></a>Viz také

[Devenv – přepínače příkazového řádku](../../ide/reference/devenv-command-line-switches.md)