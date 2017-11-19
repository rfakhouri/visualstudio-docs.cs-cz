---
title: "Návod: Volání kódu z jazyka VBA v projektu jazyka Visual Basic | Microsoft Docs"
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
- documents [Office development in Visual Studio], Visual Basic for Applications and
- ThisDocument class
- Word [Office development in Visual Studio], calling code from VBA
- Visual Basic [Office development in Visual Studio], calling code from VBA
- VBA [Office development in Visual Studio], calling code in document-level customizations
- Office documents [Office development in Visual Studio, Visual Basic for Applications and
- calling code from VBA
- document-level customizations [Office development in Visual Studio], calling code
ms.assetid: 798bc2fa-449e-4d1a-86b4-18e57b02a4a8
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bd1dfd2f1b1565a861b91730483cecde26fa9f08
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-calling-code-from-vba-in-a-visual-basic-project"></a>Návod: Volání kódu z jazyka VBA v projektu jazyka Visual Basic
  Tento návod ukazuje, jak volat metodu přizpůsobení na úrovni dokumentu pro aplikaci Microsoft Office Word z jazyka Visual Basic pro aplikace (VBA) kód v dokumentu. Postup zahrnuje tři základní kroky: Přidejte metodu k `ThisDocument` položky třída hostitele, vystavit metody VBA kód a potom volejte metodu z kódu jazyka VBA v dokumentu.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 I když tento návod používá slovo konkrétně koncepty znázorněno pomocí průvodce jsou rovněž vztahují na projekty na úrovni dokumentu pro Excel.  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Vytvoření dokumentu, který obsahuje VBA kód.  
  
-   Důvěřující umístění dokumentu s použitím v Centru zabezpečení v aplikaci Word.  
  
-   Přidání metody do `ThisDocument` položky třída hostitele.  
  
-   Vystavení metody VBA kód.  
  
-   Volání metody z jazyka VBA kód.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft Word  
  
## <a name="creating-a-document-that-contains-vba-code"></a>Vytvoření dokumentu, který obsahuje VBA kód  
 Prvním krokem je vytvoření s podporou maker dokumentu, který obsahuje jednoduché makro VBA pro vytváření. Dokument musí obsahovat VBA pro vytváření projektu, než vytvoříte projekt sady Visual Studio, který je založen na tomto dokumentu. Visual Studio nelze upravit, jinak hodnota VBA projekt, který má povolení VBA kód provést volání do sestavení vlastní nastavení.  
  
 Pokud již máte dokument, který obsahuje VBA kód, který chcete použít, můžete tento krok přeskočit.  
  
#### <a name="to-create-a-document-that-contains-vba-code"></a>Vytvoření dokumentu, který obsahuje VBA kód  
  
1.  Spuštění aplikace Word.  
  
2.  Uloží aktivní dokument jako slovo **dokument s podporou maker (\*DOCM)** s názvem **DocumentWithVBA**. Ho uložte do vhodného umístění, jako je například plochy.  
  
3.  Na pásu karet klikněte na **vývojáře** kartě.  
  
    > [!NOTE]  
    >  Pokud **vývojáře** karta není viditelný, musíte ji nejdříve zobrazit. Další informace najdete v tématu [postupy: zobrazení karty Vývojář na pásu karet](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md).  
  
4.  V **kód** klikněte na možnost **jazyka Visual Basic**.  
  
     Otevře se Editor jazyka Visual Basic.  
  
5.  V **projektu** okna, klikněte dvakrát na **ThisDocument**.  
  
     V souboru kódu `ThisDocument` objektu se otevře.  
  
6.  Přidejte následující VBA kód do souboru kódu. Tento kód definuje jednoduché funkci, která se nic nestane. Jediným účelem: Tato funkce je zajistit, že projekt VBA existuje v dokumentu. To je potřeba na pozdější kroky v tomto návodu.  
  
    ```  
    Sub EmptySub()  
    End Sub  
    ```  
  
7.  Uložte dokument a ukončete aplikace Word.  
  
## <a name="creating-the-project"></a>Vytvoření projektu  
 Nyní můžete vytvořit projekt na úrovni dokumentu ve Wordu, který používá s podporou maker dokument, který jste vytvořili dříve.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Spustit [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
2.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **projektu**. Pokud vaše IDE je nastavený na použití nastavení vývoj jazyka Visual Basic, na **soubor** nabídky, klikněte na tlačítko **nový projekt**.  
  
3.  Rozbalte v podokně šablon **jazyka Visual Basic**a potom rozbalte **Office/SharePoint**.  
  
4.  Vyberte **Office Add in** uzlu.  
  
5.  V seznamu šablon projektu, vyberte **dokument aplikace Word 2010** nebo **dokument aplikace Word 2013** projektu.  
  
6.  V **název** zadejte **CallingCodeFromVBA**.  
  
7.  Click **OK**.  
  
     **Visual Studio Tools for Office – Průvodce projektem** otevře.  
  
8.  Vyberte **zkopírovat stávající dokument**a v **úplnou cestu stávající dokument** zadejte umístění **DocumentWithVBA** dokument, který jste vytvořili dříve . Pokud používáte vlastní dokument podporou maker, zadejte umístění tohoto dokumentu.  
  
9. Klikněte na tlačítko **Dokončit**.  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]Otevře se **DocumentWithVBA** dokumentu v návrháři a přidá **CallingCodeFromVBA** projektu do **Průzkumníku řešení**.  
  
## <a name="trusting-the-location-of-the-document"></a>Důvěřující umístění dokumentu  
 Před kódu můžete vystavit ve vašem řešení VBA kód v dokumentu, musí důvěřovat VBA v dokumentu ke spuštění. Chcete-li to provést několika způsoby. V tomto návodu důvěřovat umístění dokumentu v **Centrum zabezpečení** v aplikaci Word.  
  
#### <a name="to-trust-the-location-of-the-document"></a>Důvěřovat umístění dokumentu  
  
1.  Spuštění aplikace Word.  
  
2.  Klikněte **souboru** kartě.  
  
3.  Klikněte **možnosti v aplikaci Word** tlačítko.  
  
4.  V podokně kategorie, klikněte na **Centrum zabezpečení**.  
  
5.  V podokně podrobností klikněte na tlačítko **nastavení Centra zabezpečení**.  
  
6.  V podokně kategorie, klikněte na **důvěryhodné umístění**.  
  
7.  V podokně podrobností klikněte na tlačítko **přidat nové umístění**.  
  
8.  V **umístění důvěryhodné Microsoft Office** dialogové okno, přejděte do složky, která obsahuje **CallingCodeFromVBA** projektu.  
  
9. Vyberte **podsložky toto umístění jsou také důvěryhodné**.  
  
10. V **umístění důvěryhodné Microsoft Office** dialogové okno, klikněte na tlačítko **OK**.  
  
11. V **Centrum zabezpečení** dialogové okno, klikněte na tlačítko **OK**.  
  
12. V **možnosti v aplikaci Word** dialogové okno, klikněte na tlačítko **OK**.  
  
13. Ukončete aplikaci Word.  
  
## <a name="adding-a-method-to-the-thisdocument-class"></a>Přidání metody do ThisDocument – třída  
 Teď, když je projekt VBA nastavili, přidejte metodu k `ThisDocument` položky třída, kterou můžete volat z kódu VBA pro vytváření hostitele.  
  
#### <a name="to-add-a-method-to-the-thisdocument-class"></a>Přidání metody do ThisDocument – třída  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **ThisDocument.vb**a potom klikněte na **kód zobrazení**.  
  
     **ThisDocument.vb** soubor se otevře v editoru kódu.  
  
2.  Přidejte následující metodu do `ThisDocument` třídy. Tato metoda vytvoří tabulku se dva řádky a dva sloupce na začátku dokumentu. Parametry zadejte text, který se zobrazí na prvním řádku. Dále v tomto návodu bude tuto metodu volat z kódu jazyka VBA v dokumentu.  
  
     [!code-vb[Trin_CallingVBCustomizationFromVBA#1](../vsto/codesnippet/VisualBasic/CallingCodeFromVBA/ThisDocument.vb#1)]  
  
3.  Sestavte projekt.  
  
## <a name="exposing-the-method-to-vba-code"></a>Vystavení metody VBA kód  
 Ke zveřejnění `CreateTable` Metoda VBA kód v dokumentu, nastavte **EnableVbaCallers** vlastnost `ThisDocument` položky hostitele **True**.  
  
#### <a name="to-expose-the-method-to-vba-code"></a>Aby se zveřejnily metody VBA kód  
  
1.  V **Průzkumníku řešení**, dvakrát klikněte na **ThisDocument.vb**.  
  
     **DocumentWithVBA** soubor se otevře v návrháři.  
  
2.  V **vlastnosti** vyberte **EnableVbaCallers** vlastnost a změňte hodnotu na **True**.  
  
3.  Klikněte na tlačítko **OK** zprávy, která se zobrazí.  
  
4.  Sestavte projekt.  
  
## <a name="calling-the-method-from-vba-code"></a>Volání metody z jazyka VBA kód  
 Nyní můžete volat `CreateTable` metoda z kódu jazyka VBA v dokumentu.  
  
> [!NOTE]  
>  V tomto návodu přidáte VBA kód v dokumentu při ladění projektu. VBA kód, které přidáte k tomuto dokumentu budou přepsány příštím sestavení projektu, protože Visual Studio nahradí kopii dokumentu ze složky hlavní projektu dokumentu do výstupní složky sestavení. Pokud chcete uložit VBA kód, zkopírujte jej do dokumentu ve složce projektu. Další informace najdete v tématu [kombinování VBA pro vytváření a úpravy na úrovni dokumentů](../vsto/combining-vba-and-document-level-customizations.md).  
  
#### <a name="to-call-the-method-from-vba-code"></a>K volání metody z jazyka VBA kód  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  Na **vývojáře** ve **kód** klikněte na možnost **jazyka Visual Basic**.  
  
     Otevře se Editor jazyka Visual Basic.  
  
3.  Na **vložit** nabídky, klikněte na tlačítko **modulu**.  
  
4.  Přidejte následující kód do nového modulu.  
  
     Tento kód zavolá `CreateTable` metoda v sestavení vlastní nastavení. Makro přistoupí pomocí této metody `CallVSTOAssembly` vlastnost `ThisDocument` objektu. Tato vlastnost se automaticky vygenerovala při nastavení **EnableVbaCallers** vlastnost dříve v tomto návodu.  
  
    ```  
    Sub CreateTable()  
        Call ThisDocument.CallVSTOAssembly.CreateTable("Employee Name", "Start Date")  
    End Sub  
    ```  
  
5.  Stiskněte klávesu F5.  
  
6.  Ověřte, že byl přidán do nové tabulky v dokumentu.  
  
7.  Ukončit aplikaci Word bez uložení změn.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o volání kódu v řešeních pro systém Office z jazyka VBA v těchto tématech:  
  
-   Volání kódu v přizpůsobení Visual C# z jazyka VBA. Tento proces se liší od proces jazyka Visual Basic. Další informace najdete v tématu [návod: volání kódu z jazyka VBA v Visual C &#35; Projekt](../vsto/walkthrough-calling-code-from-vba-in-a-visual-csharp-project.md).  
  
-   Volání kódu v doplňku VSTO z jazyka VBA. Další informace najdete v tématu [návod: volání kódu v Add-in VSTO z jazyka VBA](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md).  
  
## <a name="see-also"></a>Viz také  
 [Kombinování VBA pro vytváření a úpravy na úrovni dokumentů](../vsto/combining-vba-and-document-level-customizations.md)   
 [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)   
 [Postupy: vystavení kódu do VBA v projektu jazyka Visual Basic](../vsto/how-to-expose-code-to-vba-in-a-visual-basic-project.md)   
 [Postupy: vystavení kódu do VBA v Visual C &#35; Projekt](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md)   
 [Návod: Volání kódu z jazyka VBA v Visual C &#35; Projekt](../vsto/walkthrough-calling-code-from-vba-in-a-visual-csharp-project.md)  
  
  