---
title: Správa prostředků aplikace (.NET) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
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
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b6fb31449dbbe56416f2f6c3f31142638d90d366
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65674954"
---
# <a name="managing-application-resources-net"></a>Správa prostředků aplikace (.NET)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Zdrojové soubory jsou soubory, které jsou součástí aplikace, ale nejsou zkompilovány, pro soubory ikon příklad nebo zvukové soubory. Protože tyto soubory nejsou součástí procesu kompilace, můžete je změnit bez nutnosti znovu kompilovat vaše binární soubory. Pokud máte v úmyslu lokalizovat vaši aplikaci, měli byste použít soubory prostředků pro všechny řetězce a další prostředky, které je potřeba změnit, pokud lokalizovat vaši aplikaci.  
  
 Další informace o prostředcích v desktopové aplikace .NET najdete v tématu [prostředky v desktopových aplikací](https://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890). Další informace o prostředcích v aplikacích klasické pracovní plochy jazyka C++, naleznete v tématu [práce se zdrojovými soubory](https://msdn.microsoft.com/library/2699a539-b369-4b78-80f0-df03eb7b6780).  
  
 Aplikace Windows Store pomocí modelu jinému prostředku z aplikací klasické pracovní plochy. Informace o prostředcích v aplikacích pro Windows Store naleznete v tématu [definování prostředků aplikace](https://msdn.microsoft.com/library/windows/apps/hh465228.aspx) na webu Windows Dev Center.  
  
## <a name="working-with-resources"></a>Práce s prostředky  
 V spravovaný projekt kódu, otevřete okno s vlastnostmi projektu (klikněte pravým tlačítkem na uzel projektu v **Průzkumníka řešení** a vyberte **vlastnosti**, nebo typ **vlastnostiprojektu**v **Snadné spuštění** okna, nebo zadejte ALT + ENTER v **Průzkumníka řešení** okno). Vyberte **prostředky** kartu. Pokud váš projekt není již obsahovat jednu, přidat a odstraňovat různé druhy prostředků a úpravám stávajících prostředků, můžete přidat soubor .resx.  
  
 Chcete-li zjistit, jak pracovat s prostředky v projektech C++, přečtěte si téma [jak: Vytvořit prostředek](https://msdn.microsoft.com/library/aad44914-9145-45a3-a7d8-9de89b366716).
