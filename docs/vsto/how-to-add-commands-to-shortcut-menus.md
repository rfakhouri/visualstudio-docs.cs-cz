---
title: 'Postupy: přidávání příkazů do místních nabídek | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office menus, creating
- Office development in Visual Studio, context menus
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0d1bf0aee988e194b51220588a710a4b5b8d66ec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-commands-to-shortcut-menus"></a>Postupy: Přidávání příkazů do místních nabídek
  Toto téma ukazuje, jak přidat příkazy do místní nabídky v aplikaci Office pomocí doplňku VSTO.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
### <a name="to-add-commands-to-shortcut-menus-in-office"></a>Přidání příkazů do místní nabídky v Office  
  
1.  Přidat **XML karet** položky na úrovni dokumentu nebo projektu doplňku VSTO. Další informace najdete v tématu [postupy: získání spuštění přizpůsobení pásu karet](../vsto/how-to-get-started-customizing-the-ribbon.md). V  
  
2.  **Průzkumník řešení**, vyberte **ThisAddin.cs** nebo **ThisAddin.vb**.  
  
3.  Na řádku nabídek zvolte **zobrazení**, **kód**.  
  
     **ThisAddin** třída soubor se otevře v editoru kódu.  
  
4.  Přidejte následující kód, který **ThisAddin** třídy. Tento kód přepíše metodu CreateRibbonExtensibilityObject a vrátí třídy XML pásu karet do aplikace Office.  
  
     [!code-csharp[Trin_WordAddIn_Menus#1](../vsto/codesnippet/CSharp/trin_wordaddin_menus.cs/thisaddin.cs#1)]
     [!code-vb[Trin_WordAddIn_Menus#1](../vsto/codesnippet/VisualBasic/trin_wordaddin_menus.vb/thisaddin.vb#1)]  
  
5.  V **Průzkumníku**, vyberte soubor XML pásu karet. Ve výchozím nastavení je soubor XML karet s názvem Ribbon1.xml.  
  
6.  Na řádku nabídek zvolte **zobrazení**, **kód**.  
  
     Soubor xml pásu karet se otevře v editoru kódu.  
  
7.  V editoru kódu přidejte kód XML, který popisuje místní nabídky a ovládací prvek, který chcete přidat do místní nabídky.  
  
     Následující příklad přidá tlačítko, nabídky a řízení Galerie na místní nabídku pro dokument aplikace word. ID ovládacího prvku této místní nabídky je ContextMenuText. Úplný seznam řízení zástupce Office 2010 ID, která, najdete v části [soubory nápovědy Office 2010: Office Fluent uživatelské rozhraní ovládacího prvku identifikátory](http://go.microsoft.com/fwlink/?LinkID=181052).  
  
    ```  
    <?xml version="1.0" encoding="UTF-8"?>  
    <customUI xmlns="http://schemas.microsoft.com/office/2009/07/customui">  
      <contextMenus>  
        <contextMenu idMso="ContextMenuText">  
          <button id="MyButton" label="My Button" insertBeforeMso="HyperlinkInsert" onAction="GetButtonID" />  
          <menu id="MySubMenu" label="My Submenu" >  
            <button id="MyButton2" label="Button on submenu" />  
          </menu>  
          <gallery id="galleryOne" label="My Gallery">  
            <item id="item1" imageMso="HappyFace" />  
            <item id="item2" imageMso="HappyFace" />  
            <item id="item3" imageMso="HappyFace" />  
            <item id="item4" imageMso="HappyFace" />  
          </gallery>  
        </contextMenu>  
      </contextMenus>  
    </customUI>  
    ```  
  
8.  V **Průzkumníku řešení**, zvolte **MyRibbon.cs** nebo **MyRibbon.vb**.  
  
9. Přidat metody zpětného volání k `Ribbon1` třídu pro každý ovládací prvek, který chcete zpracovat.  
  
     Následující metoda zpracovává zpětného volání **Moje tlačítko** tlačítko. Tento kód přidá řetězec do aktivního dokumentu v aktuálním umístění kurzor.  
  
     [!code-vb[Trin_WordAddIn_Menus#2](../vsto/codesnippet/VisualBasic/trin_wordaddin_menus.vb/ribbon1.vb#2)]
     [!code-csharp[Trin_WordAddIn_Menus#2](../vsto/codesnippet/CSharp/trin_wordaddin_menus.cs/ribbon1.cs#2)]  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [Návod: Vytváření místních nabídek pro záložky](../vsto/walkthrough-creating-shortcut-menus-for-bookmarks.md)   
 [Volitelné parametry v řešeních pro systém Office](../vsto/optional-parameters-in-office-solutions.md)   
 [Přizpůsobení kontextové nabídky v Office 2010](http://go.microsoft.com/fwlink/?LinkId=182186)  
  
  