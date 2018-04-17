---
title: Postup přidání souboru app.config na projekt v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: conceptual
dev_langs:
- CSharp
helpviewer_keywords:
- app.config files, adding to C# projects
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: 22b9ed31621074e27cfa2d51502e44d508d6b424
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-an-application-configuration-file-to-a-c-project"></a>Postupy: Přidání konfiguračního souboru aplikace do projektu C#

Přidáním konfiguračního souboru aplikace (*app.config* soubor) do projektu jazyka C#, můžete přizpůsobit, jak modul common language runtime vyhledá a načte soubory sestavení. Další informace o konfigurační soubory aplikace najdete v tématu [jak běhové prostředí vyhledává sestavení (rozhraní .NET Framework)](/dotnet/framework/deployment/how-the-runtime-locates-assemblies).

> [!NOTE]
> Aplikace UWP neobsahují *app.config* souboru.

Při sestavování projektu vývojového prostředí automaticky zkopíruje vaše *app.config* souborů, změny názvu souboru kopie tak, aby odpovídaly vaší spustitelný soubor a pak se posouvá kopírovat do **bin** adresář.

## <a name="to-add-an-application-configuration-file-to-a-c-project"></a>Přidání konfiguračního souboru aplikace do projektu C#

1. Na řádku nabídek zvolte **projektu** > **přidat novou položku**.

     **Přidat novou položku** zobrazí se dialogové okno.

1. Rozbalte položku **nainstalovaná** > **Visual C# položky**a potom zvolte **konfigurační soubor aplikace** šablony.

1. V **název** textového pole zadejte název a potom zvolte **přidat** tlačítko.

     Soubor s názvem *app.config* se přidá do projektu.

## <a name="see-also"></a>Viz také

[Správa nastavení aplikace (.NET)](../ide/managing-application-settings-dotnet.md)  
[Schéma konfiguračního souboru (rozhraní .NET Framework)](/dotnet/framework/configure-apps/file-schema/index)  
[Konfigurace aplikací (rozhraní .NET Framework)](/dotnet/framework/configure-apps/index)