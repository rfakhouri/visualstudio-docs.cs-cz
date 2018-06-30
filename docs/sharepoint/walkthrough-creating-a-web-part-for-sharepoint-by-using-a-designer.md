---
title: 'Návod: Vytvoření webové části pro službu SharePoint pomocí návrháře | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- Web Parts [SharePoint development in Visual Studio], designer
- Web Parts [SharePoint development in Visual Studio], creating
- Web Parts [SharePoint development in Visual Studio], designing
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 01efc1972ea4833900b5e6f002d36ae51fa63a85
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37120180"
---
# <a name="walkthrough-create-a-web-part-for-sharepoint-by-using-a-designer"></a>Návod: Vytvoření webové části pro službu SharePoint pomocí návrháře

Pokud vytvoříte webové části pro web služby SharePoint, vaši uživatelé můžete přímo upravit obsah, vzhled a chování stránek v dané lokalitě pomocí prohlížeče. Tento postup vám ukáže, jak vytvořit webovou část vizuálně pomocí webu služby SharePoint **Visual webovou část** šablona projektu v sadě Visual Studio.

Webová část, která vytvoříte zobrazí měsíční kalendář zobrazení a zaškrtávací políčko pro každý seznam kalendáře na webu. Uživatelé mohou určit uvádí kalendář, který Pokud chcete zahrnout do zobrazení měsíční kalendář zaškrtnutím políčka.

Tento návod znázorňuje následující úlohy:

- Vytvoření webové části pomocí **Visual webovou část** šablona projektu.
- Návrh webové části pomocí návrháře Visual Web Developer v sadě Visual Studio.
- Přidání kódu pro zpracování události ovládacích prvků na webové části.
- Testování webové části služby SharePoint.

    > [!NOTE]
    > Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění pro některé prvky uživatelského rozhraní pro sadu Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. V tématu [přizpůsobení sady Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).

## <a name="prerequisites"></a>Požadavky

K dokončení tohoto návodu budete potřebovat následující komponenty:

- Podporované edice systému Windows a služby SharePoint. V tématu [požadavky na vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).

## <a name="create-a-web-part-project"></a>Vytvoření projektu webové části

Nejprve vytvořte projekt webové části pomocí **Visual webovou část** šablona projektu.

1. Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] pomocí **spustit jako správce** možnost.

2. Na řádku nabídek zvolte **soubor** > **nový** > **projektu**.

     **Nový projekt** zobrazí se dialogové okno.

3. V **nový projekt** dialogové okno, v části buď **Visual C#** nebo **jazyka Visual Basic**, rozbalte položku **Office/SharePoint**a potom vyberte  **Řešení služby SharePoint** kategorie.

4. V seznamu šablon, vyberte **SharePoint 2013 – webová část Visual** šablony a potom zvolte **OK** tlačítko.

     **Průvodce vlastním nastavením SharePoint** se zobrazí. Pomocí tohoto průvodce můžete zadat web, který budete používat k ladění projektu a úroveň důvěryhodnosti řešení.

5. V **co je úrovně důvěryhodnosti pro toto řešení služby SharePoint?** zvolte **nasadit jako řešení farmy** tlačítko.

6. Vyberte **Dokončit** tlačítko přijmout výchozí místní web služby SharePoint.

## <a name="designing-the-web-part"></a>Navrhování webové části

Návrh webové části přidáním ovládacích prvků z **sada nástrojů** na plochu návrháře Visual Web Developer.

1. V aplikaci Visual Web Developer, zvolte **návrhu** tab přepněte do zobrazení návrhu.

2. Na řádku nabídek zvolte **zobrazení** > **sada nástrojů**.

3. V **standardní** uzlu **sada nástrojů**, vyberte **CheckBoxList** řízení a poté proveďte jednu z následujících kroků:

    - Otevřete místní nabídku pro **CheckBoxList** řídit, zvolte **kopie**, otevřete místní nabídku pro první řádek v návrháři a potom zvolte **vložení**.

    - Přetáhněte **CheckBoxList** řídit z **sada nástrojů**a připojte se k první řádek v návrháři ovládacího prvku.

4. Opakujte předchozí krok, ale tlačítko přesunout na další řádek návrháře.

5. V návrháři, vyberte **Button1** tlačítko.

6. Na řádku nabídek zvolte **zobrazení** > **vlastnosti – okno**.

     **Vlastnosti** otevře se okno.

7. V **Text** vlastnost tlačítko, zadejte **aktualizace**.

## <a name="handling-the-events-of-controls-on-the-web-part"></a>Zpracování událostí ovládacích prvků na webové části

Přidejte kód, který umožňuje uživateli přidat kalendáře na zobrazení hlavní kalendáře.

1. Proveďte jednu z následujících sad kroků:

    - V návrháři, dvakrát klikněte **aktualizace** tlačítko.

    - V **vlastnosti** okna pro **aktualizace** tlačítko, vyberte **události** tlačítko. V **klikněte na tlačítko** vlastnost, zadejte **Button1_Click**a potom vyberte klávesu Enter.

     Soubor uživatelského ovládacího prvku kódu otevře v editoru kódu a `Button1_Click` obslužné rutiny události se zobrazí. Kód budete později, přidáte do této obslužné rutiny události.

2. Přidejte následující příkazy na začátek souboru uživatelského ovládacího prvku kódu.

     [!code-vb[SP_VisualWebPart#1](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#1)]
     [!code-csharp[SP_VisualWebPart#1](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#1)]

3. Přidejte následující řádek kódu `VisualWebPart1` třídy. Tento kód deklaruje zobrazení ovládacího prvku měsíční kalendář.

     [!code-vb[SP_VisualWebPart#2](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#2)]
     [!code-csharp[SP_VisualWebPart#2](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#2)]

4. Nahraďte `Page_Load` metodu `VisualWebPart1` třídy následujícím kódem. Tento kód provede následující:

    - Přidá do uživatelského ovládacího prvku měsíční kalendář zobrazení.

    - Přidá zaškrtávací políčko pro každý seznam kalendáře na webu.

    - Určuje šablonu pro každý typ položky, který se zobrazí v zobrazení kalendáře.

     [!code-vb[SP_VisualWebPart#3](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#3)]
     [!code-csharp[SP_VisualWebPart#3](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#3)]

5. Nahraďte `Button1_Click` metodu `VisualWebPart1` třídy následujícím kódem. Tento kód přidá položky z každé vybrané kalendáře na zobrazení hlavní kalendáře.

     [!code-vb[SP_VisualWebPart#4](../sharepoint/codesnippet/VisualBasic/sp_visualwebpart.vb/visualwebpart1/visualwebpart1usercontrol.ascx.vb#4)]
     [!code-csharp[SP_VisualWebPart#4](../sharepoint/codesnippet/CSharp/sp_visualwebpart.cs/visualwebpart1/visualwebpart1usercontrol.ascx.cs#4)]

## <a name="test-the-web-part"></a>Test webové části

Když spouštíte projekt, otevře se web služby SharePoint. Webová část je automaticky přidá do Galerie webových částí služby SharePoint. K otestování tohoto projektu, budete provádět následující úlohy:

- Přidání události pro každé dva seznamy samostatné kalendáře.
- Přidáte webovou část na stránku webové části.
- Zadejte seznamy, které chcete zahrnout do zobrazení měsíčního kalendáře.

### <a name="to-add-events-to-calendar-lists-on-the-site"></a>Přidání události do kalendáře seznamy na webu

1. Ve Visual Studiu zvolte **F5** klíč.

     Otevře se stránka serveru SharePoint a [!INCLUDE[wss_14_long](../sharepoint/includes/wss-14-long-md.md)] panel Snadné spuštění se zobrazí na stránce.

2. Na panelu Snadné spuštění pod **uvádí**, vyberte **kalendáře** odkaz.

     **Kalendáře** se zobrazí stránka.

     Pokud jste žádné kalendáře se zobrazí na panelu Snadné spuštění, vyberte **obsah webu** odkaz. Pokud se nezobrazí stránka obsah webu **kalendáře** položky, vytvořte ho.

3. Na stránce kalendář, zvolte den a potom zvolte **přidat** odkazu ve vybraný den přidat událost.

4. V **název** zadejte **událostí v kalendáři výchozí**a potom zvolte **Uložit** tlačítko.

5. Vyberte **obsah webu** propojit a potom zvolte **přidat aplikaci** dlaždici.

6. Na **vytvořit** vyberte **kalendáře** zadejte název kalendáře a pak zvolte **vytvořit** tlačítko.

7. Přidání události do kalendáře nového, název události **událostí ve vlastních kalendářů**a potom zvolte **Uložit** tlačítko.

### <a name="to-add-the-web-part-to-a-web-part-page"></a>Chcete-li přidat webovou část na stránku webové části

1. Na **obsah webu** otevřete **weby** složky.

2. Na pásu karet, vyberte **soubory** kartě, otevřete **nový dokument** nabídce a potom zvolte **webová část** příkaz.

3. Na **nová stránka webových částí** stránky, zadejte název stránky **SampleWebPartPage.aspx**a potom zvolte **vytvořit** tlačítko.

     Zobrazí se stránka webové části.

4. V horní zóně část webové stránky, vyberte **vložit** a pak klikněte na příkaz **webovou část** tlačítko.

5. Vyberte **vlastní** složky, vyberte **VisualWebPart1** webovou část a potom vyberte **přidat** tlačítko.

     Na stránce se zobrazí webová část. Na webové části se zobrazí následující prvky:

    - Měsíční kalendář zobrazení.

    - **Aktualizace** tlačítko.

    - A **kalendáře** zaškrtávací políčko.

    - A **vlastní kalendáře** zaškrtávací políčko.

### <a name="to-specify-lists-to-include-in-the-monthly-calendar-view"></a>Chcete-li určit uvádí Pokud chcete zahrnout do zobrazení měsíční kalendář

Ve webové části zadejte kalendářích, které chcete zahrnout do zobrazení měsíční kalendář a potom vyberte **aktualizace** tlačítko.

Události ze všech kalendářů, které jste zadali se zobrazí v zobrazení měsíčního kalendáře.

## <a name="see-also"></a>Viz také:

[Vytvoření webové části pro službu SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)  
[Postupy: vytvoření webové části služby SharePoint](../sharepoint/how-to-create-a-sharepoint-web-part.md)  
[Návod: Vytvoření webové části pro službu SharePoint](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint.md)
