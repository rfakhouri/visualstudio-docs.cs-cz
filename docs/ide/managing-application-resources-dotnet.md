---
title: "Správa prostředků aplikace (.NET) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- msvse_resedit.dlg.SetCustomTool
- msvse_settingsdesigner.err.formatvalue
- msvse_resedit.err.nameblank
- msvse_resedit.err.duplicatename
helpviewer_keywords:
- editors [Visual Studio], Resource Designer
- Resource Designer
- resources [Visual Studio], managing
- Resources page in Project Designer
- resources types, Resource Designer
- application resources [Visual Studio]
- Project Designer, Resources page
ms.assetid: f2582734-8ada-4baa-8a7c-e2ef943ddf7e
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b599a919911fcc5d2833cfe69b75f7b32cced858
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="managing-application-resources-net"></a>Správa prostředků aplikace (.NET)
Soubory prostředků jsou soubory, které jsou součástí aplikace, ale nejsou kompilovány, pro soubory ikon příklad nebo zvukových souborů. Vzhledem k tomu, že tyto soubory nejsou součástí procesu kompilace, můžete je změnit bez nutnosti její kompilace vaší binární soubory. Pokud máte v úmyslu lokalizaci vaší aplikace, používejte zdrojové soubory pro všechny řetězce a další prostředky, které se musí změnit při lokalizaci berte vaší aplikace.  
  
Další informace o prostředcích v aplikacích klasické pracovní plochy rozhraní .NET najdete v tématu [prostředků v aplikacích plochy](/dotnet/framework/resources/index). Další informace o prostředcích v aplikacích klasické pracovní plochy C++ najdete v tématu [práce se zdrojovými soubory](/cpp/windows/working-with-resource-files).  
  
Aplikace UWP pomocí různých prostředků model z aplikace klasické pracovní plochy. Informace o prostředcích v aplikacích pro Windows 8.x najdete v tématu [definování prostředky aplikace (HTML)](https://msdn.microsoft.com/en-us/library/windows/apps/hh465228.aspx).  
  
## <a name="working-with-resources"></a>Práci s prostředky  
V projektu spravovaného kódu otevřete okno Vlastnosti projektu. Buď můžete otevřít okno Vlastnosti:

- pravým tlačítkem myši na uzel projektu v **Průzkumníku řešení** a výběrem **vlastnosti**
- zadáním **projektu vlastnosti** v **Snadné spuštění** okna
- Výběr **Alt + Enter** v **Průzkumníku řešení** okna

Vyberte **prostředky** kartě. Pokud projekt není obsahovat jeden již, přidat a odstranit různé druhy prostředků a upravit stávající prostředky, můžete přidat souboru RESX.  
  
Chcete-li zjistit, jak pracovat s prostředky v projektech C++, přečtěte si téma [postupy: vytvoření prostředku](/cpp/windows/how-to-create-a-resource).