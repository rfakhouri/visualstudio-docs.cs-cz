---
title: 'Tutoriál 1: Vytvoření prohlížeče obrázků'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 3071d6df-2b2f-4e95-ab68-bef727323136
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5be14bf68f88bc058adf3685cc30e3ab545a6354
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="tutorial-1-create-a-picture-viewer"></a>Tutoriál 1: Vytvoření prohlížeče obrázků
V tomto kurzu vytvoříte program, který načte obrázek ze souboru a zobrazí v okně. Zjistíte, jak přetáhněte ovládací prvky jako tlačítka a pole obrázků ve formuláři, nastavit jejich vlastnosti a použití kontejnerů plynule změnit velikost formuláře. Můžete také začít psát kód. Získáte informace o následujících postupech:  

-   Vytvořte nový projekt.  

-   Test (ladění) aplikace.  

-   Základní ovládací prvky jako tlačítka a zaškrtávací políčka přidejte do formuláře.  

-   Umístěte ovládací prvky ve formuláři pomocí rozložení.  

-   Přidat **otevření souboru** a **barva** dialogová okna do formuláře.  

-   Zápis kódu pomocí IntelliSense a fragmenty kódu.  

-   Zápis metody obslužná rutina události.  

 Po dokončení, váš program bude vypadat jako na následujícím obrázku.  

 ![Obrázek, který vytvoříte v tomto kurzu](../ide/media/express_pictureviewerdone.png "Express_PictureViewerDone")  
Obrázek, který vytvoříte v tomto kurzu  

 Si můžete stáhnout dokončené verzi příkladu [kurz ukázka dokončení Prohlížeč obrázků](http://code.msdn.microsoft.com/Complete-Picture-Viewer-7d91d3a8).  

 ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo")video verzi tohoto tématu naleznete v části [jak I: vytvořit Prohlížeč obrázků v jazyce Visual Basic?](http://go.microsoft.com/fwlink/?LinkId=205207) nebo [jak I: vytvořit Prohlížeč obrázků v jazyce C#?](http://go.microsoft.com/fwlink/?LinkId=205198).  

> [!NOTE]
>  Tyto videa pomocí starší verze sady Visual Studio, takže drobné rozdíly v některé příkazy a další prvky uživatelského rozhraní. Však koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio. Visual C# a Visual Basic jsou obě popsané v tomto kurzu, proto soustředit se na informace specifické pro programovací jazyk, který používáte.  
>   
>  Zobrazit kód jazyka Visual Basic, vyberte **VB** v horní části bloky kódu a zobrazit kódu pro Visual C#, vyberte **C#** kartě. Pokud vás zajímá seznamovat Visual C++, přečtěte si téma [Začínáme](../ide/getting-started-with-cpp-in-visual-studio.md) a [kurzu jazyk C++](http://www.cplusplus.com/doc/tutorial/).  
>   
>  Pokud vás zajímají informace o způsobu zápisu Visual C# nebo Visual Basic UWP aplikací najdete v tématu [aplikace UWP sestavení](https://developer.microsoft.com/windows/apps).

## <a name="related-topics"></a>Související témata  

|Název|Popis|  
|-----------|-----------------|  
|[Krok 1: Vytvořte projekt formulářové aplikace Windows](../ide/step-1-create-a-windows-forms-application-project.md)|Začněte tím, že vytvoříte projekt aplikace Windows Forms.|  
|[Krok 2: Spusťte svůj program](../ide/step-2-run-your-program.md)|Spusťte program aplikaci Windows Forms, který jste vytvořili v předchozím kroku.|  
|[Krok 3: Nastavte vlastnosti svého formuláře](../ide/step-3-set-your-form-properties.md)|Změnit způsob vzhled formuláře pomocí **vlastnosti** okno.|  
|[Krok 4: Rozvrhněte svůj formulář pomocí ovládacího prvku TableLayoutPanel](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md)|Přidat `TableLayoutPanel` ovládacího prvku do svého formuláře.|  
|[Krok 5: Přidejte do svého formuláře ovládací prvky](../ide/step-5-add-controls-to-your-form.md)|Přidání ovládacích prvků, například `PictureBox` řízení a `CheckBox` do svého formuláře ovládací prvek. Přidání tlačítka do svého formuláře.|  
|[Krok 6: Pojmenujte své ovládací prvky tlačítek](../ide/step-6-name-your-button-controls.md)|Přejmenujte tlačítka požadavků uživatele.|  
|[Krok 7: Přidejte do svého formuláře komponenty dialogových oken](../ide/step-7-add-dialog-components-to-your-form.md)|Přidat **OpenFileDialog** součásti a **ColorDialog** součásti do svého formuláře.|  
|[Krok 8: Zapište kód pro obslužnou rutinu události zobrazení tlačítka s obrázkem](../ide/step-8-write-code-for-the-show-a-picture-button-event-handler.md)|Psaní kódu pomocí nástroje IntelliSense.|  
|[Krok 9: Zrevidujte, okomentujte a otestujte svůj kód](../ide/step-9-review-comment-and-test-your-code.md)|Zkontrolujte a otestujte svůj kód. Podle potřeby přidejte komentáře.|  
|[Krok 10: Zapište kód pro přídavná tlačítka a zaškrtávací pole](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md)|Napište kód, aby ostatní tlačítka a zaškrtávací políčko pracovní pomocí IntelliSense.|  
|[Krok 11: Spusťte svůj program a vyzkoušejte další funkce](../ide/step-11-run-your-program-and-try-other-features.md)|Spusťte svůj program a nastavte barvu pozadí. Vyzkoušejte jiné funkce, jako je například změna barvy, písma a hranice.|
