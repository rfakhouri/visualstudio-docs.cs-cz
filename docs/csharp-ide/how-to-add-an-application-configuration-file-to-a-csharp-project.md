---
title: "Postupy: Přidání konfiguračního souboru aplikace do projektu C# | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords: app.config files, adding to C# projects
ms.assetid: 9caf6bb0-c2fc-4ab6-ba69-bed3b880fbf8
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 097e7a2eac78fe85b2a3ab62d5cdf1fd18908d56
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-an-application-configuration-file-to-a-c-project"></a>Postupy: Přidání konfiguračního souboru aplikace do projektu C#
Přidáním konfiguračního souboru aplikace (app.config soubor) do projektu C# můžete přizpůsobit, jak modul common language runtime vyhledá a načte soubory sestavení. Další informace o konfigurační soubory aplikace najdete v tématu [jak modul Runtime vyhledává sestavení](/dotnet/framework/deployment/how-the-runtime-locates-assemblies).  
  
> [!NOTE]
>  Aplikace UWP neobsahují šablonu app.config.
  
 Při sestavování projektu vývojového prostředí automaticky zkopíruje do souboru app.config, změníte název kopie tak, aby odpovídaly vaší spustitelný soubor a pak se posouvá kopie do adresáře bin.  
  
### <a name="to-add-an-application-configuration-file-to-your-c-project"></a>Přidání konfiguračního souboru aplikace do projektu C#  
  
1.  Na řádku nabídek zvolte **projektu**, **přidat novou položku**.  
  
     **Přidat novou položku** zobrazí se dialogové okno.  
  
2.  Rozbalte položku **nainstalovaná**, rozbalte položku **Visual C# položky**a potom zvolte **konfigurační soubor aplikace** šablony.  
  
3.  V **název** textového pole zadejte název a potom zvolte **přidat** tlačítko.  
  
     Soubor s názvem souboru app.config se přidá do projektu.  
  
## <a name="see-also"></a>Viz také  
 [Správa nastavení aplikace (.NET)](../ide/managing-application-settings-dotnet.md)   
 [Schéma konfiguračního souboru](/dotnet/framework/configure-apps/file-schema/index)   
 [Konfigurace aplikací](/dotnet/framework/configure-apps/index)   
 [Postupy: Konfigurace aplikace pro cílové verze rozhraní .NET Framework](http://msdn.microsoft.com/en-us/5247b307-89ca-417b-8dd0-e8f9bd2f4717)   
 [Použití vývojového prostředí sady Visual Studio pro jazyk C#](../csharp-ide/using-the-visual-studio-development-environment-for-csharp.md)