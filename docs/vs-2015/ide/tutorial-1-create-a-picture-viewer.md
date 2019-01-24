---
title: 'Kurz 1: Vytvoření prohlížeče obrázků | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 3071d6df-2b2f-4e95-ab68-bef727323136
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 756c979a19451a940e52165d60cc2e5d3fb6b315
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54796813"
---
# <a name="tutorial-1-create-a-picture-viewer"></a>Kurz 1: Vytvoření prohlížeče obrázků
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V tomto kurzu vytvoříte program, který načte obrázek ze souboru a zobrazí jej v okně. Naučíte se přetáhnout prvky jako tlačítka a pole obrázků ve formuláři, nastavit jejich vlastnosti a plynule změnit velikost formuláře pomocí kontejnerů. Můžete také začít psát kód. Získáte informace o následujících postupech:  
  
- Vytvořte nový projekt.  
  
- Otestujte (vylaďte) aplikaci.  
  
- Přidejte základní ovládací prvky jako zaškrtávací políčka a tlačítka do formuláře.  
  
- Umístit ovládací prvky na formulář pomocí rozložení.  
  
- Přidat **otevřít soubor** a **barva** dialogová okna do formuláře.  
  
- Pište kód pomocí technologie IntelliSense a fragmentů kódu.  
  
- Zápis obslužné rutiny události.  
  
  Jakmile skončíte, program bude vypadat jako na následujícím obrázku.  
  
  ![Obrázek, který vytvoříte v tomto kurzu](../ide/media/express-pictureviewerdone.png "Express_PictureViewerDone")  
  Obrázek, který vytvoříte v tomto kurzu  
  
  Chcete-li stáhnout úplnou verzi vzorku, přečtěte si téma [ukázkový kurz pro dokončení prohlížeče obrázků](http://code.msdn.microsoft.com/Complete-Picture-Viewer-7d91d3a8).  
  
  ![odkaz na video](../data-tools/media/playvideo.gif "PlayVideo")video verzi tohoto tématu naleznete v tématu [postupy: Vytvoření prohlížeče obrázků v jazyce Visual Basic? ](http://go.microsoft.com/fwlink/?LinkId=205207) nebo [postup: Vytvoření prohlížeče obrázků v C#? ](http://go.microsoft.com/fwlink/?LinkId=205198).  
  
> [!NOTE]
>  Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídek a jiných prvcích uživatelského rozhraní. Nicméně koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio. Visual C# a Visual Basic jsou obě popsané v tomto kurzu, takže se zaměřte na informace, které jsou specifické pro programovací jazyk, který používáte.  
>   
>  Chcete-li zobrazit kód v jazyce Visual Basic, zvolte **VB** kartě v horní části bloků kódu a chcete-li zobrazit kód pro jazyk Visual C#, zvolte **jazyka C#** kartu. Pokud máte zájem o získání informací o jazyce Visual C++, přejděte [Začínáme](../misc/getting-started-with-visual-cpp-in-visual-studio-2015.md) a [kurz jazyka C++](http://www.cplusplus.com/doc/tutorial/).  
>   
>  Pokud máte zájem se naučit, jak psát aplikace Visual C# nebo Visual Basic aplikací pro Windows Store, naleznete v tématu [vytvoření první aplikace pro Windows Store pomocí jazyka C# nebo Visual Basic](http://msdn.microsoft.com/library/windows/apps/hh974581.aspx). Informace o vytváření aplikací jazyka JavaScript pro Windows Store naleznete v tématu [vytvoření první aplikace pro Windows Store pomocí jazyka JavaScript](http://msdn.microsoft.com/library/windows/apps/br211385.aspx).  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Krok 1: Vytvořte projekt Formulářové aplikace Windows](../ide/step-1-create-a-windows-forms-application-project.md)|Začněte vytvořením projektu aplikace Windows Forms.|  
|[Krok 2: Spusťte svůj Program](../ide/step-2-run-your-program.md)|Spusťte program aplikace Windows Forms, který jste vytvořili v předchozím kroku.|  
|[Krok 3: Nastavte vlastnosti svého formuláře](../ide/step-3-set-your-form-properties.md)|Změnit způsob, jakým vzhled formuláře pomocí **vlastnosti** okna.|  
|[Krok 4: Rozvrhněte svůj formulář pomocí ovládacího prvku TableLayoutPanel](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md)|Přidat `TableLayoutPanel` ovládací prvek do formuláře.|  
|[Krok 5: Přidejte do svého formuláře ovládací prvky](../ide/step-5-add-controls-to-your-form.md)|Přidejte ovládací prvky, například `PictureBox` ovládacího prvku a `CheckBox` ovládací prvek do formuláře. Přidejte tlačítka do formuláře.|  
|[Krok 6: Pojmenujte své ovládací prvky tlačítek](../ide/step-6-name-your-button-controls.md)|Přejmenujte tlačítka na něco smysluplnějšího.|  
|[Krok 7: Přidejte do svého formuláře komponenty dialogových oken](../ide/step-7-add-dialog-components-to-your-form.md)|Přidat **OpenFileDialog** komponenty a **ColorDialog** komponentu do formuláře.|  
|[Krok 8: Napsat kód pro zobrazení obslužné rutiny události obrázku tlačítka](../ide/step-8-write-code-for-the-show-a-picture-button-event-handler.md)|Pište kód pomocí nástroje technologie IntelliSense.|  
|[Krok 9: Zkontrolujte, komentáře a testování kódu](../ide/step-9-review-comment-and-test-your-code.md)|Zkontrolujte a otestujte svůj kód. Podle potřeby přidejte komentáře.|  
|[Krok 10: Napsat kód pro přídavná tlačítka a zaškrtávací políčko](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md)|Psaní kódu, aby další tlačítka a zaškrtávací políčko pracovala pomocí technologie IntelliSense.|  
|[Krok 11: Spusťte Program a vyzkoušejte další funkce](../ide/step-11-run-your-program-and-try-other-features.md)|Spusťte svůj program a nastavit barvu pozadí. Vyzkoušejte další funkce, jako je například změna barvy, písma a ohraničení.|
