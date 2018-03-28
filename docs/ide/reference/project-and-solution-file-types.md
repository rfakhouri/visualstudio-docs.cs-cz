---
title: Typy souborů projektu a řešení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- File Properties.CopyToOutputDirectory
- File Properties.CustomToolNamespace
- File Properties.FileName
- File Properties.FullPath
- File Properties.BuildAction
- File Properties.CustomTool
- FileProperties
helpviewer_keywords:
- .sln files
- .suo files
- file types [Visual Studio]
- file extensions [Visual Studio]
- solution files [Visual Studio]
- sln files
- suo files
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: d239a5e129f12c4521ba190674d84430f8f2e646
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/28/2018
---
# <a name="project-and-solution-file-types"></a>Typy souborů projektu a řešení

Visual Studio podporuje mnoho typů souborů. V konkrétním zařízení nainstalované součásti určí, které typy souborů jsou podporovány. Toto téma uvádí typy souborů řešení a projektu, které jsou podporovány pro některé typické instalace.

## <a name="solution-files-sln-and-suo"></a>Soubory řešení (.sln a .suo)

Visual Studio používá dva typy souborů (.sln a .suo) k uložení nastavení řešení. Tyto soubory souhrnně označované jako soubory řešení, zadejte Průzkumníku řešení s informacemi potřebnými k zobrazení grafické rozhraní pro správu vašich souborů.

|Rozšíření|Název|Popis|
|---------------|----------|-----------------|
|.sln|Řešení sady Visual Studio|Umožňuje uspořádat projekty, položky projektu a řešení položky do řešení.|
|.suo|Možnosti řešení uživatele|Uchovává informace o přizpůsobení na úrovni uživatele, které jste provedli pro Visual Studio, jako je například zarážky.|

## <a name="project-files"></a>Soubory projektu

Projekty mohou obsahovat mnoho typů jiný soubor. Například mít soubory kódu C# **.cs** rozšíření a mít soubory C++ **sada** rozšíření. Prostředky jsou uloženy v **RESX** soubory a XAML v **XAML** soubory. [App.config](../../ide/managing-application-settings-dotnet.md) soubory obsahují informace o aplikaci, která by neměly být obsažené v kódu aplikace&mdash;například připojovací řetězce.

Další informace o typech souborů v projektech C++ najdete v tématu [typy souborů vytvořené pro projekty Visual C++](/cpp/ide/file-types-created-for-visual-cpp-projects).

## <a name="see-also"></a>Viz také

[Projekty a řešení](../../ide/solutions-and-projects-in-visual-studio.md)