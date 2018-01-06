---
title: "Návod: Vytvoření sloupce webu, typu obsahu a seznamu pro službu SharePoint | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.SharePointTools.ListDesigner.GeneralMessageHelp
- Microsoft.VisualStudio.SharePoint.Designers.ListDesigner.ViewModels.ListViewModel.SortingAndGrouping
- VS.SharePointTools.ListDesigner.SortingGrouping
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, list definitions
- SharePoint development in Visual Studio, list instances
- SharePoint development in Visual Studio, fields
- SharePoint development in Visual Studio, content types
ms.assetid: caebacc2-616c-4373-8e21-edc7979338e7
caps.latest.revision: "54"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 59dafe640428059b4c6772f79a23d5f0ccceaac7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-create-a-site-column-content-type-and-list-for-sharepoint"></a>Návod: Vytvoření sloupce webu, typu obsahu a seznamu pro službu SharePoint
  Následující postupy ukazují, jak vytvořit vlastní sloupců webu služby SharePoint – nebo *pole*– a také typ obsahu, který používá sloupců webu. Také ukazuje, jak můžete vytvořit seznam, který používá nový typ obsahu.  
  
 Tento návod zahrnuje následující úlohy:  
  
-   [Vytváření sloupců webu vlastní](#BKMK_CreatingCustSiteCols).  
  
-   [Vytvoření vlastního obsahu typu](#BKMK_CreateCustContType).  
  
-   [Vytvoření seznamu](#BKMK_CreateList).  
  
-   [Vytvoření seznamu](#BKMK_CreateList).  
  
-   [Testování aplikace](#BKMK_TestApp).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   Podporované edice systému Windows a služby SharePoint. Další informace najdete v tématu [požadavky pro vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   Visual Studio.  
  
##  <a name="BKMK_CreatingCustSiteCols"></a>Vytváření sloupců vlastního webu  
 Tento příklad vytvoří seznam pro správu pacientů v nemocnice. Nejprve musíte vytvořit projektu služby SharePoint v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] a přidat sloupce webu, následujícím způsobem.  
  
#### <a name="to-create-the-project"></a>Vytvoření projektu  
  
1.  Na [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] **soubor** nabídce zvolte **nový**, **projektu**.  
  
2.  V **nový projekt** dialogové okno, v části buď **Visual C#** nebo **jazyka Visual Basic**, rozbalte **SharePoint** uzel a potom zvolte **2010**.  
  
3.  V **šablony** podokně vyberte **projektu služby SharePoint 2010**, změňte název projektu do **Klinika**a potom zvolte **OK** tlačítko.  
  
     Šablona projektu služby SharePoint 2010 je prázdný projekt, který se používá v tomto příkladu obsahovat sloupce webu a další položky projektu, které jsou přidány později.  
  
4.  Na **zadejte úroveň lokality a zabezpečení pro ladění** stránky, zadejte adresu URL pro místní web služby SharePoint, do které chcete přidat novou položku vlastní pole nebo použijte výchozí umístění (`http://<`*SystemName* `>/)`.  
  
5.  V **co je úrovně důvěryhodnosti pro toto řešení služby SharePoint?** část, použijte výchozí hodnotu **nasadit jako řešení v izolovaném prostoru**.  
  
     Další informace o v izolovaném prostoru a řešení farmy najdete v tématu [v izolovaném prostoru aspekty řešení](../sharepoint/sandboxed-solution-considerations.md).  
  
6.  Vyberte **Dokončit** tlačítko. Projekt by měl být teď uvedený v **Průzkumníku řešení**.  
  
#### <a name="to-add-site-columns"></a>Chcete-li přidat sloupce webu  
  
1.  Přidáte nový sloupec webu. Chcete-li to provést, v **Průzkumníku řešení**, otevřete místní nabídku pro **Klinika**a potom zvolte **přidat**, **novou položku**.  
  
2.  V **přidat novou položku** dialogovém okně vyberte **sloupec lokality**, změňte název **pacienta název**a potom zvolte **přidat** tlačítko.  
  
3.  V souboru Elements.xml sloupec lokality, ponechte **typ** nastavení jako **Text**a změňte **skupiny** nastavení **sloupců webu Klinika**. Po dokončení soubor Elements.xml sloupec lokality by měl vypadat jako v následujícím příkladu.  
  
    ```  
    <Field  
         ID="{f9ba60d1-5631-41fb-b016-a38cf48eef63}"  
         Name="Clinic - Patient Name"  
         DisplayName="Patient Name"  
         Type="Text"  
         Required="FALSE"  
         Group="Clinic Site Columns">  
    </Field>  
    ```  
  
4.  Další dva sloupce webu pomocí stejného postupu, přidejte do projektu: **pacienta ID** (typ = "Celé číslo") a **Doctor název** (typ = "Text"). Nastavte na hodnotu jejich skupiny **sloupců webu Klinika**.  
  
##  <a name="BKMK_CreateCustContType"></a>Vytváření vlastní typ obsahu.  
 Dále vytvořte typ obsahu – na základě typu obsahu Kontakty – obsahující sloupce webu, které jste vytvořili v předchozím postupu. Typ obsahu založit na existující typ obsahu, můžete ušetřit čas, protože základní typ obsahu poskytuje několik sloupců webu pro použití v nový typ obsahu.  
  
#### <a name="to-create-a-custom-content-type"></a>Chcete-li vytvořit vlastní typ obsahu.  
  
1.  Typ obsahu přidáte k projektu. Chcete-li to provést, v **Průzkumníku**, vyberte uzel projektu  
  
2.  Na řádku nabídek zvolte **projektu**, **přidat novou položku**.  
  
3.  V části buď **Visual C#** nebo **jazyka Visual Basic**, rozbalte **SharePoint** uzel a potom vyberte **2010** uzlu.  
  
4.  V **šablony** podokně, vyberte **typ obsahu** šablony, změňte název **pacienta informace**a potom zvolte **přidat** tlačítko.  
  
     **Průvodce vlastním nastavením SharePoint** otevře.  
  
5.  V **které základní obsahu typ měli tento typ obsahu dědit z** vyberte **kontaktujte** jako typ obsahu, na které chcete vytvořit nový typ obsahu a potom vyberte **Dokončit**tlačítko.  
  
     Tato funkce umožňuje přístup k jiné sloupce potenciálně užitečné webu v obraťte se na typ obsahu, kromě sloupců webu, které jste definovali dříve.  
  
6.  Po typ obsahu designer se zobrazí v **sloupce** přidejte jsou tři sloupce, které jste definovali dříve lokality: **pacienta název**, **pacienta ID**a **Doctor název**. Přidat tyto sloupce, vyberte v seznamu sloupců lokality pod první pole se seznamem **zobrazovaný název**a potom vyberte sloupec každé lokality v seznamu, jeden v čase.  
  
    > [!TIP]  
    >  Chcete-li zvolit sloupce webu rychleji, filtrovat seznam tak, že zadáte několik prvních písmen názvu sloupce.  
  
7.  Kromě tři sloupce vlastního webu, přidejte **komentáře** sloupec webu ze seznamu sloupců lokality.  
  
8.  Vyberte **požadované** políčko u **pacienta název** a **pacienta ID** sloupců webu, aby byly požadovaná pole.  
  
9. Na **typ obsahu** a ujistěte se, zda je název typu obsahu **pacienta informace**a poté změňte popis na **kartu s informacemi o pacientech**.  
  
10. Změna **název skupiny** k **typy obsahu Klinika**a nechte ostatní nastavení na jejich výchozí hodnoty.  
  
11. Na řádku nabídek zvolte **soubor**, **Uložit vše**a pak zavřete Editor typ obsahu.  
  
##  <a name="BKMK_CreateList"></a>Vytvoření seznamu  
 Teď vytvořte seznam, který používá nové obsahu sloupce typu a lokality.  
  
#### <a name="to-create-a-list"></a>Můžete vytvořit seznam  
  
1.  Seznam přidejte do projektu. Chcete-li to provést, v **Průzkumníku**, vyberte uzel projektu.  
  
2.  Na řádku nabídek zvolte **projektu**, **přidat novou položku**.  
  
3.  V části buď **Visual C#** nebo **jazyka Visual Basic**, rozbalte **SharePoint** uzel a potom vyberte **2010** uzlu.  
  
4.  V **šablony** podokně, vyberte **seznamu** šablony, změňte název **pacientů**a potom zvolte **přidat** tlačítko.  
  
5.  Ponechte **přizpůsobit seznam na základě** nastavení jako **výchozí (prázdný)**a potom zvolte **Dokončit** tlačítko.  
  
6.  V Návrháři seznamu zvolte **typy obsahu** tlačítko pro zobrazení **nastavení typu obsahu** dialogové okno.  
  
7.  Zvolte nový řádek, vyberte **pacienta informace** obsahu typu v seznamu typů obsahu a potom vyberte **OK** tlačítko.  
  
     Díky tomuto přidá všechny sloupce lokality z **pacienta informace** typ do seznamu obsahu.  
  
8.  Odstraňte všechny sloupce webu v seznamu s těmito výjimkami:  
  
    -   Pacienta ID  
  
    -   Jméno pacienta  
  
    -   Telefon domů  
  
    -   E-mailu  
  
    -   Název Doctor  
  
    -   Komentáře  
  
9. V části **zobrazovaný název sloupce**, zvolte prázdný řádek, přidejte vlastní seznamu sloupec a pojmenujte ji **měla nemocnice**. Ponechat jeho datového typu jako **jeden řádek textu**.  
  
     Sloupec vlastní seznamu se vztahuje pouze na tomto seznamu. Když přidáte vlastní seznamu sloupec do seznamu, je nový typ obsahu seznamu, včetně všech sloupců, které jsou přidány do seznamu a nastavit jako výchozí seznam.  
  
    > [!TIP]  
    >  Pokud si zvolíte sloupce ze seznamu sloupců webu, se používá existující sloupec webu. Ale pokud zadáte název hodnota sloupce bez výběr žádné sloupce v seznamu, sloupec vlastní seznamu je vytvořen, i v případě, že sloupec se stejným názvem již existuje v seznamu.  
  
     Volitelně můžete místo nastavení datový typ sloupce vlastní seznamu **jeden řádek textu**, můžete místo toho nastavit na datový typ pro tento sloupec na vyhledávání a jeho hodnoty by načíst z tabulky nebo jiného seznamu. Informace o vyhledávání sloupce najdete v tématu [seznamu vztahy v produktu SharePoint 2010](http://go.microsoft.com/fwlink/?LinkId=224994) a [vyhledávání a vztahy seznamu](http://go.microsoft.com/fwlink/?LinkID=224995).  
  
10. Vedle položky **pacienta ID** a **pacienta název** polí, vyberte **požadované** zaškrtávací políčko.  
  
11. Na **zobrazení** , zvolte prázdný řádek můžete vytvořit zobrazení. Zadejte **pacienta podrobnosti**.  
  
     Na **zobrazení** kartě můžete zadat sloupce, které se má zobrazit v seznamu serveru SharePoint.  
  
12. Zvolte nový **pacienta podrobnosti** řádek a potom vyberte **nastavit jako výchozí** tlačítko.  
  
     Nové zobrazení je nyní výchozí zobrazení seznamu.  
  
13. Přidejte následující sloupce, které chcete **vybrané sloupce** seznamu v následujícím pořadí:  
  
    -   Pacienta ID  
  
    -   Jméno pacienta  
  
    -   Telefon domů  
  
    -   E-mailu  
  
    -   Název Doctor  
  
    -   Měla nemocnice  
  
    -   Komentáře  
  
14. V **vlastnosti** seznam, vyberte **řazení a seskupování** vlastnost a potom zvolte tlačítko se třemi tečkami ![třemi tečkami ikonu](../sharepoint/media/ellipsisicon.gif "třemi tečkami ikonu")zobrazíte **řazení a seskupování** dialogové okno.  
  
15. V **název sloupce** vyberte **pacienta název**, ujistěte se, že **Sorting** sloupec je nastavený na **vzestupné**a potom vyberte  **OK** tlačítko.  
  
##  <a name="BKMK_TestApp"></a>Testování aplikace  
 Teď, když sloupce vlastního webu, typu obsahu a seznamu jsou připravené, jejich nasazení do služby SharePoint a spusťte aplikaci otestovat.  
  
#### <a name="to-test-the-application"></a>Testování aplikace  
  
1.  Na řádku nabídek zvolte **soubor**, **Uložit vše**.  
  
2.  Zvolte klávesy F5 a spusťte aplikaci.  
  
     Kompiluje aplikace a pak se jeho funkce aktivována a nasazena do služby SharePoint.  
  
3.  V rychlé navigačním panelu zvolte **pacientů** odkaz zobrazíte **pacientů** seznamu.  
  
     Názvy sloupců v seznamu má odpovídající těm, které jste zadali na **zobrazení** kartě v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
4.  Vyberte **přidat novou položku** odkaz pro vytvoření informací o pacientech karty.  
  
5.  Zadejte informace do polí a potom zvolte **Uložit** tlačítko.  
  
     V seznamu se zobrazí nový záznam.  
  
## <a name="see-also"></a>Viz také  
 [Vytváření sloupců webu, typů obsahu a seznamů pro službu SharePoint](../sharepoint/creating-site-columns-content-types-and-lists-for-sharepoint.md)   
 [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)   
 [Postupy: vytvoření vlastního pole typu](http://go.microsoft.com/fwlink/?LinkId=192079)   
 [Typy obsahu](http://go.microsoft.com/fwlink/?LinkId=192080)   
 [Sloupce](http://go.microsoft.com/fwlink/?LinkId=192081)  
  
  