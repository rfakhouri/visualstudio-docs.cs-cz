---
title: "Návod: Import vlastní stránky předlohy a stránky webu s bitovou kopii | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, importing items
- importing items [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 544c3c727046fdcabcde90f221f4b630c11cf29f
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-import-a-custom-master-page-and-site-page-with-an-image"></a>Návod: Import vlastní stránky předlohy a stránky webu s obrázkem
  Tento návod ukazuje, jak importovat SharePoint stránky předlohy a stránky webu, který obsahuje bitovou kopii do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projektu služby SharePoint.  
  
 Tento návod ukazuje, jak k provádění následujících úloh:  
  
-   Vytvořte vlastní stránky předlohy a stránky webu pomocí obrázku v seznamu služby SharePoint.  
  
-   Exportujte vlastní stránky předlohy, image a stránka na soubor řešení (WSP) služby SharePoint.  
  
-   Importujte a nasaďte do souboru WSP [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projektu služby SharePoint pomocí projektu Import balíčku řešení služby SharePoint.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 Musíte mít následující součásti pro dokončení tohoto návodu:  
  
-   Podporované edice systému [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] a služby SharePoint. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)][Požadavky na vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
-   SharePoint Designer 2010.  
  
## <a name="create-items-in-sharepoint-designer"></a>Vytváření položek v seznamu služby SharePoint  
 Tento příklad ukazuje, jak vytvořit tři položky v seznamu služby SharePoint pro export: vlastní stránky předlohy, stránka serveru, který odkazuje na vlastní stránky předlohy a soubor bitové kopie se objeví na stránce webu. Obrázek je přidán do složky /images/ ve službě SharePoint.  
  
#### <a name="to-create-a-custom-master-page-in-sharepoint-designer"></a>Chcete-li vytvořit vlastní stránky předlohy v seznamu služby SharePoint  
  
1.  V seznamu služby SharePoint, vyberte v navigačním podokně **stránky předlohy** objektu webu.  
  
2.  Na **stránky předlohy** pásu karet, zvolte **prázdné stránky předlohy**.  
  
3.  Zvolte nové stránky předlohy a pak klikněte na **stránky předlohy** pásu karet, zvolte **upravit soubor**.  
  
4.  V dolní části seznamu služby SharePoint, vyberte **kód** kartě.  
  
5.  Nahraďte kód existující následující kód.  
  
    ```  
    <%@ Master Language="C#" %>  
    <%@ Register tagprefix="SharePoint" namespace="Microsoft.SharePoint.WebControls" assembly="Microsoft.SharePoint, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>  
    <html dir="ltr">  
    <head runat="server">  
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">  
    <SharePoint:RobotsMetaTag runat="server" __designer:Preview="" __designer:Values="<P N='InDesign' T='False' /><P N='ID' T='ctl00' /><P N='Page' ID='1' /><P N='TemplateControl' ID='2' /><P N='AppRelativeTemplateSourceDirectory' R='-1' />"></SharePoint:RobotsMetaTag>  
    <title>Web Page</title>  
    </head>  
    <body>  
    <form id="form1" runat="server">  
    <asp:ContentPlaceHolder id="ContentPlaceHolderMain"   
            runat="server">  
          </asp:ContentPlaceHolder>  
    </form>  
    </body>  
    </html>  
    ```  
  
6.  Uložit stránky, vyberte **stránky předlohy** kartě a přejmenujte stránky předlohy jako **mybasic1.master**.  
  
## <a name="add-an-image-to-the-content-database-in-sharepoint-designer"></a>Přidejte bitovou kopii k databázi obsahu služby SharePoint Designer  
 Teď můžete přidat obrázek, který se zobrazí na stránce webu. Obrázek se nasadí do databáze obsahu služby SharePoint.  
  
#### <a name="to-add-an-image-to-the-content-database-in-sharepoint-designer"></a>Chcete-li přidat bitovou kopii k databázi obsahu služby SharePoint Designer  
  
1.  V navigačním podokně, vyberte **všechny soubory** lokality objektu a zvolte ve stromovém zobrazení **bitové kopie** složky.  
  
2.  Na **všechny soubory** pásu karet, zvolte **Import souborů**, zvolte soubor podle svého výběru a pak **OK** tlačítko. V tomto příkladu je soubor s názvem **myimg1.png**.  
  
     Volitelně můžete vytvořit podsložky kvůli lepší organizaci bitové kopie.  
  
3.  Zavřít **Import** dialogové okno.  
  
## <a name="create-a-site-page"></a>Vytvoření stránky webu  
 Tato základní stránka používá vlastní stránky předlohy a zobrazí obrázek, který jste přidali v předchozím kroku.  
  
#### <a name="to-create-a-site-page"></a>K vytvoření stránky webu  
  
1.  V navigačním podokně, vyberte **weby** objektu.  
  
2.  Na **stránky** pásu karet, vyberte **stránky** tlačítko, vyberte **ASPX** stránka typu s názvem nový soubor **mycontentpage1.aspx**.  
  
     Volitelně můžete vytvořit podsložky kvůli lepší organizaci stránky webu.  
  
3.  V seznamu lokalit stránky, zvolte **MyContentPage1.aspx** otevřete stránku s jeho vlastnosti, a potom v dolní části stránky, vyberte **úpravy souboru** odkaz.  
  
     Pokud zpráva se zobrazí a informacemi o tom, že tato stránka neobsahuje žádné oblasti, které lze upravit v nouzovém režimu a zobrazí dotaz, zda má otevřete tuto stránku v rozšířeném režimu, zvolte **Ano** tlačítko.  
  
4.  V dolní části stránky, vyberte **kód** tlačítko.  
  
5.  Nahraďte kód existující následující kód.  
  
    ```  
    <%@ Import Namespace="Microsoft.SharePoint.ApplicationPages" %>  
    <%@ Register Tagprefix="SharePoint" Namespace="Microsoft.SharePoint.WebControls" Assembly="Microsoft.SharePoint, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>  
    <%@ Register Tagprefix="Utilities" Namespace="Microsoft.SharePoint.Utilities" Assembly="Microsoft.SharePoint, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>  
    <%@ Register Tagprefix="asp" Namespace="System.Web.UI" Assembly="System.Web.Extensions, Version=3.5.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" %>  
    <%@ Import Namespace="Microsoft.SharePoint" %>  
    <%@ Assembly Name="Microsoft.Web.CommandUI, Version=14.0.0.0, Culture=neutral, PublicKeyToken=71e9bce111e9429c" %>  
    <%@ Page Language="C#" Inherits="Microsoft.SharePoint.WebControls.LayoutsPageBase" MasterPageFile="../_catalogs/masterpage/mybasic1.master" meta:progid="SharePoint.WebPartPage.Document" %>  
  
    <asp:Content ID="Main" ContentPlaceHolderID="ContentPlaceHolderMain" runat="server">  
    <img alt="My Image" longdesc="My image from images folder" src="../images/myimg1.png" />  
    </asp:Content>  
    ```  
  
6.  Uložte aktualizovaný stránka.  
  
## <a name="export-the-items-from-sharepoint"></a>Export položek ze služby SharePoint  
 Exportujte položek ze služby SharePoint do souboru (WSP) řešení služby SharePoint.  
  
#### <a name="to-export-items-from-sharepoint-designer"></a>Export položky ze seznamu služby SharePoint  
  
1.  V seznamu služby SharePoint, vyberte v navigačním podokně **týmový web** objekt a pak klikněte na **lokality** pásu karet, zvolte **uložit jako šablonu**.  
  
2.  V **uložit jako šablonu** dialogovém okně zadejte název souboru a název šablony, vyberte **zahrnout obsah** zaškrtněte políčko a potom vyberte **OK** tlačítko.  
  
     To v souboru WSP uloží obsah webu.  
  
3.  Po exportuje řešení, vyberte **řešení Galerie** odkaz zobrazíte seznam souborů k dispozici řešení.  
  
4.  Otevřete místní nabídku pro nový soubor WSP a zvolte **Uložit cíl jako** ji uložit do systému.  
  
## <a name="import-the-items-into-visual-studio"></a>Import položek do sady Visual Studio  
 Import souborů WSP do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Po importu obsahu můžete přizpůsobit, přidejte další položky a poté ji nasadit.  
  
#### <a name="to-import-items-from-the-wsp-file-into-visual-studio"></a>Import položek ze souboru WSP do sady Visual Studio  
  
1.  V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], vytvořit **importu služby SharePoint 2010 řešení balíček** projektu.  
  
2.  Na **vybrat položky k importu** v části **modulu** v **typ** sloupce, zaškrtněte políčka u pouze soubory v následující tabulce pro import.  
  
    |Název souboru|Popis|  
    |---------------|-----------------|  
    |_catalogsmasterpage\_|Vlastní stránky předlohy.|  
    |images_|Soubor bitové kopie v systému souborů služby SharePoint.|  
    |SitePages_|Stránka.|  
  
3.  Vyberte **Dokončit** tlačítko Import vybraných položek.  
  
4.  V **Průzkumníku řešení**, vyberte _catalogsmasterpage\_ uzel a nastavte hodnotu jeho **řešení konfliktů při nasazení** vlastnost **automatické**.  
  
     To pomáhá zajistit, že jsou všechny konflikty nasazení automaticky vyřešen.  
  
5.  Pokud nové stránky předlohy má stejný název jako existující stránky, ujistěte se, že existující stránky není označená jako stránku předlohy výchozí nebo vlastní stránky předlohy v seznamu služby SharePoint.  
  
     Pokud existující stránky předlohy je označena jako výchozí stránky předlohy nebo vlastní stránky předlohy, zobrazí se chyba nasazení, která uvádí, že stránka předlohy nelze odstranit. Chcete-li se tomuto problému vyhnout, postupujte takto:  
  
    -   Pokud existující stránky předlohy nastaven jako výchozí stránky předlohy, jiné stránky předlohy dočasně nastavte jako výchozí stránky předlohy. Poté, co nasadíte soubory do služby SharePoint, nastavte jako výchozí stránku předlohy nové stránky předlohy.  
  
    -   Pokud existující stránky předlohy nastaven jako vlastní stránky předlohy, dočasně nastavte jiné stránky předlohy jako vlastní stránky předlohy. Poté, co nasadíte soubory do služby SharePoint, nastavte nové stránky předlohy jako vlastní stránky předlohy.  
  
6.  Na řádku nabídek zvolte **sestavení**, **nasadit řešení**.  
  
7.  Otevřete web služby SharePoint k zobrazení nasazené položky.  
  
 Alternativní způsob k importu souborů do [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] a nasadit je do služby SharePoint je na přidání souborů do modulů v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)][Postupy: Import stránky předlohy nebo motivu](../sharepoint/how-to-import-a-master-page-or-theme.md) a [vložené soubory v řešení pomocí modulů](../sharepoint/using-modules-to-include-files-in-the-solution.md).  
  
## <a name="see-also"></a>Viz také  
 [Import položek z existující stránky SharePoint](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)   
 [Vytváření opakovaně použitelných ovládacích prvků pro webové části nebo stránky aplikací](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)  
  
  