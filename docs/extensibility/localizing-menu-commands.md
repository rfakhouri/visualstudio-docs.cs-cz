---
title: "Lokalizace příkazy nabídky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- localize
- localization
- vsct
- menu commands
- localize visual studio
- localize vsct
ms.assetid: b04ee0f6-82ea-47e6-853a-72382267d6da
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 77bd698149ca4e73b462fc3ada9256ba5911177e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="localizing-menu-commands"></a>Lokalizace příkazy nabídky
Můžete zadat text lokalizované nabídky a nástrojů příkazy vytvořením lokalizované .vsct soubory a lokalizované soubory RESX pro vaše VSPackage a potom aktualizuje soubory projektu, tak aby se projevily změny.  
  
 Informace o tom, jak lokalizaci prostředí instalace najdete v tématu [lokalizace balíčky VSIX](../extensibility/localizing-vsix-packages.md).  
  
## <a name="localizing-command-names"></a>Lokalizace názvy příkazů  
 V VSPackages tlačítka panelu nástrojů a příkazy nabídky jsou definovány v souboru .vsct.  
  
1.  V **Průzkumníku řešení**, změňte název souboru .vsct z *filename*.vsct k *filename*.en-US.vsct.  
  
2.  Vytvořit kopii *filename*.en-US.vsct pro jednotlivé lokalizované jazyk.  
  
     Název každé kopie *filename*. *Národní prostředí*.vsct, kde *národního prostředí* je název konkrétní jazykové verze. Seznam hodnot název jazykové verze, najdete v části [Locale IDs Assigned přiřazené společností Microsoft](https://msdn.microsoft.com/en-us/library/windows/apps/jj657969.aspx).  
  
     Tyto *filename*. *Národní prostředí*.vsct soubory bude obsahovat text lokalizované nabídky pro svůj balíček.  
  
3.  Otevírání jednotlivých *filename*. *Národní prostředí*.vsct souboru k lokalizaci text.  
  
    1.  Změnit [ButtonText](../extensibility/buttontext-element.md) element hodnoty podle potřeby pro konkrétní jazyk.  
  
    2.  Pokud zadáte lokalizované ikony, upravte [rastrový obrázek](../extensibility/bitmap-element.md) hodnoty tak, aby odkazoval na cílové soubory.  
  
     Následující příklad ukazuje angličtinu a slovenštinu text tlačítka pro příkaz k otevření okna Průzkumník rodiny stromu nástroj.  
  
     [FamilyTree.en-US.vsct]  
  
    ```xml  
    <Button guid="guidLocalizedPackageCmdSet" id="cmdidFamilyTree" priority="0x0100" type="Button">  
      <Parent guid="guidSHLMainMenu" id="IDG_VS_WNDO_OTRWNDWS1"/>  
      <Icon guid="guidImages" id="bmpPic2" />  
      <Strings>  
        <CommandName>cmdidFamilyTree</CommandName>  
        <ButtonText>Family Tree Explorer</ButtonText>  
      </Strings>  
    </Button>  
    ```  
  
     [FamilyTree.es-ES.vsct]  
  
    ```xml  
    <Button guid="guidLocalizedPackageCmdSet" id="cmdidFamilyTree" priority="0x0100" type="Button">  
      <Parent guid="guidSHLMainMenu" id="IDG_VS_WNDO_OTRWNDWS1"/>  
      <Icon guid="guidImages" id="bmpPic2" />  
      <Strings>  
        <CommandName>cmdidFamilyTree</CommandName>  
        <ButtonText>Explorar el arbol genealogico</ButtonText>  
      </Strings>  
    </Button>  
  
    ```  
  
## <a name="localizing-other-text-resources"></a>Lokalizace prostředků další Text  
 Text prostředků než názvy příkazů jsou definovány v soubory prostředků (RESX).  
  
1.  Přejmenujte VSPackage.resx VSPackage.en-US.resx.  
  
2.  Vytvořte kopii souboru VSPackage.en US.resx pro jednotlivé lokalizované jazyky.  
  
     Název každé kopie VSPackage. *Národního prostředí*RESX, kde *národního prostředí* je název konkrétní jazykové verze.  
  
3.  Přejmenujte Resources.resx názvy Resources.en-US.resx.  
  
4.  Vytvořte kopii souboru názvy Resources.en-US.resx pro jednotlivé lokalizované jazyky.  
  
     Název každé kopie prostředky. *Národního prostředí*RESX, kde *národního prostředí* je název konkrétní jazykové verze.  
  
5.  Otevřete každý soubor .resx změnit řetězcové hodnoty podle potřeby pro konkrétní jazyk a jazykovou verzi. Následující příklad ukazuje definici lokalizovaný prostředek pro záhlaví okno nástroje.  
  
     [Názvy Resources.en-US.resx]  
  
    ```xml  
    <data name="ToolWindowTitle" xml:space="preserve">  
      <value>Family Tree Explorer</value>  
    </data>  
    ```  
  
     [Resources.es-ES.resx]  
  
    ```xml  
    <data name="ToolWindowTitle" xml:space="preserve">  
      <value>Explorador del arbol genealogico</value>  
    </data>  
  
    ```  
  
## <a name="incorporating-localized-resources-into-the-project"></a>Zařadit lokalizované prostředky do projektu  
 Musíte upravit soubor assemblyinfo.cs a soubor projektu do začlenit lokalizované prostředky.  
  
1.  Z **vlastnosti** uzlu v **Průzkumníku řešení**, otevřete assemblyinfo.cs nebo assemblyinfo.vb v editoru.  
  
2.  Přidejte následující položku.  
  
    ```csharp  
    [assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]  
    ```  
  
     Toto nastaví angličtinu jako výchozí jazyk.  
  
3.  Uvolněte projekt.  
  
4.  V editoru otevřete soubor projektu.  
  
5.  Vyhledejte `ItemGroup` elementu, který obsahuje `EmbeddedResource` elementy.  
  
6.  V `EmbeddedResource` element, který volá VSPackage.en-US.resx, nahraďte `ManifestResourceName` element s `LogicalName` elementu, nastavte na `VSPackage.en-US.Resources`, a to takto.  
  
    ```xml  
    <EmbeddedResource Include="VSPackage.en-US.resx">  
      <MergeWithCTO>true</MergeWithCTO>  
      <LogicalName>VSPackage.en-US.Resources</LogicalName>  
    </EmbeddedResource>  
    ```  
  
7.  Pro jednotlivé lokalizované jazyky, zkopírujte `EmbeddedResource` element pro VsPackage.en USA a nastavte **zahrnout** atribut a **LogicalName** element kopie cíl národního prostředí, jak je znázorněno v následující Příklad.  
  
8.  Všechny lokalizované `VSCTCompile` elementu, přidejte `ResourceName` element, který odkazuje na `Menus.ctmenu`, jak je znázorněno v následujícím příkladu.  
  
    ```xml  
    <ItemGroup>  
      <VSCTCompile Include="LocalizedPackage.es-ES.vsct">  
        <ResourceName>Menus.ctmenu</ResourceName>  
      </VSCTCompile>  
    </ItemGroup>  
    ```  
  
9. Uložte soubor projektu a projekt znovu načíst.  
  
10. Sestavte projekt.  
  
     Tím se vytvoří hlavní sestavení a sestavení prostředků pro jednotlivé jazyky. Informace o lokalizaci procesu nasazení najdete v tématu [lokalizace balíčky VSIX](../extensibility/localizing-vsix-packages.md)  
  
## <a name="see-also"></a>Viz také  
 [Rozšíření nabídek a příkazů](../extensibility/extending-menus-and-commands.md)   
 [MenuCommands Vs. OleMenuCommands](../extensibility/menucommands-vs-olemenucommands.md)   
 [Globalizace a lokalizace aplikací](../ide/globalizing-and-localizing-applications.md)