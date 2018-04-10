---
title: Vytvoření kategorie nastavení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- profile settings, creating categories
ms.assetid: 97c88693-05ff-499e-8c43-352ee073dcb7
caps.latest.revision: 39
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 2bdf3231f2df8b3700c7865fa53e60003b814a5f
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="creating-a-settings-category"></a>Vytvoření kategorie nastavení
V tomto názorném postupu vytvořit kategorii nastavení sady Visual Studio a používat k uložení hodnot a obnovení hodnoty z nastavení souboru. Kategorie nastavení je skupina souvisejících vlastností, které se zobrazují jako "bod vlastní nastavení;" To znamená jako zaškrtávací políčko v **Import a export nastavení** průvodce. (Najdete na **nástroje** nabídky.) Nastavení jsou uložena ani obnoveny v kategorii a jednotlivých nastavení nezobrazují v průvodci. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
 Můžete vytvořit kategorii nastavení odvozené z <xref:Microsoft.VisualStudio.Shell.DialogPage> třídy.  
  
 Pokud chcete spustit Tento názorný postup, musíte nejdřív dokončit první část [vytváření stránku možnosti](../extensibility/creating-an-options-page.md). Výsledný mřížkou vlastností možnosti umožňuje zkontrolovat a změnit vlastnosti v kategorii. Po uložení vlastnost kategorie v souboru nastavení, můžete zkontrolovat soubor zobrazíte ukládání hodnot vlastností.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-settings-category"></a>Vytvoření kategorie nastavení  
 V této části použijte vlastní nastavení bodu k uložení a obnovení hodnoty kategorie nastavení.  
  
#### <a name="to-create-a-settings-category"></a>Chcete-li vytvořit kategorie nastavení  
  
1.  Dokončení [vytváření stránku možnosti](../extensibility/creating-an-options-page.md).  
  
2.  Otevřete soubor VSPackage.resx a přidejte tyto tři řetězcové prostředky:  
  
    |Název|Hodnota|  
    |----------|-----------|  
    |106|Moje kategorie|  
    |107|Nastavení|  
    |108|OptionInteger a OptionFloat|  
  
     Tím se vytvoří prostředky tento název kategorie "Moje kategorie", "My nastavení objektu" a popis kategorie "A OptionInteger OptionFloat".  
  
    > [!NOTE]
    >  Z těchto tří pouze název kategorie nezobrazí v Průvodci nastavení importu a exportu.  
  
3.  V MyToolsOptionsPackage.cs, přidejte `float` vlastnost s názvem `OptionFloat` k `OptionPageGrid` třídy, jak je znázorněno v následujícím příkladu.  
  
    ```csharp  
    public class OptionPageGrid : DialogPage  
    {  
        private int optionInt = 256;  
        private float optionFloat = 3.14F;  
  
        [Category("My Options")]  
        [DisplayName("My Integer option")]  
        [Description("My integer option")]  
        public int OptionInteger  
        {  
            get { return optionInt; }  
            set { optionInt = value; }  
        }  
        [Category("My Options")]  
        [DisplayName("My Float option")]  
        [Description("My float option")]  
        public float OptionFloat  
        {  
            get { return optionFloat; }  
            set { optionFloat = value; }  
        }  
    }  
    ```  
  
    > [!NOTE]
    >  `OptionPageGrid` Kategorie s názvem "Moje kategorie" teď se skládá ze dvou vlastností `OptionInteger` a `OptionFloat`.  
  
4.  Přidat <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> k `MyToolsOptionsPackage` třídy a pojmenujte ho CategoryName "Moje kategorie", poskytněte ObjectName "Moje nastavení" a nastavte isToolsOptionPage na hodnotu true. Nastavte categoryResourceID, objectNameResourceID a DescriptionResourceID na odpovídající prostředek řetězec, který ID vytvořili dříve.  
  
    ```csharp  
    [ProvideProfileAttribute(typeof(OptionPageGrid),   
        "My Category", "My Settings", 106, 107, isToolsOptionPage:true, DescriptionResourceID = 108)]  
    ```  
  
5.  Sestavte projekt a spusťte ladění. V experimentální instanci byste měli vidět, **stránku mřížky** má nyní hodnoty celé číslo a float.  
  
## <a name="examining-the-settings-file"></a>Nastavení souboru  
 V této části exportovat do souboru nastavení hodnot vlastností kategorie. Zkontrolujte v souboru a poté importovat hodnoty zpět do kategorie vlastnost.  
  
1.  Stisknutím klávesy F5 spusťte projekt v režimu ladění. Spustí se experimentální instanci.  
  
2.  Otevřete **Nástroje / možnosti** dialogové okno.  
  
3.  Ve stromovém zobrazení v levém podokně rozbalte **Moje kategorie** a pak klikněte na **stránku mřížky**.  
  
4.  Změňte hodnotu **OptionFloat** k 3.1416 a **OptionInteger** do 12. Click **OK**.  
  
5.  Na **nástroje** nabídky, klikněte na tlačítko **nastavení importu a exportu**.  
  
     **Nastavení importu a exportu** zobrazí se průvodce.  
  
6.  Zajistěte, aby **Export vybrané nastavení prostředí** je vybrána a potom klikněte na **Další**.  
  
     **Zvolte nastavení pro Export** se zobrazí stránka.  
  
7.  Klikněte na tlačítko **nastavení**.  
  
     **Popis** změny **OptionInteger a OptionFloat**.  
  
8.  Ujistěte se, že **Moje nastavení** je pouze kategorii, která je vybrána a potom klikněte na **Další**.  
  
     **Názvu souboru nastavení** se zobrazí stránka.  
  
9. Pojmenujte nový soubor s nastaveními `MySettings.vssettings` a uložit je do příslušného adresáře. Klikněte na tlačítko **Dokončit**.  
  
     **Exportovat dokončení** stránky sestavy, aby byly úspěšně exportovány nastavení.  
  
10. Na **soubor** nabídky, přejděte na příkaz **otevřete**a potom klikněte na **soubor**. Vyhledejte `MySettings.vssettings` a otevřete ji.  
  
     Můžete najít vlastnost kategorie, které jste exportovali v následující části souboru (vaše identifikátory GUID se budou lišit).  
  
    ```  
    <Category name="My Category_My Settings"   
          Category="{4802bc3e-3d9d-4591-8201-23d1a05216a6}"   
          Package="{6bb6942e-014c-489e-a612-a935680f703d}"   
          RegisteredName="My Category_My Settings">  
          PackageName="MyToolsOptionsPackage">  
       <PropertyValue name="OptionFloat">3.1416</PropertyValue>   
       <PropertyValue name="OptionInteger">12</PropertyValue>   
    </Category>  
    ```  
  
     Všimněte si, název úplné kategorie je tvořen přidání podtržítkem pro název kategorie, za nímž následuje název objektu. OptionFloat a OptionInteger se zobrazí v kategorii, spolu s jejich exportovaný hodnoty.  
  
11. Zavřete soubor s nastaveními bez provedení změn.  
  
12. Na **nástroje** nabídky, klikněte na tlačítko **možnosti**, rozbalte položku **Moje kategorie**, klikněte na tlačítko **stránku mřížky** a poté změňte hodnotu  **OptionFloat** 1.0 a **OptionInteger** na 1. Click **OK**.  
  
13. Na **nástroje** nabídky, klikněte na tlačítko **nastavení importu a exportu**, vyberte **importovat vybrané nastavení prostředí**a potom klikněte na **Další**.  
  
     **Uložit aktuální nastavení** se zobrazí stránka.  
  
14. Vyberte **Ne, přímo importovat nové nastavení** a pak klikněte na **Další**.  
  
     **Vybrat kolekce nastavení pro Import** se zobrazí stránka.  
  
15. Vyberte `MySettings.vssettings` v soubor **Moje nastavení** uzlu stromovém zobrazení. Pokud soubor ve stromovém zobrazení nezobrazí, klikněte na tlačítko **Procházet** a ji najít. Klikněte na tlačítko **Další**.  
  
     **Zvolte nastavení pro Import** zobrazí se dialogové okno.  
  
16. Ujistěte se, že **Moje nastavení** je vybrána a potom klikněte na **Dokončit**. Když **úplný Import** stránky se zobrazí, klikněte na tlačítko **Zavřít**.  
  
17. Na **nástroje** nabídky, klikněte na tlačítko **možnosti**, rozbalte položku **Moje kategorie**, klikněte na tlačítko **stránku mřížky** a ověřte, že hodnoty vlastností kategorie byla obnovena.