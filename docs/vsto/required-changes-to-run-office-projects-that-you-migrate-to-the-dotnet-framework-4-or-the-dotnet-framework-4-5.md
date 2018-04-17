---
title: Požadované změny pro spouštění projektů Office migrovaných na rozhraní .NET Framework 4 nebo .NET Framework 4.5 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office projects [Office development in Visual Studio], migrating to .NET Framework 4
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 5df72bcf36907dbb556e8d7fffd30cb224bfd41c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="required-changes-to-run-office-projects-that-you-migrate-to-the-net-framework-4-or-the-net-framework-45"></a>Požadované změny pro spouštění projektů Office migrovaných na rozhraní .NET Framework 4 nebo .NET Framework 4.5
  Pokud cílový framework projektu Office se změní na [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo později ze starší verze rozhraní .NET Framework, je třeba provést následující úkoly a ujistěte se, že řešení můžete spustit na vývojovém počítači a počítače koncového uživatele:  
  
-   Odeberte <xref:System.Security.SecurityTransparentAttribute> z projektu, pokud jste upgradovali ze sady Visual Studio 2008.  
  
-   Provedení **Vyčistit** příkazu v sadě Visual Studio, abyste mohli spustit nebo ladění projektu na vývojovém počítači.  
  
-   Aktualizace požadované pro projekt rozhraní .NET Framework.  
  
-   Koncoví uživatelé nutné přeinstalovat také řešení, pokud jste ho předtím nasadili s použitím technologie ClickOnce než změnit cílový framework.  
  
 Další informace o každém z těchto úloh najdete v tématu odpovídající oddílech.  
  
## <a name="removing-the-securitytransparent-attribute-from-projects-that-you-upgrade-from-visual-studio-2008"></a>Odebráním atributu SecurityTransparent z projektů, které upgradujete z Visual Studio 2008  
 Pokud provádíte upgrade projektu Office ze sady Visual Studio 2008 a cílový framework projektu následně změny [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, musíte odebrat <xref:System.Security.SecurityTransparentAttribute> z projektu. Visual Studio není odeberte tento atribut automaticky. Pokud tento atribut neodeberete, obdržíte chybovou zprávu při kompilaci projektu.  
  
 Další informace o podmínkách, ve kterých Visual Studio můžete změnit cílový framework upgradovaném projektu na [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], najdete v části [upgrade a migrace řešení Office](../vsto/upgrading-and-migrating-office-solutions.md).  
  
#### <a name="to-remove-the-securitytransparentattribute"></a>Chcete-li odebrat SecurityTransparentAttribute  
  
1.  S projektem otevřeným v sadě Visual Studio, otevřete **Průzkumníku řešení**.  
  
2.  V části **vlastnosti** uzlu (pro jazyk C#) nebo **Můj projekt** uzlu (pro Visual Basic), poklikejte na soubor AssemblyInfo kódu a otevře se v editoru kódu.  
  
    > [!NOTE]  
    >  V projektech Visual Basic, musíte kliknout na **zobrazit všechny soubory** tlačítka na **Průzkumníku řešení** zobrazíte souboru AssemblyInfo kódu.  
  
3.  Vyhledejte <xref:System.Security.SecurityTransparentAttribute> a ze souboru odebrat nebo ho nastavte jako komentář.  
  
    ```vb  
    <Assembly: SecurityTransparent()>  
    ```  
  
    ```csharp  
    [assembly: SecurityTransparent()]  
    ```  
  
## <a name="performing-the-clean-command-to-debug-or-run-a-project-on-the-development-computer"></a>Provádění čisté příkaz pro ladění a spuštění projektu na vývojovém počítači  
 Pokud projekt Office byla předtím, než cílový framework projektu se změní na [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, je třeba provést **Vyčistit** příkazu a pak znovu vytvořte projekt po změně cílové rozhraní. Pokud neprovádět **Vyčistit** příkaz, zobrazí se <xref:System.Runtime.InteropServices.COMException> při pokusu ladění a spusťte přesměrovanou projekt.  
  
 Další informace o **Vyčistit** příkazů najdete v tématu [vytváření řešení pro systém Office](../vsto/building-office-solutions.md).  
  
## <a name="updating-the-prerequisites-for-deployment"></a>Aktualizace požadavků na nasazení  
 Když změňte cíl Microsoft Office project k [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, je nutné také aktualizovat odpovídající předpokladů v rozhraní .NET Framework **požadavky** dialogové okno. ClickOnce – nasazení nebo projekt InstallShield Limited Edition, jinak hodnota kontroluje a nainstaluje předchozí verzi rozhraní .NET Framework.  
  
 Další informace o aktualizaci požadavky pro nasazení do počítačů koncových uživatelů najdete v tématu [postupy: instalace požadavky v počítačích koncových uživatelů pro spuštění řešení pro systém Office](http://msdn.microsoft.com/en-us/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98).  
  
## <a name="reinstalling-solutions-on-end-user-computers"></a>Přeinstalaci řešení do počítače koncového uživatele  
 Pokud používáte ClickOnce k nasazení řešení Office, která je cílena na rozhraní .NET Framework 3.5 a potom změňte cíl projekt, který má [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, musí koncoví uživatelé řešení odinstalujte a znovu řešení po znovu ji publikovat. Pokud je znovu publikovat přesměrovanou řešení a řešení se aktualizuje na počítače koncového uživatele, se koncovým uživatelům zobrazí <xref:System.Runtime.InteropServices.COMException> při jejich spuštění aktualizované řešení.  
  
## <a name="see-also"></a>Viz také  
 [Migrace řešení Office na rozhraní .NET Framework 4 nebo novější](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)  
  
  