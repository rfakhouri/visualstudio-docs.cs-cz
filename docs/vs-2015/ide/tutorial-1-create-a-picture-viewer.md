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
ms.openlocfilehash: c382ff2a16e47f52a33e5c6728f0c57d57e4315b
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65703054"
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
> Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídek a jiných prvcích uživatelského rozhraní. Nicméně koncepty a postupy fungují podobně jako v aktuální verzi sady Visual Studio. Visual C# a Visual Basic jsou obě popsané v tomto kurzu, takže se zaměřte na informace, které jsou specifické pro programovací jazyk, který používáte.  
>   
> Chcete-li zobrazit kód v jazyce Visual Basic, zvolte **VB** kartě v horní části bloků kódu a chcete-li zobrazit kód pro jazyk Visual C#, zvolte **jazyka C#** kartu. Pokud máte zájem o získání informací o jazyce Visual C++, přejděte [Začínáme](../misc/getting-started-with-visual-cpp-in-visual-studio-2015.md) a [kurz jazyka C++](http://www.cplusplus.com/doc/tutorial/).  
>   
> Pokud máte zájem se naučit, jak psát aplikace Visual C# nebo Visual Basic aplikací pro Windows Store, naleznete v tématu [vytvoření první aplikace pro Windows Store pomocí jazyka C# nebo Visual Basic](https://msdn.microsoft.com/library/windows/apps/hh974581.aspx). Informace o vytváření aplikací jazyka JavaScript pro Windows Store naleznete v tématu [vytvoření první aplikace pro Windows Store pomocí jazyka JavaScript](https://msdn.microsoft.com/library/windows/apps/br211385.aspx).  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Krok 1: Vytvoření projektu formulářové aplikace Windows](../ide/step-1-create-a-windows-forms-application-project.md)|Začněte vytvořením projektu aplikace Windows Forms.|  
|[Krok 2: Spuštění programu](../ide/step-2-run-your-program.md)|Spusťte program aplikace Windows Forms, který jste vytvořili v předchozím kroku.|  
|[Krok 3: Nastavení vlastností formuláře](../ide/step-3-set-your-form-properties.md)|Změnit způsob, jakým vzhled formuláře pomocí **vlastnosti** okna.|  
|[Krok 4: Rozvržení formuláře pomocí ovládacího prvku TableLayoutPanel](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md)|Přidat `TableLayoutPanel` ovládací prvek do formuláře.|  
|[Krok 5: Přidání ovládacích prvků do formuláře](../ide/step-5-add-controls-to-your-form.md)|Přidejte ovládací prvky, například `PictureBox` ovládacího prvku a `CheckBox` ovládací prvek do formuláře. Přidejte tlačítka do formuláře.|  
|[Krok 6: Pojmenování tlačítkových ovládacích prvků](../ide/step-6-name-your-button-controls.md)|Přejmenujte tlačítka na něco smysluplnějšího.|  
|[Krok 7: Přidání komponent dialogových oken do formuláře](../ide/step-7-add-dialog-components-to-your-form.md)|Přidat **OpenFileDialog** komponenty a **ColorDialog** komponentu do formuláře.|  
|[Krok 8: Napsání kódu pro obslužnou rutinu události zobrazení tlačítka s obrázkem](../ide/step-8-write-code-for-the-show-a-picture-button-event-handler.md)|Pište kód pomocí nástroje technologie IntelliSense.|  
|[Krok 9: Kontrola, okomentování a otestování kódu](../ide/step-9-review-comment-and-test-your-code.md)|Zkontrolujte a otestujte svůj kód. Podle potřeby přidejte komentáře.|  
|[Krok 10: Napsání kódu pro přídavná tlačítka a zaškrtávací políčko](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md)|Psaní kódu, aby další tlačítka a zaškrtávací políčko pracovala pomocí technologie IntelliSense.|  
|[Krok 11: Spuštění programu a vyzkoušení dalších funkcí](../ide/step-11-run-your-program-and-try-other-features.md)|Spusťte svůj program a nastavit barvu pozadí. Vyzkoušejte další funkce, jako je například změna barvy, písma a ohraničení.|
