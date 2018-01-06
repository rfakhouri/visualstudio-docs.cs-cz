---
title: "Návod: Vytvoření webové části pro službu SharePoint | Microsoft Docs"
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
- VB
- CSharp
helpviewer_keywords:
- Web Parts [SharePoint development in Visual Studio], developing
- Web Parts [SharePoint development in Visual Studio], creating
- Web Parts [SharePoint development in Visual Studio], designing
ms.assetid: 51fb5bdd-b99c-4716-83bc-e66a5da15169
caps.latest.revision: "34"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 3a580d662c09e0f8a73deca2c4e0cea7cea6650c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-web-part-for-sharepoint"></a>Návod: Vytvoření webové části pro službu SharePoint
  Webové části umožňují uživatelům přímo upravit obsah, vzhled a chování stránek webu služby SharePoint pomocí prohlížeče. Tento postup vám ukáže postup vytvoření webové části pomocí **webovou část** šablony položky v sadě Visual Studio 2010.  
  
 Webová část zobrazuje zaměstnanci v datové mřížce. Uživatel Určuje umístění souboru, který obsahuje data zaměstnance. Uživatele můžete také filtrovat mřížky dat tak, aby zaměstnanci, kteří jsou správci zobrazí v seznamu jenom.  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytvoření webové části pomocí sady Visual Studio **webovou část** šablony položky.  
  
-   Vytvoření vlastnosti, které lze nastavit uživatelem webové části. Tato vlastnost určuje umístění datového souboru zaměstnanců.  
  
-   Vykreslování obsahu ve webové části přidáním ovládacích prvků do webové části ovládací prvky kolekce.  
  
-   Vytvoření nové položky nabídky, označuje jako *operace,* které se zobrazí v nabídce operací vykreslené webové části. Příkazy Povolit uživateli měnit data, která se zobrazí ve webové části.  
  
-   Testování webové části služby SharePoint.  
  
    > [!NOTE]  
    >  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   Podporované edice systému Microsoft Windows a služby SharePoint. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!INCLUDE[vs_pro_current_short](../sharepoint/includes/vs-pro-current-short-md.md)]nebo edici nástroje Visual Studio Application Lifecycle Management (ALM).  
  
## <a name="creating-an-empty-sharepoint-project"></a>Vytváření prázdného projektu služby SharePoint  
 Nejprve vytvořte projektu služby SharePoint prázdný. Později, bude přidat webovou část na projekt pomocí **webovou část** šablony položky.  
  
#### <a name="to-create-an-empty-sharepoint-project"></a>K vytvoření prázdného projektu služby SharePoint  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] pomocí **spustit jako správce** možnost.  
  
2.  Na panelu muže zvolte **soubor**, **nový**, **projektu**.  
  
3.  V **nový projekt** dialogové okno, rozbalte seznam **SharePoint** uzel v jazyce, který chcete použít a potom vyberte **2010** uzlu.  
  
4.  V **šablony** podokně vyberte **projektu služby SharePoint 2010**a potom zvolte **OK** tlačítko.  
  
     **Průvodce vlastním nastavením SharePoint** se zobrazí. Tento průvodce umožňuje vyberte lokalitu, která budete používat k ladění projektu a úroveň důvěryhodnosti řešení.  
  
5.  Vyberte **nasadit jako řešení farmy** možnost tlačítko a potom vyberte **Dokončit** tlačítko přijmout výchozí místní web služby SharePoint.  
  
## <a name="adding-a-web-part-to-the-project"></a>Přidání webové části do projektu  
 Přidat **webovou část** položku do projektu. **Webovou část** položky přidá k souboru kódu webové části. Později přidáte kód do souboru kódu webové části vykreslení obsahu webové části.  
  
#### <a name="to-add-a-web-part-to-the-project"></a>Chcete-li přidat webovou část do projektu  
  
1.  Na řádku nabídek zvolte **projektu**, **přidat novou položku**.  
  
2.  V **přidat novou položku** v dialogovém **nainstalovaných šablonách** podokně rozbalte **SharePoint** uzel a potom zvolte **2010** uzlu.  
  
3.  V seznamu šablon služby SharePoint, vyberte **webovou část** šablony a potom zvolte **přidat** tlačítko.  
  
     **Webovou část** položka se zobrazí v **Průzkumníku řešení**.  
  
## <a name="rendering-content-in-the-web-part"></a>Vykreslování obsahu ve webové části  
 Můžete zadat ovládacích prvků, které se má zobrazit ve webové části jejich přidáním do kolekce ovládacích prvků třídy webové části.  
  
#### <a name="to-render-content-in-the-web-part"></a>K vykreslení obsahu ve webové části  
  
1.  V **Průzkumníku**, otevřete WebPart1.vb (v jazyce Visual Basic) nebo WebPart1.cs (v jazyku C#).  
  
     Webová část kódu soubor se otevře v editoru kódu.  
  
2.  Přidejte následující příkazy na začátek souboru kódu webové části.  
  
     [!code-csharp[SP_WebPart#1](../sharepoint/codesnippet/CSharp/spext_webpart/webpart1/webpart1.cs#1)]
     [!code-vb[SP_WebPart#1](../sharepoint/codesnippet/VisualBasic/spext_webpart/webpart1/webpart1.vb#1)]  
  
3.  Přidejte následující kód, který `WebPart1` třídy. Tento kód deklaruje následující pole:  
  
    -   Datová mřížka zobrazíte zaměstnanci ve webové části.  
  
    -   Text, který se zobrazí na ovládací prvek, který se používá k filtrování dat mřížky.  
  
    -   Popisek, který zobrazí chybu, pokud nemůže zobrazit data dat mřížky.  
  
    -   Řetězec, který obsahuje cestu k souboru dat zaměstnanců.  
  
     [!code-csharp[SP_WebPart#2](../sharepoint/codesnippet/CSharp/spext_webpart/webpart1/webpart1.cs#2)]
     [!code-vb[SP_WebPart#2](../sharepoint/codesnippet/VisualBasic/spext_webpart/webpart1/webpart1.vb#2)]  
  
4.  Přidejte následující kód, který `WebPart1` třídy. Tento kód přidá vlastní vlastnost s názvem `DataFilePath` do webové části. Vlastní vlastnost je vlastnost, která lze nastavit ve službě SharePoint uživatelem. Tato vlastnost získá a nastaví umístění datového souboru XML, který se používá k naplnění dat mřížky.  
  
     [!code-csharp[SP_WebPart#3](../sharepoint/codesnippet/CSharp/spext_webpart/webpart1/webpart1.cs#3)]
     [!code-vb[SP_WebPart#3](../sharepoint/codesnippet/VisualBasic/spext_webpart/webpart1/webpart1.vb#3)]  
  
5.  Nahraďte `CreateChildControls` metoda následujícím kódem. Tento kód provede následující:  
  
    -   Přidá datové mřížce a štítek, který je deklarován v předchozím kroku.  
  
    -   Datová mřížka váže k souboru XML, který obsahuje data zaměstnance.  
  
     [!code-csharp[SP_WebPart#4](../sharepoint/codesnippet/CSharp/spext_webpart/webpart1/webpart1.cs#4)]
     [!code-vb[SP_WebPart#4](../sharepoint/codesnippet/VisualBasic/spext_webpart/webpart1/webpart1.vb#4)]  
  
6.  Přidejte následující metodu do `WebPart1` třídy. Tento kód provede následující:  
  
    -   Vytvoří akci, která se zobrazí v nabídce webové části operací vykreslené webové části.  
  
    -   Zpracovává událost, která se vyvolá, když uživatel vybere příkaz v nabídce Akce. Tento kód vyfiltruje seznam zaměstnanci, který se zobrazí v datové mřížce.  
  
     [!code-csharp[SP_WebPart#5](../sharepoint/codesnippet/CSharp/spext_webpart/webpart1/webpart1.cs#5)]
     [!code-vb[SP_WebPart#5](../sharepoint/codesnippet/VisualBasic/spext_webpart/webpart1/webpart1.vb#5)]  
  
## <a name="testing-the-web-part"></a>Testování webové části  
 Když spouštíte projekt, otevře se web služby SharePoint. Webová část je automaticky přidá do Galerie webových částí služby SharePoint. Můžete přidat webovou část na stránku všechny webové části.  
  
#### <a name="to-test-the-web-part"></a>K otestování webové části  
  
1.  Vložte následující kód XML do souboru poznámkového bloku. Tento soubor XML obsahuje ukázková data, která se zobrazí ve webové části.  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
        <employees xmlns="http://schemas.microsoft.com/vsto/samples">  
           <employee>  
               <name>David Hamilton</name>  
               <hireDate>2001-05-11</hireDate>  
               <title>Sales Associate</title>  
           </employee>  
           <employee>  
               <name>Karina Leal</name>  
               <hireDate>1999-04-01</hireDate>  
               <title>Manager</title>  
           </employee>  
           <employee>  
               <name>Nancy Davolio</name>  
               <hireDate>1992-05-01</hireDate>  
               <title>Sales Associate</title>  
           </employee>  
           <employee>  
               <name>Steven Buchanan</name>  
               <hireDate>1955-03-04</hireDate>  
               <title>Manager</title>  
           </employee>  
           <employee>  
               <name>Suyama Michael</name>  
               <hireDate>1963-07-02</hireDate>  
               <title>Sales Associate</title>  
           </employee>  
        </employees>  
    ```  
  
2.  V poznámkovém bloku na řádku nabídek zvolte **soubor**, **uložit jako**.  
  
3.  V **uložit jako** dialogu **uložit jako typ** vyberte **všechny soubory**.  
  
4.  V **název souboru** zadejte **data.xml**.  
  
5.  Zvolte libovolné složky pomocí **procházet složky** tlačítko a potom vyberte **Uložit** tlačítko.  
  
6.  Ve Visual Studiu zvolte **F5** klíč.  
  
     Otevře se stránka serveru SharePoint.  
  
7.  Na **Akce webu** nabídce zvolte **další možnosti**.  
  
8.  V **vytvořit** vyberte **webová část** typ, a potom vyberte **vytvořit** tlačítko.  
  
9. V **nová stránka webových částí** stránky, zadejte název stránky **SampleWebPartPage.aspx**a potom zvolte **vytvořit** tlačítko.  
  
     Zobrazí se stránka webové části.  
  
10. Vyberte všechny zóny na stránku webové části.  
  
11. V horní části stránky, vyberte **vložit** a pak klikněte na příkaz **webovou část** tlačítko.  
  
12. V **kategorie** podokně, vyberte **vlastní** složky, vyberte **WebPart1** webovou část a potom vyberte **přidat** tlačítko.  
  
     Na stránce se zobrazí webová část.  
  
## <a name="testing-the-custom-property"></a>Testování vlastní vlastnosti  
 K naplnění dat mřížky, který se zobrazí ve webové části, zadejte cestu souboru XML, který obsahuje data o zaměstnanci.  
  
#### <a name="to-test-the-custom-property"></a>Chcete-li otestovat vlastní vlastnosti  
  
1.  Vyberte šipku, která se zobrazí na pravé straně webové části a potom vyberte **upravit webovou část** v nabídce, která se zobrazí.  
  
     Na pravé straně stránky se zobrazí panel, který obsahuje vlastnosti pro webové části.  
  
2.  V podokně rozbalte **různé** uzlu, zadejte cestu k souboru XML, který jste vytvořili dříve, vyberte **použít** tlačítko a potom vyberte **OK** tlačítko.  
  
     Ověřte, že zaměstnanci objeví ve webové části.  
  
## <a name="testing-the-web-part-verb"></a>Testování příkaz webové části  
 Zobrazení a skrytí zaměstnanci, kteří nejsou správci kliknutím na položku, která se zobrazí v nabídce operací webové části.  
  
#### <a name="to-test-the-web-part-verb"></a>K otestování příkazem webové části  
  
1.  Vyberte šipku, která se zobrazí na pravé straně webové části a potom vyberte **zobrazit pouze správci** v nabídce, která se zobrazí.  
  
     Pouze zaměstnanci, kteří jsou správci zobrazí ve webové části.  
  
2.  Vyberte šipku znovu a potom vyberte **zobrazit všechny zaměstnance** v nabídce, která se zobrazí.  
  
     Všechny zaměstnance se zobrazí ve webové části.  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření webové části pro službu SharePoint](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [Postupy: vytvoření webové části služby SharePoint](../sharepoint/how-to-create-a-sharepoint-web-part.md)   
 [Postupy: vytvoření webové části služby SharePoint pomocí návrháře](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)   
 [Návod: Vytvoření webové části pro službu SharePoint pomocí návrháře](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)  
  
  