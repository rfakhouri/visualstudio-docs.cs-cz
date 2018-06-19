---
title: Typy souborů projektu a řešení
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b3786d6f38e4f87aa05a51b0a6112613bda65e56
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31947596"
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

- [Projekty a řešení](../../ide/solutions-and-projects-in-visual-studio.md)