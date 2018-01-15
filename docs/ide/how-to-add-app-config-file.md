---
title: "Postup přidání souboru app.config na projekt v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords: app.config files, adding to C# projects
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: d77e86599670ef04b813381da84a03ab1f238af3
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="how-to-add-an-application-configuration-file-to-a-c-project"></a>Postupy: Přidání konfiguračního souboru aplikace do projektu C#

Přidáním konfiguračního souboru aplikace (app.config soubor) do projektu C# můžete přizpůsobit, jak modul common language runtime vyhledá a načte soubory sestavení. Další informace o konfigurační soubory aplikace najdete v tématu [jak běhové prostředí vyhledává sestavení (rozhraní .NET Framework)](/dotnet/framework/deployment/how-the-runtime-locates-assemblies).

> [!NOTE]
> Aplikace UWP neobsahují soubor app.config.

Při sestavování projektu vývojového prostředí automaticky zkopíruje do souboru app.config, změníte název kopie tak, aby odpovídaly vaší spustitelný soubor a pak se posouvá kopírovat do **bin** adresáře.

## <a name="to-add-an-application-configuration-file-to-a-c-project"></a>Přidání konfiguračního souboru aplikace do projektu C#

1. Na řádku nabídek zvolte **projektu** > **přidat novou položku**.

     **Přidat novou položku** zobrazí se dialogové okno.

1. Rozbalte položku **nainstalovaná** > **Visual C# položky**a potom zvolte **konfigurační soubor aplikace** šablony.

3 ve **název** textového pole zadejte název a potom zvolte **přidat** tlačítko.

     A file named app.config is added to your project.

## <a name="see-also"></a>Viz také

[Správa nastavení aplikace (.NET)](../ide/managing-application-settings-dotnet.md)  
[Schéma konfiguračního souboru (rozhraní .NET Framework)](/dotnet/framework/configure-apps/file-schema/index)  
[Konfigurace aplikací (rozhraní .NET Framework)](/dotnet/framework/configure-apps/index)